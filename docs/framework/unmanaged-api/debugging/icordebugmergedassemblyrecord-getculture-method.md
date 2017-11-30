---
title: "ICorDebugMergedAssemblyRecord::GetCulture yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7791491a050e31d8d6c5dfb6ef9ffe209921753d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="6adff-102">ICorDebugMergedAssemblyRecord::GetCulture yöntemi</span><span class="sxs-lookup"><span data-stu-id="6adff-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="6adff-103">Derleme kültür adı dizesini alır.</span><span class="sxs-lookup"><span data-stu-id="6adff-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adff-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6adff-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6adff-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="6adff-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="6adff-106">[in] Karakter sayısını `szCulture` arabellek.</span><span class="sxs-lookup"><span data-stu-id="6adff-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="6adff-107">[out] Gerçekte yazılan karakter sayısını `szCulture` arabellek.</span><span class="sxs-lookup"><span data-stu-id="6adff-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="6adff-108">[out] Kültür adı içeren bir karakter dizisi.</span><span class="sxs-lookup"><span data-stu-id="6adff-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6adff-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6adff-109">Remarks</span></span>  
 <span data-ttu-id="6adff-110">Kültür adı "en-US" (için İngilizce (ABD) kültür) veya (için bağımsız bir kültür) "nötr" gibi bir kültür tanımlayan benzersiz bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="6adff-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6adff-111">Bu yöntem yalnızca .NET yerel ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6adff-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6adff-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6adff-112">Requirements</span></span>  
 <span data-ttu-id="6adff-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6adff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6adff-114">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6adff-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6adff-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6adff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6adff-116">**.NET framework sürümleri:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6adff-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adff-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6adff-117">See Also</span></span>  
 [<span data-ttu-id="6adff-118">ICorDebugMergedAssemblyRecord arabirimi</span><span class="sxs-lookup"><span data-stu-id="6adff-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="6adff-119">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="6adff-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)