---
title: IMetaDataImport::GetRVA Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f64cc5b0aa6043c5408868a5a6bf23e24278ea26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="41664-102">IMetaDataImport::GetRVA Metodu</span><span class="sxs-lookup"><span data-stu-id="41664-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="41664-103">Göreli sanal adres (RAV) ve yöntem veya belirtilen belirtecin tarafından temsil edilen alan uygulama bayraklarını alır.</span><span class="sxs-lookup"><span data-stu-id="41664-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41664-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="41664-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41664-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="41664-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="41664-106">[in] İçin RVA dönmek için kod nesnesini temsil eden bir MethodDef veya fieldDef simgesi meta veri simgesi.</span><span class="sxs-lookup"><span data-stu-id="41664-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="41664-107">Belirtecin bir fieldDef simgesi ise, alan genel değişkeni olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="41664-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="41664-108">[out] Belirtecin tarafından temsil edilen kod nesne göreli sanal adresini gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="41664-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="41664-109">[out] Uygulama bayrakları yöntemi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="41664-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="41664-110">Bu değer gelen bir bit maskesi olan [Cormethodımpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="41664-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="41664-111">Değeri `pdwImplFlags` geçerli yalnızca `tk` MethodDef belirteci.</span><span class="sxs-lookup"><span data-stu-id="41664-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41664-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="41664-112">Requirements</span></span>  
 <span data-ttu-id="41664-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41664-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41664-114">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41664-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41664-115">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="41664-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41664-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41664-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41664-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="41664-117">See Also</span></span>  
 [<span data-ttu-id="41664-118">Imetadataımport arabirimi</span><span class="sxs-lookup"><span data-stu-id="41664-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="41664-119">Imetadataımport2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="41664-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)