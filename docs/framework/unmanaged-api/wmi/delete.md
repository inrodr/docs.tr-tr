---
title: "Delete işlevi (yönetilmeyen API Başvurusu)"
description: "Silme işlevini belirtilen özellik ve tüm alt niteleyicileri bir CIM sınıfı tanımından siler."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Delete
helpviewer_keywords: Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f32487d2bd59bd76acdc32218c6bb0842de20e87
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="delete-function"></a><span data-ttu-id="963aa-103">İşlev Sil</span><span class="sxs-lookup"><span data-stu-id="963aa-103">Delete function</span></span>
<span data-ttu-id="963aa-104">Belirtilen özellik ve tüm alt niteleyicileri bir CIM sınıfı tanımından siler.</span><span class="sxs-lookup"><span data-stu-id="963aa-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="963aa-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="963aa-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="963aa-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="963aa-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="963aa-107">[in] Bu parametre kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="963aa-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="963aa-108">[in] Bir işaretçi bir [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) örneği.</span><span class="sxs-lookup"><span data-stu-id="963aa-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="963aa-109">[in] Silinecek özelliğinin adı.</span><span class="sxs-lookup"><span data-stu-id="963aa-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="963aa-110">`wszName`Geçerli bir işaretçi olmalıdır `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="963aa-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="963aa-111">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="963aa-111">Return value</span></span>

<span data-ttu-id="963aa-112">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üstbilgi dosyası, veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="963aa-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="963aa-113">Sabit</span><span class="sxs-lookup"><span data-stu-id="963aa-113">Constant</span></span>  |<span data-ttu-id="963aa-114">Değer</span><span class="sxs-lookup"><span data-stu-id="963aa-114">Value</span></span>  |<span data-ttu-id="963aa-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="963aa-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="963aa-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="963aa-116">0x80041001</span></span> | <span data-ttu-id="963aa-117">Belirlenemeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="963aa-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="963aa-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="963aa-118">0x80041016</span></span> | <span data-ttu-id="963aa-119">Özellik silinemez.</span><span class="sxs-lookup"><span data-stu-id="963aa-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="963aa-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="963aa-120">0x80041008</span></span> | <span data-ttu-id="963aa-121">`wszzName` geçersizdir.</span><span class="sxs-lookup"><span data-stu-id="963aa-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="963aa-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="963aa-122">0x80041002</span></span> | <span data-ttu-id="963aa-123">Belirtilen özellik yok.</span><span class="sxs-lookup"><span data-stu-id="963aa-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="963aa-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="963aa-124">0x80041006</span></span> | <span data-ttu-id="963aa-125">İşlemi tamamlamak için yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="963aa-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="963aa-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="963aa-126">0x8004101c</span></span> | <span data-ttu-id="963aa-127">Özelliği bir taban sınıftan devralınır.</span><span class="sxs-lookup"><span data-stu-id="963aa-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="963aa-128">Özelliği bir sistem özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="963aa-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="963aa-129">0</span><span class="sxs-lookup"><span data-stu-id="963aa-129">0</span></span> | <span data-ttu-id="963aa-130">İşlev çağrısı başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="963aa-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="963aa-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="963aa-131">0x80041030</span></span> | <span data-ttu-id="963aa-132">İşlev geçerli sınıf için bir geçersiz kılma varsayılan değer silindi.</span><span class="sxs-lookup"><span data-stu-id="963aa-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="963aa-133">Bu özellikte üst sınıfı için varsayılan değer reactiviated olmuştur.</span><span class="sxs-lookup"><span data-stu-id="963aa-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="963aa-134">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="963aa-134">Remarks</span></span>

<span data-ttu-id="963aa-135">Bu işlev çağrısı sarmalar [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="963aa-135">This function wraps a call to the [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="963aa-136">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="963aa-136">Requirements</span></span>  
 <span data-ttu-id="963aa-137">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="963aa-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="963aa-138">**Başlık:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="963aa-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="963aa-139">**.NET framework sürümleri:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="963aa-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963aa-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="963aa-140">See also</span></span>  
[<span data-ttu-id="963aa-141">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="963aa-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)