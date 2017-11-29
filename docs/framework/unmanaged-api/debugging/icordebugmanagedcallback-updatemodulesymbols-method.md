---
title: "ICorDebugManagedCallback::UpdateModuleSymbols Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UpdateModuleSymbols
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a1606c256bbfd3b0a7de29b84aace1b4831a016
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="36aa8-102">ICorDebugManagedCallback::UpdateModuleSymbols Yöntemi</span><span class="sxs-lookup"><span data-stu-id="36aa8-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="36aa8-103">Hata ayıklayıcı bir ortak dil çalışma zamanı modülü simgelerini değişmiş bildirir.</span><span class="sxs-lookup"><span data-stu-id="36aa8-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36aa8-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="36aa8-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36aa8-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="36aa8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="36aa8-106">[in] Bir işaretçi Icordebugappdomain nesneye simgeleri değiştirilmesi modülü içeren uygulama etki alanını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="36aa8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="36aa8-107">[in] Bir işaretçi Icordebugmodule nesneye simgeleri değiştirilmesi modülü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="36aa8-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="36aa8-108">[in] Bir işaretçi bir Win32 COM `IStream` değiştirilmiş sembolleri içeren nesne.</span><span class="sxs-lookup"><span data-stu-id="36aa8-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36aa8-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="36aa8-109">Remarks</span></span>  
 <span data-ttu-id="36aa8-110">Bu yöntem çağırarak bir modülün simgelerin Hata Ayıklayıcı'nın Görünümü güncelleştirmek için bir fırsat sunar [Isymunmanagedreader::updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) veya [Isymunmanagedreader::replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="36aa8-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="36aa8-111">Bu geri çağırma birden çok kez aynı modülü için oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="36aa8-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="36aa8-112">Bir hata ayıklayıcısı ilişkisiz kaynak düzeyi kesme noktaları bağlamak denemelisiniz.</span><span class="sxs-lookup"><span data-stu-id="36aa8-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36aa8-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="36aa8-113">Requirements</span></span>  
 <span data-ttu-id="36aa8-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36aa8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36aa8-115">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36aa8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36aa8-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36aa8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36aa8-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36aa8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36aa8-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="36aa8-118">See Also</span></span>  
 [<span data-ttu-id="36aa8-119">Icordebugmanagedcallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="36aa8-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)