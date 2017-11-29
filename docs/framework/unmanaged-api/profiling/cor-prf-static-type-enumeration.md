---
title: "COR_PRF_STATIC_TYPE Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_STATIC_TYPE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_STATIC_TYPE
helpviewer_keywords: COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 446967cc157962a1ec4a87193bbf84b1a356efa6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="4cd12-102">COR_PRF_STATIC_TYPE Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="4cd12-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="4cd12-103">Bir statik alandır ve varsa, statik kalite, alan için geçerli olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="4cd12-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="4cd12-104">Bu değerler, alanın birden fazla olduğunu belirtmek için bit düzeyinde OR işlemi kullanılarak birleştirilebilir farklı statik nitelikleri.</span><span class="sxs-lookup"><span data-stu-id="4cd12-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd12-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4cd12-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="4cd12-106">Üyeler</span><span class="sxs-lookup"><span data-stu-id="4cd12-106">Members</span></span>  
  
|<span data-ttu-id="4cd12-107">Üye</span><span class="sxs-lookup"><span data-stu-id="4cd12-107">Member</span></span>|<span data-ttu-id="4cd12-108">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4cd12-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="4cd12-109">Alanı statik değil.</span><span class="sxs-lookup"><span data-stu-id="4cd12-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="4cd12-110">Uygulama etki alanı statik alandır.</span><span class="sxs-lookup"><span data-stu-id="4cd12-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="4cd12-111">İş parçacığı statik alandır.</span><span class="sxs-lookup"><span data-stu-id="4cd12-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="4cd12-112">Bağlam statik alandır.</span><span class="sxs-lookup"><span data-stu-id="4cd12-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="4cd12-113">Göreli sanal adres (RVA) alanıdır-statik.</span><span class="sxs-lookup"><span data-stu-id="4cd12-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cd12-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4cd12-114">Requirements</span></span>  
 <span data-ttu-id="4cd12-115">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cd12-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd12-116">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cd12-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cd12-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cd12-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cd12-118">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd12-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd12-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4cd12-119">See Also</span></span>  
 [<span data-ttu-id="4cd12-120">Profil oluşturma numaralandırmaları</span><span class="sxs-lookup"><span data-stu-id="4cd12-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)