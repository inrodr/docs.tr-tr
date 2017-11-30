---
title: "Nesneler için Varsayılan Sıralama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c5bfafcad5f1f60e7e763b69f220188517d29f17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="4bf5b-102">Nesneler için Varsayılan Hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-102">Default Marshaling for Objects</span></span>
<span data-ttu-id="4bf5b-103">Parametreler ve alanlar olarak yazılan <xref:System.Object?displayProperty=nameWithType> yönetilmeyen kod için şu türlerden biri olarak gösterilebilir:</span><span class="sxs-lookup"><span data-stu-id="4bf5b-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>  
  
-   <span data-ttu-id="4bf5b-104">Nesne bir parametre olduğunda bir değişken.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-104">A variant when the object is a parameter.</span></span>  
  
-   <span data-ttu-id="4bf5b-105">Nesne yapısı alan olduğunda bir arabirim.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-105">An interface when the object is a structure field.</span></span>  
  
 <span data-ttu-id="4bf5b-106">Nesne türleri için hazırlama yalnızca COM birlikte çalışma destekler.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="4bf5b-107">COM çeşitleri nesnelere sıralamakta varsayılan davranıştır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="4bf5b-108">Bu kurallar yalnızca türü için geçerli **nesne** ve türetilen kesin türü belirtilmiş nesne için geçerli değildir **nesne** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>  
  
 <span data-ttu-id="4bf5b-109">Bu konu hakkında nesnetürleri hazırlama aşağıdaki ek bilgileri sağlar:</span><span class="sxs-lookup"><span data-stu-id="4bf5b-109">This topic provides the following additional information about marshaling object types:</span></span>  
  
-   [<span data-ttu-id="4bf5b-110">Hazırlama seçenekleri</span><span class="sxs-lookup"><span data-stu-id="4bf5b-110">Marshaling Options</span></span>](#cpcondefaultmarshalingforobjectsanchor7)  
  
-   [<span data-ttu-id="4bf5b-111">Arabirim nesnesine hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-111">Marshaling Object to Interface</span></span>](#cpcondefaultmarshalingforobjectsanchor2)  
  
-   [<span data-ttu-id="4bf5b-112">Nesne değişken için hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-112">Marshaling Object to Variant</span></span>](#cpcondefaultmarshalingforobjectsanchor3)  
  
-   [<span data-ttu-id="4bf5b-113">VARIANT nesnesi için hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-113">Marshaling Variant to Object</span></span>](#cpcondefaultmarshalingforobjectsanchor4)  
  
-   [<span data-ttu-id="4bf5b-114">ByRef çeşitleri hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-114">Marshaling ByRef Variants</span></span>](#cpcondefaultmarshalingforobjectsanchor6)  
  
<a name="cpcondefaultmarshalingforobjectsanchor7"></a>   
## <a name="marshaling-options"></a><span data-ttu-id="4bf5b-115">Hazırlama seçenekleri</span><span class="sxs-lookup"><span data-stu-id="4bf5b-115">Marshaling Options</span></span>  
 <span data-ttu-id="4bf5b-116">Hazırlama seçenekleri aşağıdaki tabloda gösterilmektedir **nesne** veri türü.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-116">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="4bf5b-117"><xref:System.Runtime.InteropServices.MarshalAsAttribute> Özniteliği sağlayan birkaç <xref:System.Runtime.InteropServices.UnmanagedType> numaralandırma değerleri sıralama nesnelere.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-117">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>  
  
|<span data-ttu-id="4bf5b-118">Numaralandırma türü</span><span class="sxs-lookup"><span data-stu-id="4bf5b-118">Enumeration type</span></span>|<span data-ttu-id="4bf5b-119">Yönetilmeyen biçimi açıklaması</span><span class="sxs-lookup"><span data-stu-id="4bf5b-119">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="4bf5b-120">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-120">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="4bf5b-121">(varsayılan parametreler için)</span><span class="sxs-lookup"><span data-stu-id="4bf5b-121">(default for parameters)</span></span>|<span data-ttu-id="4bf5b-122">Bir COM Stili değişken.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-122">A COM-style variant.</span></span>|  
|<span data-ttu-id="4bf5b-123">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-123">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="4bf5b-124">Bir **IDispatch** arabirim, mümkünse; Aksi halde, bir **IUnknown** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-124">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|  
|<span data-ttu-id="4bf5b-125">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-125">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="4bf5b-126">(alanlar için varsayılan)</span><span class="sxs-lookup"><span data-stu-id="4bf5b-126">(default for fields)</span></span>|<span data-ttu-id="4bf5b-127">Bir **IUnknown** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-127">An **IUnknown** interface.</span></span>|  
|<span data-ttu-id="4bf5b-128">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-128">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="4bf5b-129">Bir **IDispatch** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-129">An **IDispatch** interface.</span></span>|  
  
 <span data-ttu-id="4bf5b-130">Aşağıdaki örnek yönetilen arabirimi tanımını gösterir `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-130">The following example shows the managed interface definition for `MarshalObject`.</span></span>  
  
```vb  
Interface MarshalObject  
   Sub SetVariant(o As Object)  
   Sub SetVariantRef(ByRef o As Object)  
   Function GetVariant() As Object  
  
   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)  
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _  
      As Object)  
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object  
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)  
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _  
      As Object)  
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object  
End Interface  
```  
  
```csharp  
interface MarshalObject {  
   void SetVariant(Object o);  
   void SetVariantRef(ref Object o);  
   Object GetVariant();  
  
   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);  
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);  
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();  
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);  
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);  
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();  
}  
```  
  
 <span data-ttu-id="4bf5b-131">Aşağıdaki kod dışarı `MarshalObject` bir tür kitaplığı için arabirim.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-131">The following code exports the `MarshalObject` interface to a type library.</span></span>  
  
```  
interface MarshalObject {  
   HRESULT SetVariant([in] VARIANT o);  
   HRESULT SetVariantRef([in,out] VARIANT *o);  
   HRESULT GetVariant([out,retval] VARIANT *o)   
   HRESULT SetIDispatch([in] IDispatch *o);  
   HRESULT SetIDispatchRef([in,out] IDispatch **o);  
   HRESULT GetIDispatch([out,retval] IDispatch **o)   
   HRESULT SetIUnknown([in] IUnknown *o);  
   HRESULT SetIUnknownRef([in,out] IUnknown **o);  
   HRESULT GetIUnknown([out,retval] IUnknown **o)   
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="4bf5b-132">Birlikte çalışma Sıralayıcı değişken içinde herhangi bir ayrılmış nesne çağrısından sonra otomatik olarak boşaltır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-132">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>  
  
 <span data-ttu-id="4bf5b-133">Aşağıdaki örnekte bir biçimlendirilmiş değer türü gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-133">The following example shows a formatted value type.</span></span>  
  
```vb  
Public Structure ObjectHolder  
   Dim o1 As Object  
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object  
End Structure  
```  
  
```csharp  
public struct ObjectHolder {  
   Object o1;  
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;  
}  
```  
  
 <span data-ttu-id="4bf5b-134">Aşağıdaki kod biçimlendirilmiş türü için bir tür kitaplığı dışarı aktarır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-134">The following code exports the formatted type to a type library.</span></span>  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
<a name="cpcondefaultmarshalingforobjectsanchor2"></a>   
## <a name="marshaling-object-to-interface"></a><span data-ttu-id="4bf5b-135">Arabirim nesnesine hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-135">Marshaling Object to Interface</span></span>  
 <span data-ttu-id="4bf5b-136">Bir nesne COM arabirim olarak sunulduğunda, bu arabirim sınıfı için yönetilen türü arabirimdir <xref:System.Object> ( **_Object** arabirimi).</span><span class="sxs-lookup"><span data-stu-id="4bf5b-136">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="4bf5b-137">Bu arabirim olarak yazılan bir **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) veya bir **IUnknown** (**UnmanagedType.IUnknown**) sonuçta elde edilen türü Kitaplığı'nda.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-137">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="4bf5b-138">COM istemcileri dinamik olarak çağırma yönetilen sınıf üyeleri veya türetilmiş sınıflarından tarafından uygulanan herhangi bir üye **_Object** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-138">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="4bf5b-139">İstemci ayrıca çağırabilirsiniz **QueryInterface** açıkça yönetilen türü tarafından uygulanan arabirimi elde edilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-139">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor3"></a>   
## <a name="marshaling-object-to-variant"></a><span data-ttu-id="4bf5b-140">Nesne değişken için hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-140">Marshaling Object to Variant</span></span>  
 <span data-ttu-id="4bf5b-141">Bir nesne için bir değişken sıralanmış, iç değişken türü aşağıdaki kurallara göre çalışma zamanında belirlenir:</span><span class="sxs-lookup"><span data-stu-id="4bf5b-141">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>  
  
-   <span data-ttu-id="4bf5b-142">Nesne başvurusu null ise (**hiçbir şey** Visual Basic'te), nesne türünde bir değişken için sıralanmış **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-142">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>  
  
-   <span data-ttu-id="4bf5b-143">Aşağıdaki tabloda listelenen herhangi bir türde bir örneğiyse, sonuçta elde edilen değişken türü Sıralayıcı yerleşik ve tabloda gösterilen kuralları tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-143">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>  
  
-   <span data-ttu-id="4bf5b-144">Açıkça hazırlama davranışı denetlemek için gereken diğer nesneleri uygulayabilirsiniz <xref:System.IConvertible> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-144">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="4bf5b-145">Bu durumda, döndürülen türü kodu değişken türü saptanır <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-145">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4bf5b-146">Nesne türünde bir değişken Aksi halde, sıralanmış **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-146">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>  
  
### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="4bf5b-147">Değişken için sistem türlerini hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-147">Marshaling System Types to Variant</span></span>  
 <span data-ttu-id="4bf5b-148">Aşağıdaki tabloda, yönetilen nesne türlerini ve bunların karşılık gelen COM değişken türlerine gösterir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-148">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="4bf5b-149">Çağrılan yöntem imzası türü olduğunda bu tür dönüştürülür <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-149">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
|<span data-ttu-id="4bf5b-150">Nesne türü</span><span class="sxs-lookup"><span data-stu-id="4bf5b-150">Object type</span></span>|<span data-ttu-id="4bf5b-151">COM değişken türü</span><span class="sxs-lookup"><span data-stu-id="4bf5b-151">COM variant type</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="4bf5b-152">Null Nesne başvurusu (**hiçbir şey** Visual Basic'te).</span><span class="sxs-lookup"><span data-stu-id="4bf5b-152">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="4bf5b-153">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-153">**VT_EMPTY**</span></span>|  
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-154">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-154">**VT_NULL**</span></span>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-155">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-155">**VT_ERROR**</span></span>|  
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-156">**VT_ERROR** ile **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-156">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-157">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-157">**VT_DISPATCH**</span></span>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-158">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-158">**VT_UNKNOWN**</span></span>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-159">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-159">**VT_CY**</span></span>|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-160">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-160">**VT_BOOL**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-161">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-161">**VT_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-162">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-162">**VT_UI1**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-163">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-163">**VT_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-164">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-164">**VT_UI2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-165">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-165">**VT_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-166">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-166">**VT_UI4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-167">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-167">**VT_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-168">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-168">**VT_UI8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-169">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-169">**VT_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-170">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-170">**VT_R8**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-171">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-171">**VT_DECIMAL**</span></span>|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-172">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-172">**VT_DATE**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-173">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-173">**VT_BSTR**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-174">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-174">**VT_INT**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-175">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-175">**VT_UINT**</span></span>|  
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="4bf5b-176">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-176">**VT_ARRAY**</span></span>|  
  
 <span data-ttu-id="4bf5b-177">Kullanarak `MarshalObject` önceki örnekte, aşağıdaki kod örneğinde tanımlanan arabirimi çeşitleri çeşitli türleri COM sunucuya geçirmek nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-177">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>  
  
```vb  
Dim mo As New MarshalObject()  
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.  
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.  
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.  
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.  
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.  
```  
  
```csharp  
MarshalObject mo = new MarshalObject();  
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.  
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.  
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.  
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.  
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.  
```  
  
 <span data-ttu-id="4bf5b-178">Karşılık gelen yönetilen türleri COM türleri sıralanmış sarmalayıcı sınıflar gibi kullanılarak <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, ve <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-178">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="4bf5b-179">Aşağıdaki kod örneğinde bu sarmalayıcıları çeşitleri çeşitli türleri COM sunucuya geçirmek için nasıl kullanılacağı gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-179">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
' Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(New UnknownWrapper(inew))  
' Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(New DispatchWrapper(inew))  
' Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(New ErrorWrapper(&H80054002))  
' Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))  
```  
  
```csharp  
using System.Runtime.InteropServices;  
// Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(new UnknownWrapper(inew));  
// Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(new DispatchWrapper(inew));  
// Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(new ErrorWrapper(0x80054002));  
// Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));  
```  
  
 <span data-ttu-id="4bf5b-180">Sarmalayıcı sınıfları tanımlanan <xref:System.Runtime.InteropServices> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-180">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="4bf5b-181">IConvertible arabirimi değişken için hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-181">Marshaling the IConvertible Interface to Variant</span></span>  
 <span data-ttu-id="4bf5b-182">Önceki bölümde listelenenler nasıl bunlar uygulayarak sıralanmış denetleyebilirsiniz daha diğer türleri <xref:System.IConvertible> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-182">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="4bf5b-183">Nesne uyguluyorsa **IConvertible** arabirimi, COM değişken türü, çalışma zamanında değeri tarafından belirlenir <xref:System.TypeCode> döndürülen numaralandırma <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-183">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4bf5b-184">İçin olası değerler aşağıdaki tabloda gösterilmektedir **TypeCode** numaralandırma ve her bir değer için karşılık gelen COM değişken türü.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-184">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>  
  
|<span data-ttu-id="4bf5b-185">TypeCode</span><span class="sxs-lookup"><span data-stu-id="4bf5b-185">TypeCode</span></span>|<span data-ttu-id="4bf5b-186">COM değişken türü</span><span class="sxs-lookup"><span data-stu-id="4bf5b-186">COM variant type</span></span>|  
|--------------|----------------------|  
|<span data-ttu-id="4bf5b-187">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-187">**TypeCode.Empty**</span></span>|<span data-ttu-id="4bf5b-188">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-188">**VT_EMPTY**</span></span>|  
|<span data-ttu-id="4bf5b-189">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-189">**TypeCode.Object**</span></span>|<span data-ttu-id="4bf5b-190">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-190">**VT_UNKNOWN**</span></span>|  
|<span data-ttu-id="4bf5b-191">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-191">**TypeCode.DBNull**</span></span>|<span data-ttu-id="4bf5b-192">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-192">**VT_NULL**</span></span>|  
|<span data-ttu-id="4bf5b-193">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-193">**TypeCode.Boolean**</span></span>|<span data-ttu-id="4bf5b-194">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-194">**VT_BOOL**</span></span>|  
|<span data-ttu-id="4bf5b-195">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-195">**TypeCode.Char**</span></span>|<span data-ttu-id="4bf5b-196">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-196">**VT_UI2**</span></span>|  
|<span data-ttu-id="4bf5b-197">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-197">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="4bf5b-198">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-198">**VT_I1**</span></span>|  
|<span data-ttu-id="4bf5b-199">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-199">**TypeCode.Byte**</span></span>|<span data-ttu-id="4bf5b-200">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-200">**VT_UI1**</span></span>|  
|<span data-ttu-id="4bf5b-201">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-201">**TypeCode.Int16**</span></span>|<span data-ttu-id="4bf5b-202">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-202">**VT_I2**</span></span>|  
|<span data-ttu-id="4bf5b-203">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-203">**TypeCode.UInt16**</span></span>|<span data-ttu-id="4bf5b-204">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-204">**VT_UI2**</span></span>|  
|<span data-ttu-id="4bf5b-205">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-205">**TypeCode.Int32**</span></span>|<span data-ttu-id="4bf5b-206">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-206">**VT_I4**</span></span>|  
|<span data-ttu-id="4bf5b-207">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-207">**TypeCode.UInt32**</span></span>|<span data-ttu-id="4bf5b-208">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-208">**VT_UI4**</span></span>|  
|<span data-ttu-id="4bf5b-209">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-209">**TypeCode.Int64**</span></span>|<span data-ttu-id="4bf5b-210">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-210">**VT_I8**</span></span>|  
|<span data-ttu-id="4bf5b-211">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-211">**TypeCode.UInt64**</span></span>|<span data-ttu-id="4bf5b-212">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-212">**VT_UI8**</span></span>|  
|<span data-ttu-id="4bf5b-213">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-213">**TypeCode.Single**</span></span>|<span data-ttu-id="4bf5b-214">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-214">**VT_R4**</span></span>|  
|<span data-ttu-id="4bf5b-215">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-215">**TypeCode.Double**</span></span>|<span data-ttu-id="4bf5b-216">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-216">**VT_R8**</span></span>|  
|<span data-ttu-id="4bf5b-217">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-217">**TypeCode.Decimal**</span></span>|<span data-ttu-id="4bf5b-218">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-218">**VT_DECIMAL**</span></span>|  
|<span data-ttu-id="4bf5b-219">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-219">**TypeCode.DateTime**</span></span>|<span data-ttu-id="4bf5b-220">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-220">**VT_DATE**</span></span>|  
|<span data-ttu-id="4bf5b-221">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-221">**TypeCode.String**</span></span>|<span data-ttu-id="4bf5b-222">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-222">**VT_BSTR**</span></span>|  
|<span data-ttu-id="4bf5b-223">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-223">Not supported.</span></span>|<span data-ttu-id="4bf5b-224">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-224">**VT_INT**</span></span>|  
|<span data-ttu-id="4bf5b-225">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-225">Not supported.</span></span>|<span data-ttu-id="4bf5b-226">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-226">**VT_UINT**</span></span>|  
|<span data-ttu-id="4bf5b-227">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-227">Not supported.</span></span>|<span data-ttu-id="4bf5b-228">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-228">**VT_ARRAY**</span></span>|  
|<span data-ttu-id="4bf5b-229">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-229">Not supported.</span></span>|<span data-ttu-id="4bf5b-230">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-230">**VT_RECORD**</span></span>|  
|<span data-ttu-id="4bf5b-231">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-231">Not supported.</span></span>|<span data-ttu-id="4bf5b-232">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-232">**VT_CY**</span></span>|  
|<span data-ttu-id="4bf5b-233">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-233">Not supported.</span></span>|<span data-ttu-id="4bf5b-234">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-234">**VT_VARIANT**</span></span>|  
  
 <span data-ttu-id="4bf5b-235">COM değişken değerini çağrılarak belirlenen **IConvertible.To** *türü* arabirimi, burada **için** *türü* dönüştürme döndürüldü türüne karşılık gelen yordamı **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-235">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="4bf5b-236">Örneğin, döndüren bir nesne **TypeCode.Double** gelen **IConvertible.GetTypeCode** türünde COM değişken sıralanmış **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-236">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="4bf5b-237">Değişken değeri elde edebilirsiniz (depolanan **dblVal** COM variant alanını) çevrim tarafından **IConvertible** arabirimi ve arama <xref:System.IConvertible.ToDouble%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-237">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor4"></a>   
## <a name="marshaling-variant-to-object"></a><span data-ttu-id="4bf5b-238">VARIANT nesnesi için hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-238">Marshaling Variant to Object</span></span>  
 <span data-ttu-id="4bf5b-239">Üretti. ne zaman bir nesne, türü ve bazen değerini sıralanmış değişken için bir değişken hazırlama nesne türünü belirler.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-239">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="4bf5b-240">Aşağıdaki tabloda, her bir değişken türü ve bir değişken için .NET Framework COM geçirildiğinde Sıralayıcı oluşturur karşılık gelen nesne türünü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-240">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>  
  
|<span data-ttu-id="4bf5b-241">COM değişken türü</span><span class="sxs-lookup"><span data-stu-id="4bf5b-241">COM variant type</span></span>|<span data-ttu-id="4bf5b-242">Nesne türü</span><span class="sxs-lookup"><span data-stu-id="4bf5b-242">Object type</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="4bf5b-243">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-243">**VT_EMPTY**</span></span>|<span data-ttu-id="4bf5b-244">Null Nesne başvurusu (**hiçbir şey** Visual Basic'te).</span><span class="sxs-lookup"><span data-stu-id="4bf5b-244">Null object reference (**Nothing** in Visual Basic).</span></span>|  
|<span data-ttu-id="4bf5b-245">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-245">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-246">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-246">**VT_DISPATCH**</span></span>|<span data-ttu-id="4bf5b-247">**System.__ComObject** ya da null ise (pdispVal null ==)</span><span class="sxs-lookup"><span data-stu-id="4bf5b-247">**System.__ComObject** or null if (pdispVal == null)</span></span>|  
|<span data-ttu-id="4bf5b-248">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-248">**VT_UNKNOWN**</span></span>|<span data-ttu-id="4bf5b-249">**System.__ComObject** ya da null ise (punkVal null ==)</span><span class="sxs-lookup"><span data-stu-id="4bf5b-249">**System.__ComObject** or null if (punkVal == null)</span></span>|  
|<span data-ttu-id="4bf5b-250">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-250">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-251">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-251">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-252">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-252">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-253">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-253">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-254">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-254">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-255">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-255">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-256">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-256">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-257">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-257">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-258">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-258">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-259">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-259">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-260">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-260">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-261">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-261">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-262">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-262">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-263">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-263">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-264">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-264">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-265">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-265">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-266">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-266">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-267">**VT_ARRAY** &#124; **VT_\***</span><span class="sxs-lookup"><span data-stu-id="4bf5b-267">**VT_ARRAY** &#124; **VT_\***</span></span>|<xref:System.Array?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-268">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-268">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="4bf5b-269">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-269">**VT_RECORD**</span></span>|<span data-ttu-id="4bf5b-270">Paketlenmiş değer türüne karşılık gelen.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-270">Corresponding boxed value type.</span></span>|  
|<span data-ttu-id="4bf5b-271">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-271">**VT_VARIANT**</span></span>|<span data-ttu-id="4bf5b-272">Desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-272">Not supported.</span></span>|  
  
 <span data-ttu-id="4bf5b-273">VARIANT türleri COM gelen geçirilen yönetilen kodu ve ardından geri COM aynı değişken türü çağrı süresince korumak değil.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-273">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="4bf5b-274">Türünde bir değişken olduğunda ne olacağını düşünün **VT_DISPATCH** COM .NET Framework geçirilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-274">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="4bf5b-275">Hazırlama sırasında değişken dönüştürülür bir <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-275">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4bf5b-276">Varsa **nesne** sonra geçirilen geri COM için geri türünde bir değişken için sıralanmış olduğundan **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-276">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="4bf5b-277">Başlangıçta nesne üretmek için kullanılan değişken aynı türde bir nesne COM yönetilen koddan sıralanmış zaman üretilen değişken olacaktır garantisi yoktur.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-277">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor6"></a>   
## <a name="marshaling-byref-variants"></a><span data-ttu-id="4bf5b-278">ByRef çeşitleri hazırlama</span><span class="sxs-lookup"><span data-stu-id="4bf5b-278">Marshaling ByRef Variants</span></span>  
 <span data-ttu-id="4bf5b-279">Türevleri kendilerini değere veya başvuruya göre geçirilen rağmen **VT_BYREF** bayrağı de kullanılabilir ile herhangi bir değişken türü değişken içeriğini yerine başvuruya geçirilen göstermek için değeri.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-279">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="4bf5b-280">Çeşitleri başvuruya göre sıralama ve bir türevi hazırlama arasındaki farkı **VT_BYREF** bayrağı ayarlanmış kafa karıştırıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-280">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="4bf5b-281">Aşağıdaki çizimde farklılıkları açıklar.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-281">The following illustration clarifies the differences.</span></span>  
  
 <span data-ttu-id="4bf5b-282">![Değişken geçilen yığınındaki](../../../docs/framework/interop/media/interopvariant.gif "interopvariant")</span><span class="sxs-lookup"><span data-stu-id="4bf5b-282">![Variant passed on the stack](../../../docs/framework/interop/media/interopvariant.gif "interopvariant")</span></span>  
<span data-ttu-id="4bf5b-283">Değer ve başvuru tarafından geçirilen çeşitleri</span><span class="sxs-lookup"><span data-stu-id="4bf5b-283">Variants passed by value and by reference</span></span>  
  
 <span data-ttu-id="4bf5b-284">**Nesneleri ve değişkenleri değere göre sıralama için varsayılan davranış**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-284">**Default behavior for marshaling objects and variants by value**</span></span>  
  
-   <span data-ttu-id="4bf5b-285">Nesneleri COM yönetilen koddan geçirirken, nesnenin içeriğinin tanımlanan kuralların kullanarak sıralayıcı tarafından oluşturulan yeni bir değişken içine kopyalanır [değişken hazırlama nesnesine](#cpcondefaultmarshalingforobjectsanchor3).</span><span class="sxs-lookup"><span data-stu-id="4bf5b-285">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#cpcondefaultmarshalingforobjectsanchor3).</span></span> <span data-ttu-id="4bf5b-286">Yönetilmeyen tarafında değişken yapılan değişiklikleri geri dönüş çağrısından özgün nesne için yayılmaz.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-286">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>  
  
-   <span data-ttu-id="4bf5b-287">Çeşitleri yönetilen kod için COM geçirirken, değişken içerikleri tanımlanan kuralların kullanarak yeni oluşturulan bir nesne için kopyalanır [hazırlama değişken nesnesine](#cpcondefaultmarshalingforobjectsanchor4).</span><span class="sxs-lookup"><span data-stu-id="4bf5b-287">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#cpcondefaultmarshalingforobjectsanchor4).</span></span> <span data-ttu-id="4bf5b-288">Yönetilen tarafında nesnede yapılan değişiklikleri geri dönüş çağrısından özgün değişken için yayılmaz.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-288">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>  
  
 <span data-ttu-id="4bf5b-289">**Nesneleri ve değişkenleri başvuruya göre sıralama için varsayılan davranış**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-289">**Default behavior for marshaling objects and variants by reference**</span></span>  
  
 <span data-ttu-id="4bf5b-290">Çağırana geri değişiklikleri yaymak için parametreleri başvuruyla geçirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-290">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="4bf5b-291">Örneğin, kullanabileceğiniz **ref** C# anahtar sözcüğü (veya **ByRef** Visual Basic'te yönetilen kod) başvuruya göre parametreleri geçirmek için.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-291">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="4bf5b-292">COM'da, başvuru parametreleri bir işaretçi gibi kullanılarak geçirilen bir **değişken \*** .</span><span class="sxs-lookup"><span data-stu-id="4bf5b-292">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>  
  
-   <span data-ttu-id="4bf5b-293">Bir nesne COM başvuruya göre geçirme, Sıralayıcı yeni bir değişken oluşturur ve çağrı yapılmadan önce nesne başvurusu içeriğini değişken kopyalar.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-293">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="4bf5b-294">Değişken, kullanıcının değişken içeriğini değiştirmek boş olduğu yönetilmeyen işleve geçirilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-294">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="4bf5b-295">Çağrısından getirisi yönetilmeyen tarafında değişken yapılan değişiklikler orijinal nesneyi yayılır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-295">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="4bf5b-296">Değişken türü çağrısı geçirilen değişken türünü farklıysa, değişiklikleri geri farklı bir türde bir nesne için yayılır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-296">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="4bf5b-297">Diğer bir deyişle, çağrısına geçirilen nesne türünü çağrısından döndürülen nesne türünü farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-297">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>  
  
-   <span data-ttu-id="4bf5b-298">Bir değişken başvurusu tarafından yönetilen koda geçirirken, Sıralayıcı yeni bir nesne oluşturur ve arama yapmadan önce değişken içeriğini nesnesine kopyalar.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-298">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="4bf5b-299">Nesneye bir başvurusu, kullanıcının bir nesneyi değiştirmek boş olduğu yönetilen bir işleve geçirilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-299">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="4bf5b-300">Çağrısından getirisi başvurulan nesneye yapılan değişiklikler özgün değişkenine yayılır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-300">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="4bf5b-301">Nesne türünü çağrısı geçirilen nesne türünü farklıysa, özgün değişken türünü değiştirilir ve geri değişken değeri yayılır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-301">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="4bf5b-302">Yeniden çağrısına geçirilen değişken türünü çağrısından döndürülen variant türü farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-302">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>  
  
 <span data-ttu-id="4bf5b-303">**Bir değişken VT_BYREF bayrağı ayarlanmış hazırlama için varsayılan davranış**</span><span class="sxs-lookup"><span data-stu-id="4bf5b-303">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>  
  
-   <span data-ttu-id="4bf5b-304">Yönetilen kod için değeri tarafından geçirilen bir değişken olabilir **VT_BYREF** bayrağı değişken değeri yerine bir başvuru içeriyor belirtmek üzere ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-304">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="4bf5b-305">Bu durumda, değişken değeri tarafından geçtiğinden değişken hala bir nesneye başvuruya.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-305">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="4bf5b-306">Sıralayıcı otomatik olarak değişken içeriğini dereferences ve arama yapmadan önce yeni oluşturulan nesnesine kopyalar.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="4bf5b-307">Nesne daha sonra yönetilen işlevdeki geçirilir; Ancak, çağrısından getirisi geri özgün türevi nesne dağıtılmaz.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-307">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="4bf5b-308">Yönetilen nesneye yapılan değişiklikler kaybolur.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-308">Changes made to the managed object are lost.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="4bf5b-309">Değişken olsa bile değer ile geçirilen bir değişken değerini değiştirmek mümkün **VT_BYREF** bayrağı ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-309">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>  
  
-   <span data-ttu-id="4bf5b-310">Yönetilen kod için başvuru tarafından geçirilen bir değişken de sağlayabilirsiniz **VT_BYREF** bayrağı değişken başka bir başvuru içeriyor belirtmek üzere ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-310">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="4bf5b-311">Değişken sıralanmış olduğundan bulursa, bir **ref** değişken başvuruya göre geçtiğinden nesne.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-311">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="4bf5b-312">Sıralayıcı otomatik olarak değişken içeriğini dereferences ve arama yapmadan önce yeni oluşturulan nesnesine kopyalar.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-312">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="4bf5b-313">Nesne geçirilen gibi yalnızca nesne aynı türde ise çağrısından getirisi nesnenin değerini geri başvuru özgün türevi içinde yayılır.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-313">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="4bf5b-314">Diğer bir deyişle, yayma ile bir değişken türü değiştirmez **VT_BYREF** bayrağı ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-314">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="4bf5b-315">Nesne türü aramasında değişirse bir <xref:System.InvalidCastException> çağrısından döndürülen oluşur.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-315">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>  
  
 <span data-ttu-id="4bf5b-316">Aşağıdaki tabloda çeşitleri ve nesneler için yayma kuralları özetler.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-316">The following table summarizes the propagation rules for variants and objects.</span></span>  
  
|<span data-ttu-id="4bf5b-317">Başlangıç</span><span class="sxs-lookup"><span data-stu-id="4bf5b-317">From</span></span>|<span data-ttu-id="4bf5b-318">Bitiş</span><span class="sxs-lookup"><span data-stu-id="4bf5b-318">To</span></span>|<span data-ttu-id="4bf5b-319">Geri yayılma değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="4bf5b-319">Changes propagated back</span></span>|  
|----------|--------|-----------------------------|  
|<span data-ttu-id="4bf5b-320">**Değişken***v* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-320">**Variant**  *v*</span></span>|<span data-ttu-id="4bf5b-321">**Nesne***o* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-321">**Object**  *o*</span></span>|<span data-ttu-id="4bf5b-322">Hiçbir zaman</span><span class="sxs-lookup"><span data-stu-id="4bf5b-322">Never</span></span>|  
|<span data-ttu-id="4bf5b-323">**Nesne***o* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-323">**Object**  *o*</span></span>|<span data-ttu-id="4bf5b-324">**Değişken***v* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-324">**Variant**  *v*</span></span>|<span data-ttu-id="4bf5b-325">Hiçbir zaman</span><span class="sxs-lookup"><span data-stu-id="4bf5b-325">Never</span></span>|  
|<span data-ttu-id="4bf5b-326">**Değişken*****\*****pv* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-326">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="4bf5b-327">**Ref nesne***o* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-327">**Ref Object**  *o*</span></span>|<span data-ttu-id="4bf5b-328">Her zaman</span><span class="sxs-lookup"><span data-stu-id="4bf5b-328">Always</span></span>|  
|<span data-ttu-id="4bf5b-329">**Ref nesne***o* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-329">**Ref object**  *o*</span></span>|<span data-ttu-id="4bf5b-330">**Değişken*****\*****pv* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-330">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="4bf5b-331">Her zaman</span><span class="sxs-lookup"><span data-stu-id="4bf5b-331">Always</span></span>|  
|<span data-ttu-id="4bf5b-332">**Değişken***v* **(VT_BYREF** *&#124;* **VT_\*)** </span><span class="sxs-lookup"><span data-stu-id="4bf5b-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="4bf5b-333">**Nesne***o* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-333">**Object**  *o*</span></span>|<span data-ttu-id="4bf5b-334">Hiçbir zaman</span><span class="sxs-lookup"><span data-stu-id="4bf5b-334">Never</span></span>|  
|<span data-ttu-id="4bf5b-335">**Değişken***v* **(VT_BYREF** *&#124;* **VT_)** </span><span class="sxs-lookup"><span data-stu-id="4bf5b-335">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="4bf5b-336">**Ref nesne***o* </span><span class="sxs-lookup"><span data-stu-id="4bf5b-336">**Ref Object**  *o*</span></span>|<span data-ttu-id="4bf5b-337">Yalnızca türü değişmemişse.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-337">Only if the type has not changed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bf5b-338">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4bf5b-338">See Also</span></span>  
 [<span data-ttu-id="4bf5b-339">Varsayılan hazırlama davranışı</span><span class="sxs-lookup"><span data-stu-id="4bf5b-339">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)  
 [<span data-ttu-id="4bf5b-340">Blok halinde kopyalanabilir ve kopyalanamaz türler</span><span class="sxs-lookup"><span data-stu-id="4bf5b-340">Blittable and Non-Blittable Types</span></span>](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [<span data-ttu-id="4bf5b-341">Tek yönlü öznitelikleri</span><span class="sxs-lookup"><span data-stu-id="4bf5b-341">Directional Attributes</span></span>](http://msdn.microsoft.com/en-us/241ac5b5-928e-4969-8f58-1dbc048f9ea2)  
 [<span data-ttu-id="4bf5b-342">Kopyalama ve sabitleme</span><span class="sxs-lookup"><span data-stu-id="4bf5b-342">Copying and Pinning</span></span>](../../../docs/framework/interop/copying-and-pinning.md)