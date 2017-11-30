---
title: "&lt;declaredTypes&gt; Öğesi &lt;ekleme&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 699d18b4c49d2915724309d96d4ad501b98601eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="b5a5e-102">&lt;declaredTypes&gt; Öğesi &lt;ekleme&gt;</span><span class="sxs-lookup"><span data-stu-id="b5a5e-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="b5a5e-103">Tarafından kullanılan bir tür ekler <xref:System.Runtime.Serialization.DataContractSerializer> seri durumdan çıkarma sırasında.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="b5a5e-104">Bildirilen her türü, bir alan veya özellik bildirilen türü döndürülecek bilinen türler içerir.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="b5a5e-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="b5a5e-105">system.runtime.serialization</span></span>  
<span data-ttu-id="b5a5e-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="b5a5e-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-107">\<declaredTypes></span></span>  
<span data-ttu-id="b5a5e-108">\<Ekle >, \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a5e-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b5a5e-109">Syntax</span></span>  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5a5e-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="b5a5e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5a5e-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5a5e-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b5a5e-112">Attributes</span></span>  
  
|<span data-ttu-id="b5a5e-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="b5a5e-113">Attribute</span></span>|<span data-ttu-id="b5a5e-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b5a5e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5a5e-115">türü</span><span class="sxs-lookup"><span data-stu-id="b5a5e-115">type</span></span>|<span data-ttu-id="b5a5e-116">Gerekli dize özniteliği.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b5a5e-117">Tür adı (ad alanı dahil), derleme adı, sürüm numarası, kültür ve ortak anahtar belirteci belirtir.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5a5e-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="b5a5e-118">Child Elements</span></span>  
  
|<span data-ttu-id="b5a5e-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="b5a5e-119">Element</span></span>|<span data-ttu-id="b5a5e-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b5a5e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a5e-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="b5a5e-122">Eklenmekte olan türü için bilinen türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="b5a5e-123">Genel bir tür bildirilen türüdür sonra da bir parametre öğesine eklemelisiniz `<knownType>` öğesi bilinen türü döndürmek için kullanılan hangi genel parametresini belirtin.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5a5e-124">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="b5a5e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b5a5e-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="b5a5e-125">Element</span></span>|<span data-ttu-id="b5a5e-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b5a5e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a5e-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="b5a5e-128">Bilinen türler tarafından seri durumdan çıkarma sırasında gerektiren türleri içerir <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5a5e-129">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b5a5e-129">Remarks</span></span>  
 <span data-ttu-id="b5a5e-130">Bilinen türleri hakkında daha fazla bilgi için bkz: [veri sözleşmesi bilinen türleri](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) ve <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b5a5e-131">Bkz: [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) bu öğe kullanma örneği için.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5a5e-132">Eklerseniz <xref:System.Object> olarak yazın bir `<declaredType>`, <xref:System.Configuration.ConfigurationErrorsException> atılır.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="b5a5e-133">Bunun nedeni, <xref:System.Object> türü, yapılandırmada bildirilen türü olarak kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5a5e-134">Örnek</span><span class="sxs-lookup"><span data-stu-id="b5a5e-134">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5a5e-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b5a5e-135">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="b5a5e-136">Veri sözleşmesi bilinen türler</span><span class="sxs-lookup"><span data-stu-id="b5a5e-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="b5a5e-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="b5a5e-138">\<Ekle >, \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b5a5e-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)