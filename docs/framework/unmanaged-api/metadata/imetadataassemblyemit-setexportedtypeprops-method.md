---
title: "IMetaDataAssemblyEmit::SetExportedTypeProps Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetExportedTypeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c41cc2c6433139f1e1f355585e4af0a8f01c7c94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="97cd3-102">IMetaDataAssemblyEmit::SetExportedTypeProps Yöntemi</span><span class="sxs-lookup"><span data-stu-id="97cd3-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="97cd3-103">Belirtilen değiştirir `ExportedType` meta veri yapısı.</span><span class="sxs-lookup"><span data-stu-id="97cd3-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97cd3-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="97cd3-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97cd3-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="97cd3-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="97cd3-106">[in] Belirtir meta veri simgesi `ExportedType` değiştirilecek meta veri yapısı.</span><span class="sxs-lookup"><span data-stu-id="97cd3-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="97cd3-107">[in] Türünde belirteç `File`, `AssemblyRef`, veya `ExportedType`, bu tür nasıl uygulandığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="97cd3-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="97cd3-108">[in] `TypeDef` Kod dosyasında başvurulan belirteci.</span><span class="sxs-lookup"><span data-stu-id="97cd3-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="97cd3-109">[in] Türü özniteliklerini belirtmek değerlerin Bitsel bir birleşimi.</span><span class="sxs-lookup"><span data-stu-id="97cd3-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97cd3-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="97cd3-110">Remarks</span></span>  
 <span data-ttu-id="97cd3-111">Oluşturmak için bir `ExportedType` meta veri yapısı, kullanım [Imetadataassemblyemit::defineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="97cd3-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97cd3-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="97cd3-112">Requirements</span></span>  
 <span data-ttu-id="97cd3-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97cd3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97cd3-114">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="97cd3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97cd3-115">**Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır</span><span class="sxs-lookup"><span data-stu-id="97cd3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97cd3-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97cd3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97cd3-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="97cd3-117">See Also</span></span>  
 [<span data-ttu-id="97cd3-118">Imetadataassemblyemit arabirimi</span><span class="sxs-lookup"><span data-stu-id="97cd3-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)