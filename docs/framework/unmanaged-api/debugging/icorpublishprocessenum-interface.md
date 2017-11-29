---
title: ICorPublishProcessEnum Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum
helpviewer_keywords: ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66e31911289d1ef8b590a0b7e7896adfa4998adc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="272ec-102">ICorPublishProcessEnum Arabirimi</span><span class="sxs-lookup"><span data-stu-id="272ec-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="272ec-103">Öğesinin bir alt [Icorpublishenum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) koleksiyonu geçiş için yöntemler sağlar arabirimi [Icorpublishprocess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) nesneleri.</span><span class="sxs-lookup"><span data-stu-id="272ec-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="272ec-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="272ec-104">Methods</span></span>  
  
|<span data-ttu-id="272ec-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="272ec-105">Method</span></span>|<span data-ttu-id="272ec-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="272ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="272ec-107">Next yöntemi</span><span class="sxs-lookup"><span data-stu-id="272ec-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="272ec-108">Belirtilen sayıda alır `ICorPublishProcess` geçerli konumdan başlayarak koleksiyondan örnekleri.</span><span class="sxs-lookup"><span data-stu-id="272ec-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="272ec-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="272ec-109">Remarks</span></span>  
 <span data-ttu-id="272ec-110">`ICorPublishProcessEnum` Arabirimini uygulayan soyut arabiriminin yöntemlerini [Icorpublishenum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="272ec-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="272ec-111">Bir `ICorPublishProcessEnum` örneği tarafından oluşturulan [Icorpublish::enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="272ec-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="272ec-112">Geçişi koleksiyonunun `ICorPublishProcess` nesneleri aynı anda verilen filtre ölçütünü temel `ICorPublishProcessEnum` örneği oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="272ec-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="272ec-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="272ec-113">Requirements</span></span>  
 <span data-ttu-id="272ec-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="272ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="272ec-115">**Başlık:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="272ec-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="272ec-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="272ec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="272ec-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="272ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272ec-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="272ec-118">See Also</span></span>  
 [<span data-ttu-id="272ec-119">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="272ec-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="272ec-120">Corpubpublish ortak sınıfı</span><span class="sxs-lookup"><span data-stu-id="272ec-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)