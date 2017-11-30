---
title: "ICorDebugEval2::NewStringWithLength Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewStringWithLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b794482e491dc9825b0311cf1731d159082bd1f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="1cf3d-102">ICorDebugEval2::NewStringWithLength Yöntemi</span><span class="sxs-lookup"><span data-stu-id="1cf3d-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="1cf3d-103">Belirtilen uzunlukta bir dize belirtilen içerikle oluşturur.</span><span class="sxs-lookup"><span data-stu-id="1cf3d-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf3d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1cf3d-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cf3d-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="1cf3d-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="1cf3d-106">[in] Dize değeri için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="1cf3d-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="1cf3d-107">[in] Dize uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="1cf3d-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cf3d-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1cf3d-108">Remarks</span></span>  
 <span data-ttu-id="1cf3d-109">Dizenin sonunda ise null karakter yönetilen dizesinde çağıranı olması beklenir `NewStringWithLength` yöntemi dize uzunluğu sonunda null karakteri içeren emin gerekir.</span><span class="sxs-lookup"><span data-stu-id="1cf3d-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="1cf3d-110">Dize, her zaman iş parçacığı şu anda yürütülmekte uygulama etki alanında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="1cf3d-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf3d-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1cf3d-111">Requirements</span></span>  
 <span data-ttu-id="1cf3d-112">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cf3d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf3d-113">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cf3d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cf3d-114">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cf3d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cf3d-115">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cf3d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>