---
title: "ICorProfilerCallback::AppDomainShutdownStarted Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainShutdownStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eff8807b5f50708b8d8e4935052de89f59eb5d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="f6300-102">ICorProfilerCallback::AppDomainShutdownStarted Yöntemi</span><span class="sxs-lookup"><span data-stu-id="f6300-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="f6300-103">Profil Oluşturucu uygulama etki alanı bir işlemden yüklenmemiş olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="f6300-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6300-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f6300-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6300-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f6300-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="f6300-106">[in] Uygulamanın derlemelerini depolandığı etki alanını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="f6300-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6300-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f6300-107">Remarks</span></span>  
 <span data-ttu-id="f6300-108">Değeri `appDomainId` sonra herhangi bir bilgi istek için geçerli değil `AppDomainShutdownStarted` yöntemi döndürür — bu bu uygulama etki alanı hakkında bilgi almak için Profil Oluşturucu'nın son şansınızdır.</span><span class="sxs-lookup"><span data-stu-id="f6300-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6300-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f6300-109">Requirements</span></span>  
 <span data-ttu-id="f6300-110">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6300-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6300-111">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6300-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6300-112">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6300-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6300-113">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6300-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6300-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f6300-114">See Also</span></span>  
 [<span data-ttu-id="f6300-115">Icorprofilercallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="f6300-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)