---
title: CorNotificationForTokenMovement-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNotificationForTokenMovement
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNotificationForTokenMovement
helpviewer_keywords: CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60d6c56394952fca84b45ba042f7d45a1dec6b1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="138ae-102">CorNotificationForTokenMovement-Enumeration</span><span class="sxs-lookup"><span data-stu-id="138ae-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="138ae-103">Gibt an, die Benachrichtigungen, die an den Metadaten-API-Client gesendet werden, wenn ein token neuzuordnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="138ae-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="138ae-104">Syntax</span></span>  
  
```  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="138ae-105">Member</span><span class="sxs-lookup"><span data-stu-id="138ae-105">Members</span></span>  
  
|<span data-ttu-id="138ae-106">Member</span><span class="sxs-lookup"><span data-stu-id="138ae-106">Member</span></span>|<span data-ttu-id="138ae-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138ae-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="138ae-108">Benachrichtigen, wenn `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, oder `mdFieldDef` Token verschieben.</span><span class="sxs-lookup"><span data-stu-id="138ae-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="138ae-109">Benachrichtigen Sie, wenn ein beliebiges Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="138ae-110">Nicht benachrichtigen Sie, wenn Token verschieben.</span><span class="sxs-lookup"><span data-stu-id="138ae-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="138ae-111">Benachrichtigen, wenn ein `mdMethodDef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="138ae-112">Benachrichtigen, wenn ein `mdMemberRef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="138ae-113">Benachrichtigen, wenn ein `mdFieldDef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="138ae-114">Benachrichtigen, wenn ein `mdTypeRef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="138ae-115">Benachrichtigen, wenn ein `mdTypeDef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="138ae-116">Benachrichtigen, wenn ein `mdParamDef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="138ae-117">Benachrichtigen, wenn ein `mdInterfaceImpl` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="138ae-118">Benachrichtigen, wenn ein `mdProperty` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="138ae-119">Benachrichtigen, wenn ein `mdEvent` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="138ae-120">Benachrichtigen, wenn ein `mdSignature` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="138ae-121">Benachrichtigen, wenn ein `mdTypeSpec` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="138ae-122">Benachrichtigen, wenn ein `mdCustomAttribute` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="138ae-123">Benachrichtigen, wenn ein `mdSecurityValue` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="138ae-124">Benachrichtigen, wenn ein `mdPermission` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="138ae-125">Benachrichtigen, wenn ein `mdModuleRef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="138ae-126">Benachrichtigen, wenn ein `mdNameSpace` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="138ae-127">Benachrichtigen, wenn ein `mdAssemblyRef` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="138ae-128">Benachrichtigen, wenn ein `mdFile` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="138ae-129">Benachrichtigen, wenn ein `mdExportedType` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="138ae-130">Benachrichtigen, wenn ein `mdManifestResource` -Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="138ae-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="138ae-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="138ae-131">Remarks</span></span>  
 <span data-ttu-id="138ae-132">Ein Token möglicherweise erneut zugeordnet werden (die verschoben) beim Zusammenführen von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="138ae-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="138ae-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="138ae-133">Requirements</span></span>  
 <span data-ttu-id="138ae-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="138ae-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="138ae-135">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="138ae-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="138ae-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="138ae-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138ae-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="138ae-137">See Also</span></span>  
 [<span data-ttu-id="138ae-138">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="138ae-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)