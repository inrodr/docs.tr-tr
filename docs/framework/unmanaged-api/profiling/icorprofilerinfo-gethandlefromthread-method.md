---
title: ICorProfilerInfo::GetHandleFromThread Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetHandleFromThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be925bbbcc86785feae28353dbc6563974aae2c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="f1d2d-102">ICorProfilerInfo::GetHandleFromThread Metodu</span><span class="sxs-lookup"><span data-stu-id="f1d2d-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="f1d2d-103">Bir iş parçacığı kimliği için Win32 iş parçacığı tanıtıcı eşler.</span><span class="sxs-lookup"><span data-stu-id="f1d2d-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d2d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f1d2d-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1d2d-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f1d2d-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f1d2d-106">[in] Eşlenecek iş parçacığı kimliği.</span><span class="sxs-lookup"><span data-stu-id="f1d2d-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="f1d2d-107">[out] Win32 iş parçacığı işleyicisi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="f1d2d-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d2d-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f1d2d-108">Remarks</span></span>  
 <span data-ttu-id="f1d2d-109">Profil Oluşturucu Win32 çağırmalısınız `DuplicateHandle` kullanmadan önce tutamacı işlevi.</span><span class="sxs-lookup"><span data-stu-id="f1d2d-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d2d-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f1d2d-110">Requirements</span></span>  
 <span data-ttu-id="f1d2d-111">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d2d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d2d-112">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1d2d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1d2d-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1d2d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1d2d-114">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d2d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d2d-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f1d2d-115">See Also</span></span>  
 [<span data-ttu-id="f1d2d-116">Icorprofilerınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="f1d2d-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)