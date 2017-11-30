---
title: "ICLRTask::NeedsPriorityScheduling Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.NeedsPriorityScheduling
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 46da785535bef3443a1b917a5fb997e8e6ef3fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="53e6b-102">ICLRTask::NeedsPriorityScheduling Yöntemi</span><span class="sxs-lookup"><span data-stu-id="53e6b-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="53e6b-103">Out anahtarlanır, geçerli görev kullanılabilirliğiyle için yüksek öncelikli olarak işaretlenmiş gerekip gerekmediğini belirten bir değer alır.</span><span class="sxs-lookup"><span data-stu-id="53e6b-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e6b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="53e6b-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53e6b-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="53e6b-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="53e6b-106">[out] `true`, mümkün olan en kısa sürede; Aksi takdirde, geçerli görev örneği yeniden zamanlamak konak denemelidir `false`.</span><span class="sxs-lookup"><span data-stu-id="53e6b-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53e6b-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="53e6b-107">Return Value</span></span>  
  
|<span data-ttu-id="53e6b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53e6b-108">HRESULT</span></span>|<span data-ttu-id="53e6b-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="53e6b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53e6b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53e6b-110">S_OK</span></span>|<span data-ttu-id="53e6b-111">`NeedsPriorityRescheduling`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="53e6b-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="53e6b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53e6b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53e6b-113">Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="53e6b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53e6b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53e6b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53e6b-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="53e6b-115">The call timed out.</span></span>|  
|<span data-ttu-id="53e6b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53e6b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53e6b-117">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="53e6b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53e6b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53e6b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53e6b-119">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="53e6b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53e6b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53e6b-120">E_FAIL</span></span>|<span data-ttu-id="53e6b-121">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="53e6b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53e6b-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="53e6b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53e6b-123">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="53e6b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53e6b-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="53e6b-124">Remarks</span></span>  
 <span data-ttu-id="53e6b-125">Görev olduğu atık toplayıcısı tarafından toplanan yakın durumlarda, CLR değerini ayarlar `pbNeedsPriorityScheduling` için `true`, yüksek öncelikli kullanılabilirliğiyle belirten.</span><span class="sxs-lookup"><span data-stu-id="53e6b-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="53e6b-126">Bu görev hızla yeniden zamanlamak için ana böylece çöp toplama gecikme olasılığını en aza indirmenizi ve ana bilgisayar ve çalışma zamanı bellek kaynakların tasarrufu için işbirliği etkinleştirme sağlar.</span><span class="sxs-lookup"><span data-stu-id="53e6b-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53e6b-127">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="53e6b-127">Requirements</span></span>  
 <span data-ttu-id="53e6b-128">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53e6b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e6b-129">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53e6b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53e6b-130">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="53e6b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53e6b-131">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e6b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e6b-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="53e6b-132">See Also</span></span>  
 [<span data-ttu-id="53e6b-133">Iclrtask arabirimi</span><span class="sxs-lookup"><span data-stu-id="53e6b-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="53e6b-134">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="53e6b-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="53e6b-135">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="53e6b-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="53e6b-136">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="53e6b-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)