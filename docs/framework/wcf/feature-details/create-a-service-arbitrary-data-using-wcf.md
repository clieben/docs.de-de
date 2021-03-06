---
title: 'Vorgehensweise: Erstellen Sie einen Dienst, akzeptiert der beliebige Daten mithilfe des WCF REST-Programmiermodells'
ms.date: 03/30/2017
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
ms.openlocfilehash: 8728afbe5ebfe31d619b311f521eb1012a0dc323
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666997"
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a>Vorgehensweise: Erstellen Sie einen Dienst, akzeptiert der beliebige Daten mithilfe des WCF REST-Programmiermodells
Unter bestimmten Voraussetzungen benötigen Entwickler umfassende Steuerungsmöglichkeiten für die Rückgabe der Daten durch einen Dienstvorgang. Dies ist der Fall, wenn ein Dienstvorgang zurückgeben muss, Daten in einem Format ByWCF werden nicht unterstützt. In diesem Thema wird erläutert, mit den WCF REST-Programmiermodell zum Erstellen eines Diensts, das beliebige Daten empfangen.  
  
### <a name="to-implement-the-service-contract"></a>So implementieren Sie den Dienstvertrag  
  
1.  Definieren Sie den Dienstvertrag. Der Vorgang, der die beliebigen Daten empfängt, muss über einen Parameter des Typs <xref:System.IO.Stream> verfügen. Außerdem muss es sich bei diesem Parameter um den einzigen Parameter handeln, der im Text der Anforderung übergeben wird. Der in diesem Beispiel beschriebene Vorgang nimmt auch einen Dateinamenparameter an. Dieser Parameter wird innerhalb der URL der Anforderung übergeben. Geben Sie zum Festlegen, dass ein Parameter innerhalb der URL übergeben wird, im <xref:System.UriTemplate> eine <xref:System.ServiceModel.Web.WebInvokeAttribute> an. In diesem Fall verwendete URI aufrufen, beendet diese Methode in "UploadFile/Beliebiger_dateiname". Der Teil von "{Filename}" für die URI-Vorlage gibt an, dass der dateinameparameter für den Vorgang, in dem URI übergeben wird, um den Vorgang aufzurufen.  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  Implementieren Sie den Dienstvertrag. Der Vertrag verfügt über nur eine Methode (`UploadFile`), die in einem Stream eine Datei mit beliebigen Daten empfängt. Der Vorgang liest den Stream, erfasst die Menge der gelesenen Bytes und zeigt anschließend den Dateinamen und die Menge der gelesenen Bytes an.  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a>So hosten Sie den Dienst  
  
1.  Erstellen Sie eine Konsolenanwendung, um den Dienst zu hosten.  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2.  Erstellen Sie eine Variable, um die Basisadresse für den Dienst innerhalb der `Main`-Methode zu speichern.  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz für den Dienst, um die Dienstklasse und die Basisadresse anzugeben.  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  Fügen Sie einen Endpunkt hinzu, durch den der Vertrag, die <xref:System.ServiceModel.WebHttpBinding> sowie das <xref:System.ServiceModel.Description.WebHttpBehavior> angegeben werden.  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  Öffnen des Diensthosts Der Dienst ist nun zum Empfangen von Anforderungen bereit.  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a>So rufen Sie den Dienst programmgesteuert auf  
  
1.  Erstellen Sie eine <xref:System.Net.HttpWebRequest> mit dem URI, mit dem der Dienst aufgerufen wird. In diesem Code wird die Basisadresse mit `"/UploadFile/Text"` kombiniert. Der `"UploadFile"`-Teil des URI gibt den aufzurufenden Vorgang an. Der `"Test.txt"`-Teil des URI gibt den Dateinamenparameter an, der an den `UploadFile`-Vorgang übergeben werden soll. Beide Elemente werden der <xref:System.UriTemplate> zugeordnet, die auf den Vorgangsvertrag angewendet wurde.  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2.  Legen Sie die <xref:System.Net.HttpWebRequest.Method%2A>-Eigenschaft der <xref:System.Net.HttpWebRequest> auf `POST` und die <xref:System.Net.HttpWebRequest.ContentType%2A>-Eigenschaft auf `"text/plain"` fest. Dadurch wird dem Dienst mitgeteilt, dass der Code Daten sendet und diese Daten im Nur-Text-Format vorliegen.  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  Rufen Sie <xref:System.Net.HttpWebRequest.GetRequestStream%2A> auf, um den Anforderungsstream abzurufen, erstellen Sie die zu sendenden Daten, schreiben Sie die Daten in den Anforderungsstream, und schließen Sie anschließend den Stream.  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4.  Rufen Sie die Antwort des Diensts ab, indem Sie <xref:System.Net.HttpWebRequest.GetResponse%2A> aufrufen, und zeigen Sie die Antwortdaten an die Konsole an.  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5.  Schließen Sie den Diensthost.  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie eine vollständige Liste des Codes für dieses Beispiel:  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Verweisen Sie beim Kompilieren des Codes auf "System.ServiceModel.dll" und "System.ServiceModel.Web.dll".  
  
## <a name="see-also"></a>Siehe auch
- [UriTemplate und UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)
- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [Überblick über das WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
