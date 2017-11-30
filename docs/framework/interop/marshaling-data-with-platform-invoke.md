---
title: "Platform Çağırma ile Veri Hazırlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 71a4962029c0056287e97ea56dc02ae6cef8b603
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="marshaling-data-with-platform-invoke"></a><span data-ttu-id="281dc-102">Platform Çağırma ile Veri Hazırlama</span><span class="sxs-lookup"><span data-stu-id="281dc-102">Marshaling Data with Platform Invoke</span></span>
<span data-ttu-id="281dc-103">Yönetilmeyen Kitaplığı'ndan dışarı aktarılan işlevleri çağırmak için bir işlev prototipi yönetilmeyen işlevi temsil eden yönetilen kodda .NET Framework uygulamasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="281dc-103">To call functions exported from an unmanaged library, a .NET Framework application requires a function prototype in managed code that represents the unmanaged function.</span></span> <span data-ttu-id="281dc-104">Platform sağlayan prototip oluşturmak için veri doğru sıralamakta çağırma, aşağıdakileri yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="281dc-104">To create a prototype that enables platform invoke to marshal data correctly, you must do the following:</span></span>  
  
-   <span data-ttu-id="281dc-105">Uygulama <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği statik işlev veya yöntem yönetilen kod için.</span><span class="sxs-lookup"><span data-stu-id="281dc-105">Apply the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to the static function or method in managed code.</span></span>  
  
-   <span data-ttu-id="281dc-106">Yönetilmeyen veri türleri için yönetilen veri türleri yerine koyun.</span><span class="sxs-lookup"><span data-stu-id="281dc-106">Substitute managed data types for unmanaged data types.</span></span>  
  
 <span data-ttu-id="281dc-107">Yönetilmeyen işlev ile sağlanan belgelere özniteliği isteğe bağlı alanları ile uygulama ve yönetilmeyen türleri için yönetilen veri türleri değiştirerek bir eşdeğer yönetilen prototip oluşturmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="281dc-107">You can use the documentation supplied with an unmanaged function to construct an equivalent managed prototype by applying the attribute with its optional fields and substituting managed data types for unmanaged types.</span></span> <span data-ttu-id="281dc-108">Uygulama hakkında yönergeler için **DllImportAttribute**, bkz: [yönetilmeyen DLL işlevlerini kullanma](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-108">For instructions about how to apply the **DllImportAttribute**, see [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).</span></span>  
  
 <span data-ttu-id="281dc-109">Bu bölüm için bağımsız değişkenleri geçirme ve yönetilmeyen kitaplıkları tarafından dışarı aktarılan işlevlerden dönüş değerleri alma Yönetilen işlev prototipleri oluşturma gösteren örnekler sağlar.</span><span class="sxs-lookup"><span data-stu-id="281dc-109">This section provides samples that demonstrate how to create managed function prototypes for passing arguments to and receiving return values from functions exported by unmanaged libraries.</span></span> <span data-ttu-id="281dc-110">Örnekler de ne zaman kullanılacağını göstermek <xref:System.Runtime.InteropServices.MarshalAsAttribute> özniteliği ve <xref:System.Runtime.InteropServices.Marshal> veri açıkça sıralamakta sınıfı.</span><span class="sxs-lookup"><span data-stu-id="281dc-110">The samples also demonstrate when to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute and the <xref:System.Runtime.InteropServices.Marshal> class to explicitly marshal data.</span></span>  
  
## <a name="platform-invoke-data-types"></a><span data-ttu-id="281dc-111">Platform çağırma veri türleri</span><span class="sxs-lookup"><span data-stu-id="281dc-111">Platform invoke data types</span></span>  
 <span data-ttu-id="281dc-112">Aşağıdaki tabloda, Win32 API (Wtypes.h içinde listelenen) ve C stili işlevlerde kullanılan veri türlerini listeler.</span><span class="sxs-lookup"><span data-stu-id="281dc-112">The following table lists data types used in the Win32 API (listed in Wtypes.h) and C-style functions.</span></span> <span data-ttu-id="281dc-113">Birçok yönetilmeyen kitaplıkları bu veri türleri parametreler ve dönüş değerleri işlevler içerir.</span><span class="sxs-lookup"><span data-stu-id="281dc-113">Many unmanaged libraries contain functions that pass these data types as parameters and return values.</span></span> <span data-ttu-id="281dc-114">Üçüncü sütun karşılık gelen .NET Framework yerleşik değer türü veya yönetilen kodda kullanma sınıfı listeler.</span><span class="sxs-lookup"><span data-stu-id="281dc-114">The third column lists the corresponding .NET Framework built-in value type or class that you use in managed code.</span></span> <span data-ttu-id="281dc-115">Bazı durumlarda tabloda listelenen türü için aynı boyutta türünü değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="281dc-115">In some cases, you can substitute a type of the same size for the type listed in the table.</span></span>  
  
|<span data-ttu-id="281dc-116">Wtypes.h yönetilmeyen türü</span><span class="sxs-lookup"><span data-stu-id="281dc-116">Unmanaged type in Wtypes.h</span></span>|<span data-ttu-id="281dc-117">Yönetilmeyen C dil türü</span><span class="sxs-lookup"><span data-stu-id="281dc-117">Unmanaged C language type</span></span>|<span data-ttu-id="281dc-118">Yönetilen sınıf adı</span><span class="sxs-lookup"><span data-stu-id="281dc-118">Managed class name</span></span>|<span data-ttu-id="281dc-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="281dc-119">Description</span></span>|  
|--------------------------------|-------------------------------|------------------------|-----------------|  
|<span data-ttu-id="281dc-120">**İŞLEME**</span><span class="sxs-lookup"><span data-stu-id="281dc-120">**HANDLE**</span></span>|<span data-ttu-id="281dc-121">**void\***</span><span class="sxs-lookup"><span data-stu-id="281dc-121">**void\***</span></span>|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="281dc-122">32 bit 32-bit Windows işletim sistemlerinde, 64-bit Windows işletim sistemlerinde 64 bit.</span><span class="sxs-lookup"><span data-stu-id="281dc-122">32 bits on 32-bit Windows operating systems, 64 bits on 64-bit Windows operating systems.</span></span>|  
|<span data-ttu-id="281dc-123">**BAYT**</span><span class="sxs-lookup"><span data-stu-id="281dc-123">**BYTE**</span></span>|<span data-ttu-id="281dc-124">**İmzasız char**</span><span class="sxs-lookup"><span data-stu-id="281dc-124">**unsigned char**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="281dc-125">8 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-125">8 bits</span></span>|  
|<span data-ttu-id="281dc-126">**KISA**</span><span class="sxs-lookup"><span data-stu-id="281dc-126">**SHORT**</span></span>|<span data-ttu-id="281dc-127">**kısa**</span><span class="sxs-lookup"><span data-stu-id="281dc-127">**short**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="281dc-128">16 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-128">16 bits</span></span>|  
|<span data-ttu-id="281dc-129">**WORD**</span><span class="sxs-lookup"><span data-stu-id="281dc-129">**WORD**</span></span>|<span data-ttu-id="281dc-130">**İmzasız short**</span><span class="sxs-lookup"><span data-stu-id="281dc-130">**unsigned short**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="281dc-131">16 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-131">16 bits</span></span>|  
|<span data-ttu-id="281dc-132">**INT**</span><span class="sxs-lookup"><span data-stu-id="281dc-132">**INT**</span></span>|<span data-ttu-id="281dc-133">**int**</span><span class="sxs-lookup"><span data-stu-id="281dc-133">**int**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="281dc-134">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-134">32 bits</span></span>|  
|<span data-ttu-id="281dc-135">**UINT**</span><span class="sxs-lookup"><span data-stu-id="281dc-135">**UINT**</span></span>|<span data-ttu-id="281dc-136">**İmzasız int**</span><span class="sxs-lookup"><span data-stu-id="281dc-136">**unsigned int**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="281dc-137">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-137">32 bits</span></span>|  
|<span data-ttu-id="281dc-138">**UZUN**</span><span class="sxs-lookup"><span data-stu-id="281dc-138">**LONG**</span></span>|<span data-ttu-id="281dc-139">**uzun**</span><span class="sxs-lookup"><span data-stu-id="281dc-139">**long**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="281dc-140">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-140">32 bits</span></span>|  
|<span data-ttu-id="281dc-141">**BOOL**</span><span class="sxs-lookup"><span data-stu-id="281dc-141">**BOOL**</span></span>|<span data-ttu-id="281dc-142">**uzun**</span><span class="sxs-lookup"><span data-stu-id="281dc-142">**long**</span></span>|<xref:System.Byte>|<span data-ttu-id="281dc-143">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-143">32 bits</span></span>|  
|<span data-ttu-id="281dc-144">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="281dc-144">**DWORD**</span></span>|<span data-ttu-id="281dc-145">**İmzasız long**</span><span class="sxs-lookup"><span data-stu-id="281dc-145">**unsigned long**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="281dc-146">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-146">32 bits</span></span>|  
|<span data-ttu-id="281dc-147">**ULONG**</span><span class="sxs-lookup"><span data-stu-id="281dc-147">**ULONG**</span></span>|<span data-ttu-id="281dc-148">**İmzasız long**</span><span class="sxs-lookup"><span data-stu-id="281dc-148">**unsigned long**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="281dc-149">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-149">32 bits</span></span>|  
|<span data-ttu-id="281dc-150">**CHAR**</span><span class="sxs-lookup"><span data-stu-id="281dc-150">**CHAR**</span></span>|<span data-ttu-id="281dc-151">**char**</span><span class="sxs-lookup"><span data-stu-id="281dc-151">**char**</span></span>|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="281dc-152">ANSI ile işaretleme.</span><span class="sxs-lookup"><span data-stu-id="281dc-152">Decorate with ANSI.</span></span>|  
|<span data-ttu-id="281dc-153">**WCHAR**</span><span class="sxs-lookup"><span data-stu-id="281dc-153">**WCHAR**</span></span>|<span data-ttu-id="281dc-154">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="281dc-154">**wchar_t**</span></span>|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="281dc-155">Unicode ile işaretleme.</span><span class="sxs-lookup"><span data-stu-id="281dc-155">Decorate with Unicode.</span></span>|  
|<span data-ttu-id="281dc-156">**LPSTR**</span><span class="sxs-lookup"><span data-stu-id="281dc-156">**LPSTR**</span></span>|<span data-ttu-id="281dc-157">**char\***</span><span class="sxs-lookup"><span data-stu-id="281dc-157">**char\***</span></span>|<span data-ttu-id="281dc-158"><xref:System.String?displayProperty=nameWithType>veya<xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="281dc-158"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="281dc-159">ANSI ile işaretleme.</span><span class="sxs-lookup"><span data-stu-id="281dc-159">Decorate with ANSI.</span></span>|  
|<span data-ttu-id="281dc-160">**LPCSTR**</span><span class="sxs-lookup"><span data-stu-id="281dc-160">**LPCSTR**</span></span>|<span data-ttu-id="281dc-161">**Const char\***</span><span class="sxs-lookup"><span data-stu-id="281dc-161">**Const char\***</span></span>|<span data-ttu-id="281dc-162"><xref:System.String?displayProperty=nameWithType>veya<xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="281dc-162"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="281dc-163">ANSI ile işaretleme.</span><span class="sxs-lookup"><span data-stu-id="281dc-163">Decorate with ANSI.</span></span>|  
|<span data-ttu-id="281dc-164">**LPWSTR**</span><span class="sxs-lookup"><span data-stu-id="281dc-164">**LPWSTR**</span></span>|<span data-ttu-id="281dc-165">**wchar_t\***</span><span class="sxs-lookup"><span data-stu-id="281dc-165">**wchar_t\***</span></span>|<span data-ttu-id="281dc-166"><xref:System.String?displayProperty=nameWithType>veya<xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="281dc-166"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="281dc-167">Unicode ile işaretleme.</span><span class="sxs-lookup"><span data-stu-id="281dc-167">Decorate with Unicode.</span></span>|  
|<span data-ttu-id="281dc-168">**LPCWSTR**</span><span class="sxs-lookup"><span data-stu-id="281dc-168">**LPCWSTR**</span></span>|<span data-ttu-id="281dc-169">**Const wchar_t\***</span><span class="sxs-lookup"><span data-stu-id="281dc-169">**Const wchar_t\***</span></span>|<span data-ttu-id="281dc-170"><xref:System.String?displayProperty=nameWithType>veya<xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="281dc-170"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="281dc-171">Unicode ile işaretleme.</span><span class="sxs-lookup"><span data-stu-id="281dc-171">Decorate with Unicode.</span></span>|  
|<span data-ttu-id="281dc-172">**KAYAN NOKTA**</span><span class="sxs-lookup"><span data-stu-id="281dc-172">**FLOAT**</span></span>|<span data-ttu-id="281dc-173">**Kayan nokta**</span><span class="sxs-lookup"><span data-stu-id="281dc-173">**Float**</span></span>|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="281dc-174">32 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-174">32 bits</span></span>|  
|<span data-ttu-id="281dc-175">**ÇİFT**</span><span class="sxs-lookup"><span data-stu-id="281dc-175">**DOUBLE**</span></span>|<span data-ttu-id="281dc-176">**Çift**</span><span class="sxs-lookup"><span data-stu-id="281dc-176">**Double**</span></span>|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="281dc-177">64 bit</span><span class="sxs-lookup"><span data-stu-id="281dc-177">64 bits</span></span>|  
  
 <span data-ttu-id="281dc-178">Karşılık gelen türlerin [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# ve C++, bkz: [.NET Framework sınıf kitaplığı giriş](../../../docs/standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-178">For corresponding types in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++, see the [Introduction to the .NET Framework Class Library](../../../docs/standard/class-library-overview.md).</span></span>  
  
## <a name="pinvokelibdll"></a><span data-ttu-id="281dc-179">PinvokeLib.dll</span><span class="sxs-lookup"><span data-stu-id="281dc-179">PinvokeLib.dll</span></span>  
 <span data-ttu-id="281dc-180">Aşağıdaki kod Pinvoke.dll tarafından sağlanan kitaplık işlevleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="281dc-180">The following code defines the library functions provided by Pinvoke.dll.</span></span> <span data-ttu-id="281dc-181">Çok sayıda Bu bölümde çağrısında bu kitaplığı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="281dc-181">Many samples described in this section call this library.</span></span>  
  
### <a name="example"></a><span data-ttu-id="281dc-182">Örnek</span><span class="sxs-lookup"><span data-stu-id="281dc-182">Example</span></span>  
 [!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]  
  
 [!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]