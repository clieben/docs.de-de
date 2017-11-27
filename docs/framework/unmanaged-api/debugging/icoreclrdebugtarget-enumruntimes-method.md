---
title: ICoreClrDebugTarget::EnumRuntimes-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumRuntimes
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d28e5f3f529f72607e2ddd84789e89f82dcdaba0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="c90e7-102">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="c90e7-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="c90e7-103">Listet die CLR-Laufzeiten (Common Language Runtime) im angegebenen Prozess auf, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c90e7-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c90e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c90e7-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c90e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c90e7-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="c90e7-106">[in] Die interne Prozess-ID des Prozesses, für den Laufzeiten aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c90e7-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="c90e7-107">Dadurch werden `m_dwInternalID` aus der entsprechenden [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="c90e7-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="c90e7-108">[out] Die Anzahl der in `ppRuntimes` zurückgegebenen Laufzeiten.</span><span class="sxs-lookup"><span data-stu-id="c90e7-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="c90e7-109">Dieser Wert kann 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c90e7-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="c90e7-110">[out] Ein Array von [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) Strukturen, die die Laufzeiten darstellen, die in der remote-Zielprozess geladen.</span><span class="sxs-lookup"><span data-stu-id="c90e7-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c90e7-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c90e7-111">Return Value</span></span>  
 <span data-ttu-id="c90e7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c90e7-112">S_OK</span></span>  
 <span data-ttu-id="c90e7-113">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c90e7-113">Success.</span></span>  
  
 <span data-ttu-id="c90e7-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c90e7-114">S_FALSE</span></span>  
 <span data-ttu-id="c90e7-115">`dwInternalProcessID` entspricht keinem auf dem Computer ausgeführten Prozess; wahrscheinlich wurde der Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="c90e7-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="c90e7-116">`pcRuntimes` und `ppRuntimes` sind null.</span><span class="sxs-lookup"><span data-stu-id="c90e7-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="c90e7-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c90e7-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c90e7-118">Für `ppRuntimes` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c90e7-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="c90e7-119">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="c90e7-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c90e7-120">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="c90e7-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c90e7-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c90e7-121">Remarks</span></span>  
 <span data-ttu-id="c90e7-122">Um den Arbeitsspeicher freizugeben, der von dieser Methode belegt wurde, rufen Sie die [ICoreClrDebugTarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c90e7-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c90e7-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c90e7-123">Requirements</span></span>  
 <span data-ttu-id="c90e7-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c90e7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c90e7-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c90e7-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c90e7-126">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c90e7-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c90e7-127">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c90e7-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90e7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c90e7-128">See Also</span></span>  
 [<span data-ttu-id="c90e7-129">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c90e7-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)