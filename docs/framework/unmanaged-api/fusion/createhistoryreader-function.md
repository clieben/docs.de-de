---
title: CreateHistoryReader-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="0ec8f-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="0ec8f-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="0ec8f-103">Erstellt einen Leser Verlauf für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="0ec8f-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ec8f-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ec8f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ec8f-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="0ec8f-106">[in] Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="0ec8f-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="0ec8f-107">[out] Bei erfolgreichem Abschluss können Sie einen Zeiger auf den Verlaufsreader enthält.</span><span class="sxs-lookup"><span data-stu-id="0ec8f-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ec8f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ec8f-108">Return Value</span></span>  
 <span data-ttu-id="0ec8f-109">Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert, zusätzlich zu den Werten in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ec8f-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="0ec8f-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="0ec8f-110">Return code</span></span>|<span data-ttu-id="0ec8f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ec8f-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0ec8f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ec8f-112">S_OK</span></span>|<span data-ttu-id="0ec8f-113">Gibt an, dass die Methode erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ec8f-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="0ec8f-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0ec8f-114">E_INVALIDARG</span></span>|<span data-ttu-id="0ec8f-115">Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf ein null-Verweis festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0ec8f-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ec8f-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ec8f-116">Requirements</span></span>  
 <span data-ttu-id="0ec8f-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ec8f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec8f-118">**Bibliothek:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="0ec8f-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="0ec8f-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec8f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec8f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ec8f-120">See Also</span></span>  
 [<span data-ttu-id="0ec8f-121">Globale statische Fusionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="0ec8f-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)