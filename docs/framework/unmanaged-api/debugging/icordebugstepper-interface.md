---
title: ICorDebugStepper Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper
helpviewer_keywords: ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 83d394669270eb26b33e084b20a621e18b5b14aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="a0c3f-102">ICorDebugStepper Interface1</span><span class="sxs-lookup"><span data-stu-id="a0c3f-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="a0c3f-103">Bir hata ayıklayıcının gerçekleştirdiği kod yürütmedeki bir adımı temsil eder, bir komutun çıkarılması ve tamamlanması arasında bir tanımlayıcı görevi görür ve bir adımı iptal etmek için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0c3f-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="a0c3f-104">Methods</span></span>  
  
|<span data-ttu-id="a0c3f-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="a0c3f-105">Method</span></span>|<span data-ttu-id="a0c3f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a0c3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0c3f-107">Deactivate yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="a0c3f-108">Bu neden `ICorDebugStepper` aldığı son adımı komutunu iptal etmek için.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="a0c3f-109">Isactive yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="a0c3f-110">Gösteren bir değer alır olup olmadığını bu `ICorDebugStepper` bir adım gerçekleştirmektedir.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="a0c3f-111">Setınterceptmask yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="a0c3f-112">İçine adım adım kod türlerini belirten bir Cordebugıntercept değeri ayarlar.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="a0c3f-113">Setrangeıl yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="a0c3f-114">Gösteren bir değer ayarlar olup olmadığını çağrılar [ICorDebugStepper::steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) yerel kod göreli veya Microsoft Ara dili (MSIL) koduna üzerinden adım adım yöntemin bağımsız değişken değeri geçirin.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="a0c3f-115">SetUnmappedStopMask yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="a0c3f-116">İçinde yürütme durdurulur eşlenmemiş kod türünü belirten bir CorDebugUnmappedStop değeri ayarlar.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="a0c3f-117">Step yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="a0c3f-118">Bu neden olur `ICorDebugStepper` tek adımlı içeren kendi iş parçacığı aracılığıyla ve isteğe bağlı olarak için için iş parçacığı içinde adlı işlevler üzerinden tek atlama devam edin.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="a0c3f-119">StepOut yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="a0c3f-120">Bu neden `ICorDebugStepper` tek adımlı içeren kendi iş parçacığı aracılığıyla ve tam olduğunda geçerli çerçeve arama çerçeveye denetimini döndürür.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="a0c3f-121">StepRange yöntemi</span><span class="sxs-lookup"><span data-stu-id="a0c3f-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="a0c3f-122">Bu neden `ICorDebugStepper` isteğe bağlı olarak tek adımlı için içeren kendi iş parçacığı aracılığıyla ve ne zaman döndürmek için son belirtilen aralıkların dışında kod ulaşır.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0c3f-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a0c3f-123">Remarks</span></span>  
 <span data-ttu-id="a0c3f-124">`ICorDebugStepper` Arabirimi aşağıdaki amaçlara hizmet eder:</span><span class="sxs-lookup"><span data-stu-id="a0c3f-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="a0c3f-125">Verilen bir adım komutu tamamlandığında bu komut, arasındaki bir tanımlayıcı işlevi görür.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="a0c3f-126">Gerçekleştirilebilecek tüm atlama kapsülleyen bir merkezi arabirimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="a0c3f-127">Erken bir sürüm işlemi iptal etmek için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="a0c3f-128">İş parçacığı başına birden fazla Adımlayıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="a0c3f-129">Örneğin, bir işlev atlama sırasında bir kesme noktası isabet ve kullanıcı bu işlev içinde yeni bir sürüm işlemini başlatmak isteyebilir.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="a0c3f-130">Bu durum nasıl ele alınacağını belirlemek için hata ayıklayıcı kadar olur.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="a0c3f-131">Hata ayıklayıcı özgün sürüm işlemi iptal edin veya iki işlem iç içe isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="a0c3f-132">`ICorDebugStepper` Arabirimi her iki seçenek destekler.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="a0c3f-133">Ortak dil çalışma zamanı (CLR) arası iş parçacıklı, sıralanmış bir çağrı yaparsa Adımlayıcı iş parçacıkları arasında taşıyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0c3f-134">Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c3f-135">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a0c3f-135">Requirements</span></span>  
 <span data-ttu-id="a0c3f-136">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0c3f-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c3f-137">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0c3f-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0c3f-138">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0c3f-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0c3f-139">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c3f-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c3f-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a0c3f-140">See Also</span></span>  
 [<span data-ttu-id="a0c3f-141">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="a0c3f-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)