---
title: "_CorValidateImage İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorValidateImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorValidateImage
helpviewer_keywords: _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e2396219a5e4bfd95a9dc7134e2e603ed7a15a3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="ed5ad-102">_CorValidateImage İşlevi</span><span class="sxs-lookup"><span data-stu-id="ed5ad-102">_CorValidateImage Function</span></span>
<span data-ttu-id="ed5ad-103">Yönetilen modül görüntüleri doğrular ve bunlar yüklendikten sonra işletim sistemi yükleyicisi bildirir.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5ad-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ed5ad-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed5ad-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="ed5ad-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="ed5ad-106">[in] Yönetilen kod bir işaretçi olarak doğrulamak için görüntüsünün başlangıç konumu.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="ed5ad-107">Görüntü zaten belleğe yüklenmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="ed5ad-108">[in] Yansıma Dosya adı.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed5ad-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="ed5ad-109">Return Value</span></span>  
 <span data-ttu-id="ed5ad-110">Bu işlev, standart değerleri döndürür `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, ve `E_FAIL`, aşağıdaki değerleri yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="ed5ad-111">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="ed5ad-111">Return value</span></span>|<span data-ttu-id="ed5ad-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ed5ad-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="ed5ad-113">Görüntüsü geçersiz.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-113">The image is invalid.</span></span> <span data-ttu-id="ed5ad-114">Bu değer HRESULT 0xC000007BL sahiptir.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="ed5ad-115">Görüntü geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-115">The image is valid.</span></span> <span data-ttu-id="ed5ad-116">Bu değer HRESULT 0x00000000L sahiptir.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed5ad-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ed5ad-117">Remarks</span></span>  
 <span data-ttu-id="ed5ad-118">Windows XP ve sonraki sürümlerinde, işletim sistemi yükleyicisi ortak nesne dosya biçimi (COFF) üstbilgisinde COM tanımlayıcısı dizin bit inceleyerek yönetilen modülleri için denetler.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="ed5ad-119">Yönetilen bir modül kümesini bit gösterir.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="ed5ad-120">Yükleyici yönetilen bir modül algılarsa, MsCorEE.dll ve çağrıları yüklerken `_CorValidateImage`, aşağıdaki eylemleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="ed5ad-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="ed5ad-121">Görüntü geçerli bir yönetilen modül olduğunu doğrular.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="ed5ad-122">Ortak dil çalışma zamanı (CLR) bir giriş noktası için giriş noktası görüntüdeki değiştirir.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="ed5ad-123">Windows'un 64 bit sürümleri için PE32 PE32 + biçimine dönüştürerek bellekte görüntüsü değiştirir.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="ed5ad-124">Yönetilen modül görüntüleri yüklendiğinde yükleyicisi geri döner.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="ed5ad-125">Yürütülebilir görüntüler, işletim sistemi yükleyicisi sonra çağırır [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) işlevi, bağımsız olarak yürütülebilir dosya belirtilen giriş noktası.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="ed5ad-126">DLL derleme görüntülerde yükleyicisi çağırır [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="ed5ad-127">`_CorExeMain`veya `_CorDllMain` aşağıdaki eylemleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="ed5ad-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="ed5ad-128">CLR başlatır.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="ed5ad-129">Derlemenin CLR başlığından yönetilen giriş noktası bulur.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="ed5ad-130">Yürütme başlar.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-130">Begins execution.</span></span>  
  
 <span data-ttu-id="ed5ad-131">Yükleyici çağrıları [_corımageunloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) işlev yönetildiğinde modülü görüntüleri kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="ed5ad-132">Ancak, bu işlev, herhangi bir işlem gerçekleştirmez; yalnızca döndürür.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed5ad-133">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ed5ad-133">Requirements</span></span>  
 <span data-ttu-id="ed5ad-134">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed5ad-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed5ad-135">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ed5ad-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed5ad-136">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="ed5ad-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed5ad-137">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed5ad-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5ad-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-138">See Also</span></span>  
 [<span data-ttu-id="ed5ad-139">Meta veri genel statik işlevleri</span><span class="sxs-lookup"><span data-stu-id="ed5ad-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)