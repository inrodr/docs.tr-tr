---
title: "ICorProfilerFunctionControl::SetILFunctionBody Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9469435186a5aef130ca4ebef27a4613afeb921c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="3fc12-102">ICorProfilerFunctionControl::SetILFunctionBody Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3fc12-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="3fc12-103">Ortak Ara Dili (CIL) yönteminin gövdesinin yerini alır.</span><span class="sxs-lookup"><span data-stu-id="3fc12-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc12-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3fc12-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fc12-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3fc12-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="3fc12-106">[in] Üstbilgi ve gövdeden sonra gelen yapılar da dahil olmak üzere yeni CIL'in toplam boyutu.</span><span class="sxs-lookup"><span data-stu-id="3fc12-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="3fc12-107">[in] Yeni CIL üstbilgisi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="3fc12-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fc12-108">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="3fc12-108">Return Value</span></span>  
 <span data-ttu-id="3fc12-109">Bu yöntem aşağıdaki özel HRESULT'ları döndürür.</span><span class="sxs-lookup"><span data-stu-id="3fc12-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="3fc12-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fc12-110">HRESULT</span></span>|<span data-ttu-id="3fc12-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3fc12-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fc12-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fc12-112">S_OK</span></span>|<span data-ttu-id="3fc12-113">Değişiklik başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="3fc12-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fc12-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3fc12-114">Remarks</span></span>  
 <span data-ttu-id="3fc12-115">Farklı [Icorprofilerınfo::setılfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) yöntemi, `SetILFunctionBody` yöntemi yeni CIL gövdesi için gerekli bellek yönetir.</span><span class="sxs-lookup"><span data-stu-id="3fc12-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="3fc12-116">Bu profil oluşturucu tarafından sağlanan CIL gövde kullanarak ayrılacak yok anlamına gelir [Imethodmalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) arabirim veya belirli bir aralık içinde ayrılmış.</span><span class="sxs-lookup"><span data-stu-id="3fc12-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="3fc12-117">Herhangi bir yığında ayrılabilir.</span><span class="sxs-lookup"><span data-stu-id="3fc12-117">It can be allocated on any heap.</span></span> <span data-ttu-id="3fc12-118">Profil Oluşturucu sonra onun CIL gövdesi için kullanılan bellek boşaltabilirsiniz `SetILFunctionBody` döndürür.</span><span class="sxs-lookup"><span data-stu-id="3fc12-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc12-119">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3fc12-119">Requirements</span></span>  
 <span data-ttu-id="3fc12-120">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fc12-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc12-121">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3fc12-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3fc12-122">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fc12-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fc12-123">**.NET framework sürümleri:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc12-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc12-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3fc12-124">See Also</span></span>  
 [<span data-ttu-id="3fc12-125">Icorprofilerfunctioncontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="3fc12-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)