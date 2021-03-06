---
title: Duplexdienste
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: 9adbb4166d713cea0344c9fa58ce85e5afce086d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717909"
---
# <a name="duplex-services"></a>Duplexdienste
Bei einem Duplexdienstvertrag handelt es sich um ein Nachrichtenaustauschmuster, bei dem beide Endpunkte eigenständig Nachrichten an den jeweils anderen Endpunkt senden können. Daher kann ein Duplexdienst Nachrichten zurück an den Clientendpunkt senden und so ein ereignisähnliches Verhalten bereitstellen. Eine Duplexkommunikation findet statt, wenn ein Client eine Verbindung mit einem Dienst herstellt und dem Dienst einen Kanal bereitstellt, über den dieser Nachrichten zurück an den Client senden kann. Beachten Sie, dass Duplexdienste nur innerhalb einer Sitzung ein ereignisähnliches Verhalten zeigen.  
  
 Um einen Duplexvertrag einzurichten, erstellen Sie zwei Schnittstellen. Bei der ersten handelt es sich um die Dienstvertragschnittstelle, mit der die Vorgänge beschrieben werden, die von einem Client implementiert werden können. Dieser Dienstvertrag muss Geben Sie einen *Rückrufvertrag* in die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Eigenschaft. Der Rückrufvertrag wiederum ist die Schnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können. Ein Duplexvertrag erfordert keine Sitzung, die vom System bereitgestellten Duplexbindungen nutzen allerdings Sitzungen.  
  
 Das folgende Beispiel zeigt einen Duplexvertrag.  
  
 [!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
 [!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]  
  
 Die `CalculatorService`-Klasse implementiert die primäre `ICalculatorDuplex`-Schnittstelle. Der Dienst verwendet den <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanzmodus, um die Ergebnisse für die einzelnen Sitzungen zu pflegen. Die private `Callback`-Eigenschaft greift auf den Rückrufkanal zu, der zum Client führt. Der Dienst nutzt den Rückruf, um über die Rückrufschnittstelle Nachrichten zurück an den Client zu senden, wie im folgenden Beispielcode gezeigt.  
  
 [!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
 [!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]  
  
 Damit Nachrichten vom Dienst empfangen werden können, muss der Client eine Klasse bereitstellen, die die Rückrufschnittstelle des Duplexvertrags implementiert. Der folgende Beispielcode enthält eine `CallbackHandler`-Klasse, durch die die `ICalculatorDuplexCallback`-Schnittstelle implementiert wird.  
  
 [!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
 [!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]  
  
 Der WCF-Client, der generiert wird, für ein Duplexvertrag erfordert eine <xref:System.ServiceModel.InstanceContext> Klasse, um bei der Erstellung bereitgestellt werden. Diese <xref:System.ServiceModel.InstanceContext>-Klasse wird als Standort für ein Objekt verwendet, das die Rückrufschnittstelle implementiert und die vom Dienst zurückgesendeten Nachrichten verarbeitet. Eine <xref:System.ServiceModel.InstanceContext>-Klasse wird mit einer Instanz der `CallbackHandler`-Klasse erstellt. Dieses Objekt verarbeitet die vom Dienst über die Rückrufschnittstelle an den Client gesendeten Nachrichten.  
  
 [!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
 [!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]  
  
 Der Dienst muss so konfiguriert werden, dass eine Bindung bereitgestellt wird, die sowohl eine Sitzungskommunikation als auch eine Duplexkommunikation unterstützt. Das `wsDualHttpBinding`-Element unterstützt die sitzungsbasierte Kommunikation und ermöglicht durch Bereitstellung dualer HTTP-Verbindungen (eine Verbindung pro Richtung) auch eine Duplexkommunikation.  
  
 Auf dem Client muss, wie in der folgenden Beispielkonfiguration zu sehen, eine Adresse konfiguriert werden, über die der Server eine Verbindung mit dem Client herstellen kann.  
  
  
  
> [!NOTE]
>  Nichtduplex-Clients, bei denen keine Authentifizierung über eine sichere Konversation möglich ist, lösen in der Regel eine <xref:System.ServiceModel.Security.MessageSecurityException> aus. Wenn jedoch bei einem Duplexclient, der eine sichere Konversation verwendet, keine Authentifizierung möglich ist, erhält der Client stattdessen eine <xref:System.TimeoutException>.  
  
 Wenn Sie mit dem `WSHttpBinding`-Element einen Client/Dienst erstellen und keinen Clientrückrufendpunkt aufnehmen, wird der folgende Fehler ausgegeben:  
  
```  
HTTP could not register URL  
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.  
```  
  
 Der folgende Beispielcode veranschaulicht, wie an den Client Endpunktadresse programmgesteuert.
  
```csharp  
WSDualHttpBinding binding = new WSDualHttpBinding();  
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");  
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");  
```  
```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")  
```

 Der folgende Beispielcode zeigt, wie Sie die Clientendpunktadresse in der Konfiguration angeben können:  
  
```xml  
<client>  
    <endpoint name ="ServerEndpoint"   
          address="http://localhost:12000/DuplexTestUsingConfig/Server"  
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"   
            binding="wsDualHttpBinding"  
           contract="IDuplexTest" />  
</client>  
<bindings>  
    <wsDualHttpBinding>  
        <binding name="WSDualHttpBinding_IDuplexTest"    
          clientBaseAddress="http://localhost:8000/myClient/" >  
            <security mode="None"/>  
         </binding>  
    </wsDualHttpBinding>  
</bindings>  
```  
  
> [!WARNING]
>  Das Schließen des zugehörigen Kanals durch einen Dienst oder Client wird vom Duplexmodell nicht in jedem Fall automatisch erkannt. Wenn ein Client unerwartet beendet wird, wird der Dienst daher (standardmäßig) nicht benachrichtigt. Clients und Dienste können eigene Protokolle implementieren, um sich bei Bedarf wechselseitig zu benachrichtigen.  
  
## <a name="see-also"></a>Siehe auch
- [Duplex](../../../../docs/framework/wcf/samples/duplex.md)
- [Angeben des Clientlaufzeitverhaltens](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [Vorgehensweise: Erstellen einer Kanalfactory und zum Erstellen und Verwalten von Kanälen](../../../../docs/framework/wcf/feature-details/how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
