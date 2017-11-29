---
title: GetALinkMessageDll-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetALinkMessageDll
api_location: alink.dll
api_type: DLLExport
f1_keywords: GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e87fe5b49a7d939a350d5d0bcb31f79eaaf333c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="23d4f-102">GetALinkMessageDll-Funktion</span><span class="sxs-lookup"><span data-stu-id="23d4f-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="23d4f-103">Sucht und lädt die DLL-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="23d4f-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="23d4f-104">Gibt 0 zurück, wenn die Nachricht DLL nicht gefunden oder geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="23d4f-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="23d4f-105">Die Nachricht DLL muss in einem Unterverzeichnis, deren Name eine Sprachen-ID ist, oder im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="23d4f-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d4f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="23d4f-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="23d4f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23d4f-107">Requirements</span></span>  
 <span data-ttu-id="23d4f-108">**Header:** alink.h</span><span class="sxs-lookup"><span data-stu-id="23d4f-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="23d4f-109">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="23d4f-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d4f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23d4f-110">See Also</span></span>  
 [<span data-ttu-id="23d4f-111">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="23d4f-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)