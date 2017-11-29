---
title: GetPropertyHandle-Funktion (Referenz zur nicht verwalteten API)
description: "Die GetPropertyHandle-Funktion gibt einem eindeutige Handle dieser Identitäten eine Eigenschaft an."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="8741a-103">GetPropertyHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="8741a-103">GetPropertyHandle function</span></span>
<span data-ttu-id="8741a-104">Gibt ein eindeutige-Handle, das eine Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8741a-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8741a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8741a-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="8741a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8741a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8741a-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8741a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8741a-108">[in] Ein Zeiger auf ein [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="8741a-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="8741a-109">[in] Eine Null-terminierte Zeichenfolge des UTF16-codierte Zeichen enthalten, die den Namen der Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="8741a-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="8741a-110">[out] Ein Zeiger auf eine [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) Enumerationselement, das den CIM-Typ der Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="8741a-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="8741a-111">[out] Ein Zeiger auf eine ganze Zahl, die das Eigenschaftshandle enthält.</span><span class="sxs-lookup"><span data-stu-id="8741a-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="8741a-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8741a-112">Return value</span></span>

<span data-ttu-id="8741a-113">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="8741a-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8741a-114">Konstante</span><span class="sxs-lookup"><span data-stu-id="8741a-114">Constant</span></span>  |<span data-ttu-id="8741a-115">Wert</span><span class="sxs-lookup"><span data-stu-id="8741a-115">Value</span></span>  |<span data-ttu-id="8741a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8741a-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8741a-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8741a-117">0x80041002</span></span> | <span data-ttu-id="8741a-118">Der angegebene Eigenschaftenname wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8741a-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8741a-119">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="8741a-119">0x80041008</span></span> | <span data-ttu-id="8741a-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8741a-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="8741a-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="8741a-121">0x8004100c</span></span> | <span data-ttu-id="8741a-122">Die angeforderte Eigenschaft befindet sich der Typ werden `CIM_OBJECT` oder `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="8741a-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8741a-123">0</span><span class="sxs-lookup"><span data-stu-id="8741a-123">0</span></span> | <span data-ttu-id="8741a-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8741a-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8741a-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8741a-125">Remarks</span></span>

<span data-ttu-id="8741a-126">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="8741a-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="8741a-127">Verwenden Sie dieses Handle zum Identifizieren von Eigenschaften mit [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) Methoden zum Lesen oder schreiben die Eigenschaftswerte.</span><span class="sxs-lookup"><span data-stu-id="8741a-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="8741a-128">Handles können für die Eigenschaften für alle Datentypen außer abgerufen werden `CIM_OBJECT` und `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="8741a-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="8741a-129">Handles Arbeit, die über alle Instanzen einer Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8741a-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="8741a-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8741a-130">Requirements</span></span>  
<span data-ttu-id="8741a-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8741a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8741a-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8741a-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8741a-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8741a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8741a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8741a-134">See also</span></span>  
[<span data-ttu-id="8741a-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8741a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)