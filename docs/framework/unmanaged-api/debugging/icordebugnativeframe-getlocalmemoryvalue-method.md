---
title: ICorDebugNativeFrame::GetLocalMemoryValue Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a43bc0b4bcfb50804e4bffbe4f4f18280f873436
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="c0158-102">ICorDebugNativeFrame::GetLocalMemoryValue Metodu</span><span class="sxs-lookup"><span data-stu-id="c0158-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="c0158-103">Bir bağımsız değişken veya bu yerel çerçevesi için belirtilen bellek konumda depolanan yerel değişken değerini alır.</span><span class="sxs-lookup"><span data-stu-id="c0158-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0158-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c0158-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0158-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c0158-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c0158-106">[in] A `CORDB_ADDRESS` değerini içeren bellek konumunu belirten değer.</span><span class="sxs-lookup"><span data-stu-id="c0158-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c0158-107">[in] Tarafından başvurulan ikili meta verileri imza boyutu belirten bir tamsayı `pvSigBlob` parametresi.</span><span class="sxs-lookup"><span data-stu-id="c0158-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c0158-108">[in] A `PCCOR_SIGNATURE` değerinin türü ikili meta verileri imza gösteren değer.</span><span class="sxs-lookup"><span data-stu-id="c0158-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c0158-109">[out] Belirtilen bellek konumda depolanan alınan değeri temsil eden bir "ICorDebugValue" nesnesi adresini gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="c0158-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0158-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c0158-110">Requirements</span></span>  
 <span data-ttu-id="c0158-111">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0158-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0158-112">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0158-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0158-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0158-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0158-114">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0158-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0158-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c0158-115">See Also</span></span>  
 