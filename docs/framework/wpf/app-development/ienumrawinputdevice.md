---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: e465193d6a91848a27c2832dda454c6c45837e92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530024"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
Diese Schnittstelle listet die Geräte für die unformatierte Eingabe auf und wird nur von "PresentationHost.exe" verwendet.  
  
> [!NOTE]
>  Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|Listet die nächsten `celt`-Elemente (RAWINPUTDEVICE-Strukturen) in der Liste des Enumerators auf, wobei die Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched` erfolgt.|  
|[IEnumRAWINPUTDEVIC:Skip](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|Weist den Enumerator zum nächsten überspringen `celt` Elemente in der Enumeration, damit der nächste Aufruf von [Ienumrawinputdevic](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) diese Elemente nicht zurückgibt.|  
|[IEnumRAWINPUTDEVIC:Reset](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|Setzt die Enumerationsfolge auf den Anfang zurück.|  
|[IEnumRAWINPUTDEVIC:Clone](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.|  
  
## <a name="see-also"></a>Siehe auch
- [Informationen zur unformatierten Eingabe](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
