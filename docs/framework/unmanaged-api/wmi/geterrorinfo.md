---
title: "Geterrorınfo işlevi (yönetilmeyen API Başvurusu)"
description: "Geterrorınfo işlevi önceki işlev çağrısında hata bilgilerini alır."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetErrorInfo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetErrorInfo
helpviewer_keywords: GetErrorInfo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1bdaa72723855c6688a7c8c7704b958f6196dfd
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="e9ef2-103">Geterrorınfo işlevi</span><span class="sxs-lookup"><span data-stu-id="e9ef2-103">GetErrorInfo function</span></span>
<span data-ttu-id="e9ef2-104">Önceki işlev çağrısında hata bilgilerini alır.</span><span class="sxs-lookup"><span data-stu-id="e9ef2-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e9ef2-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e9ef2-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="e9ef2-106">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="e9ef2-106">Return value</span></span>

<span data-ttu-id="e9ef2-107">Bir işaretçi bir [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) işlev çağrısı başarılı olursa, nesne veya `null` başarısız olursa.</span><span class="sxs-lookup"><span data-stu-id="e9ef2-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e9ef2-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e9ef2-108">Remarks</span></span>

<span data-ttu-id="e9ef2-109">Bu işlev çağrısı sarmalar [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e9ef2-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9ef2-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="e9ef2-110">Requirements</span></span>  
 <span data-ttu-id="e9ef2-111">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9ef2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ef2-112">**Başlık:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="e9ef2-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="e9ef2-113">**.NET framework sürümleri:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ef2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ef2-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e9ef2-114">See also</span></span>  
[<span data-ttu-id="e9ef2-115">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="e9ef2-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)