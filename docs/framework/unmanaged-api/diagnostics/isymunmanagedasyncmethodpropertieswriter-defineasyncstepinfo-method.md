---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e305ca13e419a40e9838a46a61fe7a435b7ce56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="74c22-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Yöntemi</span><span class="sxs-lookup"><span data-stu-id="74c22-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="74c22-103">Zaman uyumsuz grubu tanımlayın geçerli yöntemi işlemlerinde bekler.</span><span class="sxs-lookup"><span data-stu-id="74c22-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="74c22-104">Her verim uzaklığı potansiyel verimini tanımlayan bir bekleme 's dönüş yönerge eşleşir.</span><span class="sxs-lookup"><span data-stu-id="74c22-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="74c22-105">Her `breakpointMethod` / `breakpointOffset` çifti söyler bize olduğu zaman uyumsuz işlemi, (hangi farklı bir yöntem olabilir. devam edecek</span><span class="sxs-lookup"><span data-stu-id="74c22-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c22-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="74c22-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74c22-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="74c22-107">Parameters</span></span>  
  
|<span data-ttu-id="74c22-108">Parametre</span><span class="sxs-lookup"><span data-stu-id="74c22-108">Parameter</span></span>|<span data-ttu-id="74c22-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="74c22-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="74c22-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="74c22-110">Return Value</span></span>  
 <span data-ttu-id="74c22-111">Döndürür `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="74c22-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c22-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="74c22-112">Requirements</span></span>  
 <span data-ttu-id="74c22-113">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="74c22-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c22-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="74c22-114">See Also</span></span>  
 [<span data-ttu-id="74c22-115">Isymunmanagedasyncmethodpropertieswriter arabirimi</span><span class="sxs-lookup"><span data-stu-id="74c22-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)