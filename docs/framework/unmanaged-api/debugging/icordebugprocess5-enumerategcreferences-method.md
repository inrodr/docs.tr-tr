---
title: "ICorDebugProcess5::EnumerateGCReferences Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateGCReferences
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f517415412c93b009df81fc9a7f524449eb82a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="8b035-102">ICorDebugProcess5::EnumerateGCReferences Yöntemi</span><span class="sxs-lookup"><span data-stu-id="8b035-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="8b035-103">Bir işlemde atık olarak toplanmış olacak tüm nesneleri için bir numaralandırıcı alır.</span><span class="sxs-lookup"><span data-stu-id="8b035-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b035-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8b035-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b035-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="8b035-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="8b035-106">[in] Zayıf başvurular da sıralanması olup olmadığını gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="8b035-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="8b035-107">Varsa `enumerateWeakReferences` olan `true`, `ppEnum` Numaralandırıcı güçlü başvuruları ve zayıf başvurular içerir.</span><span class="sxs-lookup"><span data-stu-id="8b035-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="8b035-108">Varsa `enumerateWeakReferences` olan `false`, numaralandırıcı yalnızca güçlü başvurular içerir.</span><span class="sxs-lookup"><span data-stu-id="8b035-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="8b035-109">[out] Adresine bir işaretçi bir [Icordebuggcreferenceenum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) çöpünün toplanma için diğer bir deyişle bir numaralandırıcı nesneler için.</span><span class="sxs-lookup"><span data-stu-id="8b035-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b035-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8b035-110">Remarks</span></span>  
 <span data-ttu-id="8b035-111">Bu yöntem, bir işlemde herhangi bir yönetilen nesne için tam rooting zinciri belirlemenin bir yolunu sağlar ve bir nesne neden hala etkin olduğunu belirlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8b035-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b035-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="8b035-112">Requirements</span></span>  
 <span data-ttu-id="8b035-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b035-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b035-114">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b035-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b035-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b035-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b035-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b035-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b035-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8b035-117">See Also</span></span>  
 [<span data-ttu-id="8b035-118">Icordebugprocess5 arabirimi</span><span class="sxs-lookup"><span data-stu-id="8b035-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="8b035-119">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="8b035-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)