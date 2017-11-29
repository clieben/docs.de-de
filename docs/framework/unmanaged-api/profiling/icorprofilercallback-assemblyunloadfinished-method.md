---
title: ICorProfilerCallback::AssemblyUnloadFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 144f7af59afbb403d9ec1894f06c5c028b767416
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="a35d4-102">ICorProfilerCallback::AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="a35d4-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="a35d4-103">Benachrichtigt den Profiler, dass eine Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a35d4-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a35d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a35d4-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a35d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a35d4-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a35d4-106">[in] Identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="a35d4-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a35d4-107">[in] Ein HRESULT, das angibt, ob die Assembly erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a35d4-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a35d4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a35d4-108">Remarks</span></span>  
 <span data-ttu-id="a35d4-109">Der Wert der `assemblyId` gilt nicht für eine Anforderung Informationen nach der [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) -Methode zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="a35d4-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="a35d4-110">Einige Teile der Assembly entladen möglicherweise weiterhin nach dem `AssemblyUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="a35d4-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="a35d4-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="a35d4-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a35d4-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil die Assembly entladen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a35d4-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a35d4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a35d4-113">Requirements</span></span>  
 <span data-ttu-id="a35d4-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a35d4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a35d4-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a35d4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a35d4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a35d4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a35d4-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a35d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35d4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a35d4-118">See Also</span></span>  
 [<span data-ttu-id="a35d4-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a35d4-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)