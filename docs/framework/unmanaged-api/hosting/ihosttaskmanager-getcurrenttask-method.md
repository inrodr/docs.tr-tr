---
title: IHostTaskManager::GetCurrentTask Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.GetCurrentTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92b4ed0cd33d2e9d3399e409d2dba4eeb14a2f5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="f314c-102">IHostTaskManager::GetCurrentTask Metodu</span><span class="sxs-lookup"><span data-stu-id="f314c-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="f314c-103">Bu çağrı yapılır işletim sistemi iş parçacığı üzerinde şu anda yürütülmekte görev için bir arabirim işaretçisi alır.</span><span class="sxs-lookup"><span data-stu-id="f314c-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f314c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f314c-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f314c-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f314c-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="f314c-106">[out] Adresine bir işaretçi bir [Ihosttask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) hiçbir görev şu anda yürütülmekte, şu anda yürütülen görev veya null, temsil eden örneği.</span><span class="sxs-lookup"><span data-stu-id="f314c-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f314c-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="f314c-107">Return Value</span></span>  
  
|<span data-ttu-id="f314c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f314c-108">HRESULT</span></span>|<span data-ttu-id="f314c-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f314c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f314c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f314c-110">S_OK</span></span>|<span data-ttu-id="f314c-111">`GetCurrentTask`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="f314c-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="f314c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f314c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f314c-113">Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="f314c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f314c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f314c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f314c-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="f314c-115">The call timed out.</span></span>|  
|<span data-ttu-id="f314c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f314c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f314c-117">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="f314c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f314c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f314c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f314c-119">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="f314c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f314c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f314c-120">E_FAIL</span></span>|<span data-ttu-id="f314c-121">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="f314c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f314c-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="f314c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f314c-123">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="f314c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f314c-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="f314c-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="f314c-125">`GetCurrentTask`ana bilgisayar denetimi dışında kalan bir işletim sistemi parçacığında çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="f314c-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f314c-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f314c-126">Remarks</span></span>  
 <span data-ttu-id="f314c-127">Ana bilgisayar de ayarlayabilirsiniz `pTask` parametresi olmayan başlatmak bir görev CLR girmesini engellemek için null.</span><span class="sxs-lookup"><span data-stu-id="f314c-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f314c-128">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f314c-128">Requirements</span></span>  
 <span data-ttu-id="f314c-129">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f314c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f314c-130">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f314c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f314c-131">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="f314c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f314c-132">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f314c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f314c-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f314c-133">See Also</span></span>  
 [<span data-ttu-id="f314c-134">Iclrtask arabirimi</span><span class="sxs-lookup"><span data-stu-id="f314c-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f314c-135">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="f314c-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f314c-136">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="f314c-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f314c-137">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="f314c-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)