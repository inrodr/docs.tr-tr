---
title: "IMetaDataImport::EnumPermissionSets Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 031e97ad1b8180a64bc789ae52e141932d600782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="b44c2-102">IMetaDataImport::EnumPermissionSets Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b44c2-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="b44c2-103">Belirtilen meta veri kapsamı içindeki nesneler için izinleri numaralandırır.</span><span class="sxs-lookup"><span data-stu-id="b44c2-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44c2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b44c2-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b44c2-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b44c2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b44c2-106">[içinde out] Numaralayıcı gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="b44c2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b44c2-107">Bu, bu yöntem ilk çağrısı için NULL olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b44c2-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="b44c2-108">[in] Arama veya olası en geniş kapsamında arama yapmak için NULL kapsamını sınırlayan bir meta veri simgesi.</span><span class="sxs-lookup"><span data-stu-id="b44c2-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="b44c2-109">[in] Flags temsil eden <xref:System.Security.Permissions.SecurityAction> dahil edilecek değerleri `rPermission`, ya da tüm eylemler döndürmek için sıfır.</span><span class="sxs-lookup"><span data-stu-id="b44c2-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="b44c2-110">[out] İzni belirteçleri depolamak için kullanılan dizisi.</span><span class="sxs-lookup"><span data-stu-id="b44c2-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b44c2-111">[in] En büyük boyutunu `rPermission` dizi.</span><span class="sxs-lookup"><span data-stu-id="b44c2-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b44c2-112">[out] Döndürülen izni belirteçleri sayısı `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="b44c2-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b44c2-113">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="b44c2-113">Return Value</span></span>  
  
|<span data-ttu-id="b44c2-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b44c2-114">HRESULT</span></span>|<span data-ttu-id="b44c2-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b44c2-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b44c2-116">`EnumPermissionSets`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="b44c2-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b44c2-117">Numaralandırılacak hiçbir belirteçleri vardır.</span><span class="sxs-lookup"><span data-stu-id="b44c2-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="b44c2-118">Bu durumda, `pcTokens` sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="b44c2-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b44c2-119">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b44c2-119">Requirements</span></span>  
 <span data-ttu-id="b44c2-120">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b44c2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b44c2-121">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b44c2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b44c2-122">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="b44c2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b44c2-123">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b44c2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b44c2-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b44c2-124">See Also</span></span>  
 [<span data-ttu-id="b44c2-125">Imetadataımport arabirimi</span><span class="sxs-lookup"><span data-stu-id="b44c2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b44c2-126">Imetadataımport2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="b44c2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)