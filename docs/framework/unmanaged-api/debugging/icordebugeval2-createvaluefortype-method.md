---
title: ICorDebugEval2::CreateValueForType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CreateValueForType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cc2760b1c303141372aed824bda71ebdae8ffe0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="4632b-102">ICorDebugEval2::CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="4632b-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="4632b-103">Ruft einen Zeiger auf einen neuen ICorDebugValue des angegebenen Typs mit einem Anfangswert von 0 (null) oder Null.</span><span class="sxs-lookup"><span data-stu-id="4632b-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4632b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4632b-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4632b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4632b-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="4632b-106">[in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="4632b-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4632b-107">[out] Zeiger auf die Adresse von einem `ICorDebugValue` -Objekt, das den Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="4632b-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4632b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4632b-108">Remarks</span></span>  
 <span data-ttu-id="4632b-109">`CreateValueForType`verallgemeinert [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) ermöglichen Ihnen die Angabe ein beliebigen Objekttyps, einschließlich Typen konstruiert z. B. `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="4632b-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="4632b-110">Der einzige Zweck dieser Methode wird zum Generieren eines Werts, das an eine funktionsauswertung übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="4632b-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="4632b-111">Der Typ muss eine Klasse oder ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="4632b-111">The type must be a class or a value type.</span></span> <span data-ttu-id="4632b-112">Diese Methode kann nicht verwendet werden, um Arraywerte oder Zeichenfolgenwerte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4632b-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4632b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4632b-113">Requirements</span></span>  
 <span data-ttu-id="4632b-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4632b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4632b-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4632b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4632b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4632b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4632b-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4632b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>