---
title: 'Fehler beim Erstellen des Assemblymanifests: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 86c1fabe1116e5b5d7e81022777f861f6d57e3e6
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758364"
---
# <a name="error-creating-assembly-manifest-error-message"></a>Fehler beim Erstellen des Assemblymanifests: \<Fehlermeldung >
Visual Basic-Compiler Ruft die Assembly Linker (Al.exe, auch bekannt als Alink) aus, um eine Assembly mit einem Manifest zu generieren. Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.  
  
 Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt. Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält. Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält. Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **Fehler-ID:** BC30140  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). für Fehler al1019, um weitere erläuterungen und Hinweise zu erhalten  
  
2.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [Seite „Signierung“, Projekt-Designer](/visualstudio/ide/reference/signing-page-project-designer)
- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
