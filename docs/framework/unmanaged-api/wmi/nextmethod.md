---
title: "NextMethod işlevi (yönetilmeyen API Başvurusu)"
description: "NextMethod işlevi numaralandırma sonraki yöntem alır."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9b14424bb914be3ba127670e1b6490f79854d6e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="nextmethod-function"></a><span data-ttu-id="bda60-103">NextMethod işlevi</span><span class="sxs-lookup"><span data-stu-id="bda60-103">NextMethod function</span></span>
<span data-ttu-id="bda60-104">Sonraki yöntem çağrısı ile başlayan bir numaralandırmasını alır [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bda60-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bda60-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bda60-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="bda60-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="bda60-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bda60-107">[in] Bu parametre kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="bda60-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bda60-108">[in] Bir işaretçi bir [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) örneği.</span><span class="sxs-lookup"><span data-stu-id="bda60-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="bda60-109">[in] Ayrılmış.</span><span class="sxs-lookup"><span data-stu-id="bda60-109">[in] Reserved.</span></span> <span data-ttu-id="bda60-110">Bu parametre 0 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="bda60-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="bda60-111">[out] İşaret eden bir işaretçi `null` çağrı önce.</span><span class="sxs-lookup"><span data-stu-id="bda60-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="bda60-112">İşlevi döndüğünde, yeni bir adres `BSTR` yöntem adını içerir.</span><span class="sxs-lookup"><span data-stu-id="bda60-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="bda60-113">[out] Bir işaretçi alır bir işaretçi bir [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) içeren `in` yöntemi için parametreler.</span><span class="sxs-lookup"><span data-stu-id="bda60-113">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="bda60-114">[out] Bir işaretçi alır bir işaretçi bir [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) içeren `out` yöntemi için parametreler.</span><span class="sxs-lookup"><span data-stu-id="bda60-114">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="bda60-115">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="bda60-115">Return value</span></span>

<span data-ttu-id="bda60-116">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üstbilgi dosyası, veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="bda60-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bda60-117">Sabit</span><span class="sxs-lookup"><span data-stu-id="bda60-117">Constant</span></span>  |<span data-ttu-id="bda60-118">Değer</span><span class="sxs-lookup"><span data-stu-id="bda60-118">Value</span></span>  |<span data-ttu-id="bda60-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bda60-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="bda60-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="bda60-120">0x8004101d</span></span> | <span data-ttu-id="bda60-121">Hiçbir çağrısına vardı [ `BeginEnumeration` ](beginenumeration.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="bda60-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bda60-122">0</span><span class="sxs-lookup"><span data-stu-id="bda60-122">0</span></span> | <span data-ttu-id="bda60-123">İşlev çağrısı başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="bda60-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="bda60-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="bda60-124">0x40005</span></span> | <span data-ttu-id="bda60-125">Sabit listede daha fazla özellik yok.</span><span class="sxs-lookup"><span data-stu-id="bda60-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="bda60-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bda60-126">Remarks</span></span>

<span data-ttu-id="bda60-127">Bu işlev çağrısı sarmalar [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="bda60-127">This function wraps a call to the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="bda60-128">Arayan çağırarak numaralandırma sırası başlar [BeginMethodEnumeration](beginmethodenumeration.md) işlev ve işlev döndürünceye kadar [NextMethod] işlevi çağırır `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="bda60-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="bda60-129">İsteğe bağlı olarak, çağıran çağırarak sırası tamamlandıktan [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bda60-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="bda60-130">Arayan numaralandırması erken çağırarak sonlandırabilir [EndMethodEnumeration](endmethodenumeration.md) dilediğiniz zaman.</span><span class="sxs-lookup"><span data-stu-id="bda60-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="bda60-131">Örnek</span><span class="sxs-lookup"><span data-stu-id="bda60-131">Example</span></span>

<span data-ttu-id="bda60-132">C++ örnek için bkz: [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="bda60-132">For a C++ example, see the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bda60-133">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="bda60-133">Requirements</span></span>  
 <span data-ttu-id="bda60-134">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda60-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda60-135">**Başlık:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bda60-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bda60-136">**.NET framework sürümleri:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bda60-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda60-137">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bda60-137">See also</span></span>  
[<span data-ttu-id="bda60-138">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="bda60-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)