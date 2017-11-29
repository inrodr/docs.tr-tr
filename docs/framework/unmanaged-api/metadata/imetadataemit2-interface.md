---
title: IMetaDataEmit2 Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 235134c66395f04a87ed4f3325f5cc4cd9fecfc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="0ec17-102">IMetaDataEmit2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0ec17-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="0ec17-103">Genişletir [Imetadataemit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) öncelikle genel türleri ile çalışma olanağı sağlamak için arabirim.</span><span class="sxs-lookup"><span data-stu-id="0ec17-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ec17-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="0ec17-104">Methods</span></span>  
  
|<span data-ttu-id="0ec17-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="0ec17-105">Method</span></span>|<span data-ttu-id="0ec17-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0ec17-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ec17-107">DefineGenericParam yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="0ec17-108">Genel tür parametresi için bir tanım oluşturur ve o genel tür parametresi için bir belirteç alır.</span><span class="sxs-lookup"><span data-stu-id="0ec17-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="0ec17-109">DefineMethodSpec yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="0ec17-110">Bir yöntem genel bir örneğini oluşturur ve tanımı için bir belirteç alır.</span><span class="sxs-lookup"><span data-stu-id="0ec17-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="0ec17-111">GetDeltaSaveSize yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="0ec17-112">Düzenle ve devam et geçerli oturum için değişiklikleri ifade etmek için gerekli verilerin boyutunu fark belirten bir değer alır.</span><span class="sxs-lookup"><span data-stu-id="0ec17-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="0ec17-113">ResetENCLog yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="0ec17-114">Düzenle ve devam et günlük sıfırlar ve yeni bir oturum başlatır.</span><span class="sxs-lookup"><span data-stu-id="0ec17-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="0ec17-115">SaveDelta yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="0ec17-116">Değişiklikleri geçerli Düzenle ve devam et oturumundan belirtilen dosyaya kaydeder.</span><span class="sxs-lookup"><span data-stu-id="0ec17-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="0ec17-117">SaveDeltaToMemory yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="0ec17-118">Değişiklikleri geçerli Düzenle ve devam et oturumundan belleğe kaydeder.</span><span class="sxs-lookup"><span data-stu-id="0ec17-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="0ec17-119">SaveDeltaToStream yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="0ec17-120">Değişiklikleri geçerli Düzenle ve devam et oturumundan belirtilen akışa kaydeder.</span><span class="sxs-lookup"><span data-stu-id="0ec17-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="0ec17-121">SetGenericParamProps yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ec17-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="0ec17-122">Belirtilen belirteç tarafından başvurulan genel parametresini tanımı için özellik değerlerini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="0ec17-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ec17-123">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0ec17-123">Requirements</span></span>  
 <span data-ttu-id="0ec17-124">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ec17-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec17-125">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ec17-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ec17-126">**Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır</span><span class="sxs-lookup"><span data-stu-id="0ec17-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ec17-127">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec17-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec17-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0ec17-128">See Also</span></span>  
 [<span data-ttu-id="0ec17-129">Meta veri arabirimleri</span><span class="sxs-lookup"><span data-stu-id="0ec17-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="0ec17-130">Imetadataemit arabirimi</span><span class="sxs-lookup"><span data-stu-id="0ec17-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)