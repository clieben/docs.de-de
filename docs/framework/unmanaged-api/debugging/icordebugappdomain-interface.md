---
title: ICorDebugAppDomain-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9588ac26c698a8369f1ae4be89af7440a2dd1de4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546305"
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain-Schnittstelle1
Stellt Methoden zum Debuggen von Anwendungsdomänen bereit. Diese Schnittstelle ist eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Attach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Fügt den Debugger an die Anwendungsdomäne an.|  
|[EnumerateAssemblies-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.|  
|[EnumerateBreakpoints-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Ruft einen Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ab.|  
|[EnumerateSteppers-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Ruft einen Enumerator für alle aktiven Stepper in der Anwendungsdomäne ab.|  
|[GetID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Ruft die eindeutige ID der Anwendungsdomäne ab.|  
|[GetModuleFromMetaDataInterface-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Ruft das ICorDebugModule-Objekt, mit der angegebenen Metadaten-Schnittstelle.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Ruft den Namen der Anwendungsdomäne.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne der common Language Runtime (CLR) ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Ruft den Prozess ab, die die Anwendungsdomäne enthält.|  
|[IsAttached-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Bestimmt, ob die Anwendungsdomäne der Debugger angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
