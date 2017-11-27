---
title: CorDebugSetContextFlag-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugSetContextFlag
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugSetContextFlag
helpviewer_keywords: CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 958ed303fab3dcb01fad2040dd06381e76fe5a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="ab897-102">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ab897-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="ab897-103">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ab897-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab897-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab897-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="ab897-105">Member</span><span class="sxs-lookup"><span data-stu-id="ab897-105">Members</span></span>  
  
|<span data-ttu-id="ab897-106">Member</span><span class="sxs-lookup"><span data-stu-id="ab897-106">Member</span></span>|<span data-ttu-id="ab897-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab897-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ab897-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="ab897-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="ab897-109">Der Kontext ist aktiven Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="ab897-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="ab897-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="ab897-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="ab897-111">Der Kontext wurde durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ab897-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab897-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab897-112">Remarks</span></span>  
 <span data-ttu-id="ab897-113">`CorDebugSetContextFlag`enthält Werte, mit denen, die [ICorDebugStackWalk:: SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ab897-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab897-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab897-114">Requirements</span></span>  
 <span data-ttu-id="ab897-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab897-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab897-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab897-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab897-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab897-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab897-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab897-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab897-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab897-119">See Also</span></span>  
 [<span data-ttu-id="ab897-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ab897-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="ab897-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ab897-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)