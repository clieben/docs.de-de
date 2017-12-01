---
title: ICorPublishEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum
helpviewer_keywords: ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7034945824e439b42134f8ea3c13bfaf73dbb649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="af30e-102">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af30e-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="af30e-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die die Veröffentlichung von Informationen über Prozesse und Anwendungsdomänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af30e-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af30e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="af30e-104">Methods</span></span>  
  
|<span data-ttu-id="af30e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="af30e-105">Method</span></span>|<span data-ttu-id="af30e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af30e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af30e-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="af30e-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="af30e-108">Erstellt eine Kopie dieser `ICorPublishEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="af30e-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="af30e-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="af30e-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="af30e-110">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="af30e-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="af30e-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="af30e-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="af30e-112">Verschiebt den Cursor auf den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="af30e-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="af30e-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="af30e-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="af30e-114">Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="af30e-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af30e-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af30e-115">Remarks</span></span>  
 <span data-ttu-id="af30e-116">Die folgenden Enumeratoren leiten sich von `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="af30e-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="af30e-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="af30e-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="af30e-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="af30e-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="af30e-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af30e-119">Requirements</span></span>  
 <span data-ttu-id="af30e-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af30e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af30e-121">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="af30e-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="af30e-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af30e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af30e-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af30e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af30e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af30e-124">See Also</span></span>  
 [<span data-ttu-id="af30e-125">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="af30e-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [<span data-ttu-id="af30e-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="af30e-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)