---
title: "AssemblyFlags Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91760b6d16b663257bf3d89915da3bd88b3411bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="f249a-102">AssemblyFlags Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="f249a-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="f249a-103">Çalışma zamanı bütünleştirilmiş özelliklerini açıklayan değerlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="f249a-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f249a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f249a-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f249a-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="f249a-105">Members</span></span>  
  
|<span data-ttu-id="f249a-106">Üye</span><span class="sxs-lookup"><span data-stu-id="f249a-106">Member</span></span>|<span data-ttu-id="f249a-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f249a-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="f249a-108">Dışarı aktarılan tür tanımları derleme oluşturan dosyaların içinde örtük olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="f249a-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="f249a-109">.NET Framework sürüm 1.0 ve 1.1, bu değer her zaman için ayarlanacak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="f249a-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="f249a-110">Kaynak tanımları derleme oluşturan dosyaların içinde örtük olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="f249a-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="f249a-111">.NET Framework 1.0 ve 1.1, bu değer her zaman için ayarlanacak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="f249a-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="f249a-112">Aynı uygulama etki alanında çalıştırıyorsanız derleme diğer sürümleriyle yürütülemiyor belirtir.</span><span class="sxs-lookup"><span data-stu-id="f249a-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="f249a-113">Aynı işlem içinde çalıştırıyorsanız derleme diğer sürümleriyle yürütülemiyor belirtir.</span><span class="sxs-lookup"><span data-stu-id="f249a-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="f249a-114">Aynı bilgisayar üzerinde çalıştırıyorsanız, derleme diğer sürümleriyle yürütülemiyor belirtir.</span><span class="sxs-lookup"><span data-stu-id="f249a-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f249a-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f249a-115">Remarks</span></span>  
 <span data-ttu-id="f249a-116">0x0010 ve 0x0070 (dahil) arasında değerler başvurulan derlemeyi yan yana uyumluluk özelliklerini tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f249a-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="f249a-117">Bu değerlerin hiçbiri ayarlanmazsa derleme yan yana uyumlu olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="f249a-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f249a-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f249a-118">Requirements</span></span>  
 <span data-ttu-id="f249a-119">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f249a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f249a-120">**Başlık:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f249a-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="f249a-121">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="f249a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f249a-122">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f249a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f249a-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f249a-123">See Also</span></span>  
 [<span data-ttu-id="f249a-124">Meta veri numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="f249a-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="f249a-125">Imetadataassemblyemit arabirimi</span><span class="sxs-lookup"><span data-stu-id="f249a-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)