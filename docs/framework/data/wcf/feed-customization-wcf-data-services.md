---
title: "Akış özelleştirme (WCF Veri Hizmetleri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, feeds
- WCF Data Services, Atom protocol
- Atom Publishing Protocol [WCF Data Services]
- WCF Data Services, customizing feeds
ms.assetid: 0d1a39bc-6462-4683-bd7d-e74e0fd28a85
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e31f14d59bb2ac7caa233ff60c60eb944ee5bbbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="feed-customization-wcf-data-services"></a><span data-ttu-id="4516c-102">Akış özelleştirme (WCF Veri Hizmetleri)</span><span class="sxs-lookup"><span data-stu-id="4516c-102">Feed Customization (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="4516c-103">kullanan [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] veriyi bir akış olarak kullanıma sunmak için.</span><span class="sxs-lookup"><span data-stu-id="4516c-103"> uses the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose data as a feed.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="4516c-104">veri akışları için hem Atom hem de JavaScript nesne gösterimi (JSON) biçimini destekler.</span><span class="sxs-lookup"><span data-stu-id="4516c-104"> supports both Atom and JavaScript Object Notation (JSON) formats for data feeds.</span></span> <span data-ttu-id="4516c-105">Atom akışı, kullandığınızda [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] varlıkları ve ilişkileri HTTP iletisinin gövdesinde bulunan bir XML biçimine gibi verileri seri hale getirmek için standart bir yöntemini sağlar.</span><span class="sxs-lookup"><span data-stu-id="4516c-105">When you use an Atom feed, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] provides a standard method to serialize data, such as entities and relationships, into an XML format that can be included in the body of HTTP message.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="4516c-106">bir varsayılan varlık özellik eşlemesi varlıklarda bulunan verileri Atom öğeler arasındaki tanımlar.</span><span class="sxs-lookup"><span data-stu-id="4516c-106"> defines a default entity-property mapping between the data that is contained in entities and Atom elements.</span></span> <span data-ttu-id="4516c-107">Daha fazla bilgi için bkz: [OData: Atom biçimi](http://go.microsoft.com/fwlink/?LinkID=185794).</span><span class="sxs-lookup"><span data-stu-id="4516c-107">For more information, see [OData: Atom Format](http://go.microsoft.com/fwlink/?LinkID=185794).</span></span>  
  
 <span data-ttu-id="4516c-108">Veri Hizmeti tarafından döndürülen özelliği veri özelleştirilmiş bir şekilde yerine akış biçiminde standart seri hale gerektiren bir uygulama senaryosu olabilir.</span><span class="sxs-lookup"><span data-stu-id="4516c-108">You may have an application scenario that requires that the property data returned by the data service be serialized in a customized manner rather than in the standard feed format.</span></span> <span data-ttu-id="4516c-109">İle [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], bir veri akışı serileştirmede kullanılmayan öğeleri ve özniteliklerinin girdinin veya akıştaki girdinin özel öğeleri için bir varlık özelliklerini eşlenebilir özelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4516c-109">With [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], you can customize the serialization in a data feed so that properties of an entity may be mapped to unused elements and attributes of an entry or to custom elements of an entry in the feed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4516c-110">Atom akışları için akış özelleştirme yalnızca desteklenir.</span><span class="sxs-lookup"><span data-stu-id="4516c-110">Feed customization is only supported for Atom feeds.</span></span> <span data-ttu-id="4516c-111">JSON biçimi döndürülen akış için istendiğinde özel akışları döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="4516c-111">Custom feeds are not returned when the JSON format is requested for the returned feed.</span></span>  
  
 <span data-ttu-id="4516c-112">İle [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], veri modeli varlık türlerine el ile öznitelikleri uygulayarak bir Atom yükü için bir alternatif varlık özellik eşlemesi tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4516c-112">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can define an alternate entity-property mapping for an Atom payload by manually applying attributes to entity types in the data model.</span></span> <span data-ttu-id="4516c-113">Veri kaynağı sağlayıcı veri hizmetinin bu öznitelikler nasıl uygulamalıdır belirler.</span><span class="sxs-lookup"><span data-stu-id="4516c-113">The data source provider of the data service determines how you should apply these attributes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4516c-114">Özel akışları tanımladığınızda, tanımlı özel eşlemeleri sahip tüm varlık özellikleri projeksiyon içerdiği güvence altına almalıdır.</span><span class="sxs-lookup"><span data-stu-id="4516c-114">When you define custom feeds, you must guarantee that all entity properties that have custom mappings defined are included in the projection.</span></span> <span data-ttu-id="4516c-115">Eşlenen varlık özelliği cinsinden izdüşümünü bulunmaz, veri kaybı oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="4516c-115">When a mapped entity property is not included in the projection, data loss might occur.</span></span> <span data-ttu-id="4516c-116">Daha fazla bilgi için bkz: [sorgu tahminleri](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4516c-116">For more information, see [Query Projections](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md).</span></span>  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a><span data-ttu-id="4516c-117">Entity Framework sağlayıcısı akışlarıyla özelleştirme</span><span class="sxs-lookup"><span data-stu-id="4516c-117">Customizing Feeds with the Entity Framework Provider</span></span>  
 <span data-ttu-id="4516c-118">İle kullanılan veri modelini [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] sağlayıcı .edmx dosyasının XML olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="4516c-118">The data model used with the [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] provider is represented as XML in the .edmx file.</span></span> <span data-ttu-id="4516c-119">Bu durumda, özel akışları tanımlama öznitelikleri eklenir `EntityType` ve `Property` varlık türleri ve veri modelindeki özellikleri temsil eden öğeleri.</span><span class="sxs-lookup"><span data-stu-id="4516c-119">In this case, the attributes that define custom feeds are added to the `EntityType` and `Property` elements that represent entity types and properties in the data model.</span></span> <span data-ttu-id="4516c-120">Bu akış özelleştirme öznitelikler tanımlı değil [ \[MC CSDL\]: kavramsal şema tanım dosyası biçimi](http://go.microsoft.com/fwlink/?LinkId=159072), biçimi olduğu, [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] sağlayıcısı veri modeli tanımlamak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="4516c-120">These feed customization attributes are not defined in [\[MC-CSDL\]: Conceptual Schema Definition File Format](http://go.microsoft.com/fwlink/?LinkId=159072), which is the format that the [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] provider uses to define the data model.</span></span> <span data-ttu-id="4516c-121">Bu nedenle, akış özelleştirme öznitelikleri olarak tanımlanmış bir özel Şema ad alanındaki bildirmelidir `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`.</span><span class="sxs-lookup"><span data-stu-id="4516c-121">Therefore, you must declare feed customization attributes in a specific schema namespace, which is defined as `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`.</span></span> <span data-ttu-id="4516c-122">Aşağıdaki XML parçası uygulanan akış özelleştirme öznitelikleri gösterir `Property` öğeleri `Products` tanımlayan varlık türü `ProductName`, `ReorderLevel`, ve `UnitsInStock` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="4516c-122">The following XML fragment shows feed customization attributes applied to `Property` elements of the `Products` entity type that define the `ProductName`, `ReorderLevel`, and `UnitsInStock` properties.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 <span data-ttu-id="4516c-123">Bu öznitelikler için akış aşağıdaki özelleştirilmiş veri üretmek `Products` varlık kümesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-123">These attributes produce the following customized data feed for the `Products` entity set.</span></span> <span data-ttu-id="4516c-124">Akış, özelleştirilmiş veri `ProductName` özellik değerini hem de görüntülenir `author` öğesi de `ProductName` özellik öğesi ve `UnitsInStock` özelliği, kendi benzersiz ad alanına sahip özel bir öğe ve ile görüntülenir `ReorderLevel` öznitelik olarak özellik:</span><span class="sxs-lookup"><span data-stu-id="4516c-124">In the customized data feed, the `ProductName` property value is displayed in both in the `author` element and as the `ProductName` property element, and the `UnitsInStock` property is displayed in a custom element that has its own unique namespace and with the `ReorderLevel` property as an attribute:</span></span>  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 <span data-ttu-id="4516c-125">Daha fazla bilgi için bkz: [nasıl yapılır: özelleştirme akışları Entity Framework sağlayıcısı ile](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-ef-provider-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4516c-125">For more information, see [How to: Customize Feeds with the Entity Framework Provider](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-ef-provider-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4516c-126">Veri modeli için Uzantılar Entity Designer tarafından desteklenmediği için veri modeli içeren XML dosyasını el ile değiştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4516c-126">Because extensions to the data model are not supported by the Entity Designer, you must manually modify the XML file that contains the data model.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4516c-127">tarafından oluşturulan .edmx dosyasının [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] araçları, bkz: [.edmx dosyasının genel bakış](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span><span class="sxs-lookup"><span data-stu-id="4516c-127"> the .edmx file that is generated by the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools, see [.edmx File Overview](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>  
  
### <a name="custom-feed-attributes"></a><span data-ttu-id="4516c-128">Özel öznitelikler akışı</span><span class="sxs-lookup"><span data-stu-id="4516c-128">Custom Feed Attributes</span></span>  
 <span data-ttu-id="4516c-129">Aşağıdaki tabloda veri modeli tanımlayan kavramsal şema tanım dili için (CSDL) ekleyebileceğiniz akışları özelleştirme XML öznitelikleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="4516c-129">The following table shows the XML attributes that customize feeds that you can add to the conceptual schema definition language (CSDL) that defines the data model.</span></span> <span data-ttu-id="4516c-130">Bu öznitelikler özelliklerine eşdeğer <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> yansıma sağlayıcı ile kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4516c-130">These attributes are equivalent to the properties of the <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> used with the reflection provider.</span></span>  
  
|<span data-ttu-id="4516c-131">Öznitelik adı</span><span class="sxs-lookup"><span data-stu-id="4516c-131">Attribute name</span></span>|<span data-ttu-id="4516c-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4516c-132">Description</span></span>|  
|--------------------|-----------------|  
|`FC_ContentKind`|<span data-ttu-id="4516c-133">İçerik türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="4516c-133">Indicates the type of the content.</span></span> <span data-ttu-id="4516c-134">Aşağıdaki anahtar sözcükler dağıtım içerik türünü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="4516c-134">The following keywords define syndication content types.</span></span><br /><br /> <span data-ttu-id="4516c-135">`text:`Özellik değeri akışta metin olarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="4516c-135">`text:` The property value is displayed in the feed as text.</span></span><br /><br /> <span data-ttu-id="4516c-136">`html:`Özellik değeri akışta HTML olarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="4516c-136">`html:` The property value is displayed in the feed as HTML.</span></span><br /><br /> <span data-ttu-id="4516c-137">`xhtml:`Özellik değeri akışta XML biçimli HTML olarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="4516c-137">`xhtml:` The property value is displayed in the feed as XML-formatted HTML.</span></span><br /><br /> <span data-ttu-id="4516c-138">Bu anahtar sözcükler değerleri eşdeğer <xref:System.Data.Services.Common.SyndicationTextContentKind> yansıma sağlayıcı ile kullanılan numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="4516c-138">These keywords are equivalent to the values of the <xref:System.Data.Services.Common.SyndicationTextContentKind> enumeration used with the reflection provider.</span></span><br /><br /> <span data-ttu-id="4516c-139">Bu öznitelik ne zaman desteklenen `FC_NsPrefix` ve `FC_NsUri` öznitelikler kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4516c-139">This attribute is not supported when the `FC_NsPrefix` and `FC_NsUri` attributes are used.</span></span><br /><br /> <span data-ttu-id="4516c-140">Değerini belirttiğinizde `xhtml` için `FC_ContentKind` özniteliği sağlamanız özellik değeri düzgün şekilde biçimlendirilmemiş XML içeriyor.</span><span class="sxs-lookup"><span data-stu-id="4516c-140">When you specify a value of `xhtml` for the `FC_ContentKind` attribute, you must ensure that the property value contains properly formatted XML.</span></span> <span data-ttu-id="4516c-141">Veri Hizmeti, herhangi bir dönüştürme yapmadan değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="4516c-141">The data service returns the value without performing any transformations.</span></span> <span data-ttu-id="4516c-142">Ayrıca tüm XML öğesi öneklerini döndürülen XML ad alanı URI'si ve eşlenen akışta tanımlanan önek sahip olduğundan emin olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="4516c-142">You must also ensure that any XML element prefixes in the returned XML have a namespace URI and prefix defined in the mapped feed.</span></span>|  
|`FC_KeepInContent`|<span data-ttu-id="4516c-143">Başvurulan özellik değeri akışın içerik bölümü hem eşleşen konumda eklenmesi gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="4516c-143">Indicates that the referenced property value should be included both in the content section of the feed and in the mapped location.</span></span> <span data-ttu-id="4516c-144">Geçerli değerler `true` ve `false`.</span><span class="sxs-lookup"><span data-stu-id="4516c-144">Valid values are `true` and `false`.</span></span> <span data-ttu-id="4516c-145">Sonuçta elde edilen akış önceki sürümleriyle geriye dönük uyumlu olmak için [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], değerini belirtin `true` değeri akış içeriği bölümünde bulunduğundan emin olmak için.</span><span class="sxs-lookup"><span data-stu-id="4516c-145">To make the resulting feed backward-compatible with earlier versions of [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], specify a value of `true` to make sure that the value is included in the content section of the feed.</span></span>|  
|`FC_NsPrefix`|<span data-ttu-id="4516c-146">XML öğesi olmayan dağıtım eşlemeye ad alanı öneki.</span><span class="sxs-lookup"><span data-stu-id="4516c-146">The namespace prefix of the XML element in a non-syndication mapping.</span></span> <span data-ttu-id="4516c-147">Bu öznitelik ile birlikte kullanılmalıdır `FC_NsUri` özniteliği ve kullanılamaz `FC_ContentKind` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="4516c-147">This attribute must be used with the `FC_NsUri` attribute and cannot be used with the `FC_ContentKind` attribute.</span></span>|  
|`FC_NsUri`|<span data-ttu-id="4516c-148">Ad alanı URI'si dağıtım olmayan eşlemeye XML öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-148">The namespace URI of the XML element in a non-syndication mapping.</span></span> <span data-ttu-id="4516c-149">Bu öznitelik ile birlikte kullanılmalıdır `FC_NsPrefix` özniteliği ve kullanılamaz `FC_ContentKind` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="4516c-149">This attribute must be used with the `FC_NsPrefix` attribute and cannot be used with the `FC_ContentKind` attribute.</span></span>|  
|`FC_SourcePath`|<span data-ttu-id="4516c-150">Bu eşleme kuralı akış varlık özelliğinin yolu geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="4516c-150">The path of the property of the entity to which this feed mapping rule applies.</span></span> <span data-ttu-id="4516c-151">İçinde kullanıldığında bu öznitelik yalnızca desteklenen bir `EntityType` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-151">This attribute is only supported when it is used in an `EntityType` element.</span></span><br /><br /> <span data-ttu-id="4516c-152"><xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> Özelliği bir karmaşık tür doğrudan başvuruda bulunamaz.</span><span class="sxs-lookup"><span data-stu-id="4516c-152">The <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> property cannot directly reference a complex type.</span></span> <span data-ttu-id="4516c-153">Karmaşık türler için bir yol ifadesi özellik adları bir ters eğik çizgi ile ayrıldığı kullanmanız gerekir (`/`) karakter.</span><span class="sxs-lookup"><span data-stu-id="4516c-153">For complex types, you must use a path expression where property names are separated by a backslash (`/`) character.</span></span> <span data-ttu-id="4516c-154">Örneğin, aşağıdaki değerleri bir varlık türü için izin `Person` bir tamsayı özelliği ile `Age` ve karmaşık bir özellik</span><span class="sxs-lookup"><span data-stu-id="4516c-154">For example, the following values are allowed for an entity type `Person` with an integer property `Age` and a complex property</span></span><br /><br /> <span data-ttu-id="4516c-155">`Address`:</span><span class="sxs-lookup"><span data-stu-id="4516c-155">`Address`:</span></span><br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> <span data-ttu-id="4516c-156"><xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> Özelliği, bir boşluk veya bir özellik adı geçerli değil herhangi bir karakter içeren bir değere ayarlanamaz.</span><span class="sxs-lookup"><span data-stu-id="4516c-156">The <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> property cannot be set to a value that contains a space or any other character that is not valid in a property name.</span></span>|  
|`FC_TargetPath`|<span data-ttu-id="4516c-157">Sonuçta elde edilen akışın özelliği eşlemek istediğiniz hedef öğesinin adı.</span><span class="sxs-lookup"><span data-stu-id="4516c-157">The name of the target element of the resulting feed to map the property.</span></span> <span data-ttu-id="4516c-158">Bu öğe Atom belirtim tarafından tanımlanan bir öğe veya özel bir öğe olabilir.</span><span class="sxs-lookup"><span data-stu-id="4516c-158">This element can be an element defined by the Atom specification or a custom element.</span></span><br /><br /> <span data-ttu-id="4516c-159">Belirli bir konuma işaret önceden tanımlanmış dağıtım hedef yolu değerleri aşağıdaki sözcükler bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akış.</span><span class="sxs-lookup"><span data-stu-id="4516c-159">The following keywords are predefined syndication target-path values that point to specific location in an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span><br /><br /> <span data-ttu-id="4516c-160">`SyndicationAuthorEmail:``atom:email` Alt öğesi olan `atom:author` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-160">`SyndicationAuthorEmail:` The `atom:email` child element of the `atom:author` element.</span></span><br /><br /> <span data-ttu-id="4516c-161">`SyndicationAuthorName:``atom:name` Alt öğesi olan `atom:author` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-161">`SyndicationAuthorName:` The `atom:name` child element of the `atom:author` element.</span></span><br /><br /> <span data-ttu-id="4516c-162">`SyndicationAuthorUri:``atom:uri` Alt öğesi olan `atom:author` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-162">`SyndicationAuthorUri:` The `atom:uri` child element of the `atom:author` element.</span></span><br /><br /> <span data-ttu-id="4516c-163">`SyndicationContributorEmail:``atom:email` Alt öğesi olan `atom:contributor` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-163">`SyndicationContributorEmail:` The `atom:email` child element of the `atom:contributor` element.</span></span><br /><br /> <span data-ttu-id="4516c-164">`SyndicationContributorName:``atom:name` Alt öğesi olan `atom:contributor` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-164">`SyndicationContributorName:` The `atom:name` child element of the `atom:contributor` element.</span></span><br /><br /> <span data-ttu-id="4516c-165">`SyndicationContributorUri:``atom:uri` Alt öğesi olan `atom:contributor` öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-165">`SyndicationContributorUri:` The `atom:uri` child element of the `atom:contributor` element.</span></span><br /><br /> <span data-ttu-id="4516c-166">`SyndicationCustomProperty:`Bir özel özellik öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-166">`SyndicationCustomProperty:` A custom property element.</span></span> <span data-ttu-id="4516c-167">Özel bir öğeye eşlerken hedef iç içe öğelerin bir ters eğik çizgi ile ayrılır yol ifadesi olmalıdır (`/`) ve öznitelikleri ampersan tarafından belirtilen (`@`).</span><span class="sxs-lookup"><span data-stu-id="4516c-167">When mapping to a custom element, the target must be a path expression in which nested elements are separated by a backslash (`/`) and attributes are specified by an ampersand (`@`).</span></span> <span data-ttu-id="4516c-168">Aşağıdaki örnekte, dize `UnitsInStock/@ReorderLevel` adlı bir özniteliği için bir özellik değeri eşler `ReorderLevel` adlı bir alt öğesi üzerinde `UnitsInStock` kök giriş öğesinin.</span><span class="sxs-lookup"><span data-stu-id="4516c-168">In the following example, the string `UnitsInStock/@ReorderLevel` maps a property value to an attribute named `ReorderLevel` on a child element named `UnitsInStock` of the root entry element.</span></span><br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> <span data-ttu-id="4516c-169">Hedef bir özel öğe adı olduğunda `FC_NsPrefix` ve `FC_NsUri` öznitelikler de belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="4516c-169">When the target is a custom element name, the `FC_NsPrefix` and `FC_NsUri` attributes must also be specified.</span></span><br /><br /> <span data-ttu-id="4516c-170">`SyndicationPublished:``atom:published` Öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-170">`SyndicationPublished:` The `atom:published` element.</span></span><br /><br /> <span data-ttu-id="4516c-171">`SyndicationRights:``atom:rights` Öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-171">`SyndicationRights:` The `atom:rights` element.</span></span><br /><br /> <span data-ttu-id="4516c-172">`SyndicationSummary:``atom:summary` Öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-172">`SyndicationSummary:` The `atom:summary` element.</span></span><br /><br /> <span data-ttu-id="4516c-173">`SyndicationTitle:``atom:title` Öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-173">`SyndicationTitle:` The `atom:title` element.</span></span><br /><br /> <span data-ttu-id="4516c-174">`SyndicationUpdated:``atom:updated` Öğesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-174">`SyndicationUpdated:` The `atom:updated` element.</span></span><br /><br /> <span data-ttu-id="4516c-175">Bu anahtar sözcükler değerleri eşdeğer <xref:System.Data.Services.Common.SyndicationItemProperty> yansıma sağlayıcı ile kullanılan numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="4516c-175">These keywords are equivalent to the values of the <xref:System.Data.Services.Common.SyndicationItemProperty> enumeration used with the reflection provider.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4516c-176">Öznitelik adları ve değerleri büyük/küçük harf duyarlıdır.</span><span class="sxs-lookup"><span data-stu-id="4516c-176">Attribute names and values are case-sensitive.</span></span> <span data-ttu-id="4516c-177">Öznitelikleri olabilir ya da uygulanan `EntityType` öğesi ya da bir veya daha fazla `Property` öğeleri, ancak her ikisi de.</span><span class="sxs-lookup"><span data-stu-id="4516c-177">Attributes can be applied either to the `EntityType` element or to one or more `Property` elements, but not to both.</span></span>  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a><span data-ttu-id="4516c-178">Yansıma sağlayıcısı ile akışları özelleştirme</span><span class="sxs-lookup"><span data-stu-id="4516c-178">Customizing Feeds with the Reflection Provider</span></span>  
 <span data-ttu-id="4516c-179">Yansıma kullanarak uygulanan bir veri modeli akışları özelleştirmek için bir veya daha fazla örneğini ekleyin <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> özniteliği için veri modelindeki varlık türleri temsil eden sınıflar için.</span><span class="sxs-lookup"><span data-stu-id="4516c-179">To customize feeds for a data model that was implemented by using the reflection provider, add one or more instances of the <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> attribute to the classes that represent entity types in the data model.</span></span> <span data-ttu-id="4516c-180">Özelliklerini <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> sınıfı önceki bölümde açıklanan akış özelleştirme öznitelikleri karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="4516c-180">The properties of the <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> class correspond to the feed customization attributes that are described in the previous section.</span></span> <span data-ttu-id="4516c-181">Aşağıdaki bildirimi örneğidir `Order` türüyle özel eşleme için her iki özellik tanımlanan akış.</span><span class="sxs-lookup"><span data-stu-id="4516c-181">The following is an example of the declaration of the `Order` type, with custom feed mapping defined for both properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4516c-182">Bu örnek için veri modeli konusundaki tanımlanan [nasıl yapılır: yansıma sağlayıcı veri kullanarak hizmet oluşturma](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4516c-182">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 <span data-ttu-id="4516c-183">Bu öznitelikler için akış aşağıdaki özelleştirilmiş veri üretmek `Orders` varlık kümesi.</span><span class="sxs-lookup"><span data-stu-id="4516c-183">These attributes produce the following customized data feed for the `Orders` entity set.</span></span> <span data-ttu-id="4516c-184">Bu akış, özelleştirilmiş `OrderId` özellik değeri görüntüler yalnızca `title` öğesinin `entry` ve `Customer` özellik değeri görüntüler hem de `author` öğesi de `Customer` özellik öğesi:</span><span class="sxs-lookup"><span data-stu-id="4516c-184">In this customized feed, the `OrderId` property value displays only in the `title` element of the `entry` and the `Customer` property value displays both in the `author` element and as the `Customer` property element:</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 <span data-ttu-id="4516c-185">Daha fazla bilgi için bkz: [nasıl yapılır: özelleştirme akışları yansıma sağlayıcısı ile](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4516c-185">For more information, see [How to: Customize Feeds with the Reflection Provider](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).</span></span>  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a><span data-ttu-id="4516c-186">Bir özel veri hizmeti sağlayıcısına akışları özelleştirme</span><span class="sxs-lookup"><span data-stu-id="4516c-186">Customizing Feeds with a Custom Data Service Provider</span></span>  
 <span data-ttu-id="4516c-187">Özelleştirme çağırarak bir kaynak türü için tanımlı bir özel veri hizmeti sağlayıcısı kullanılarak tanımlanmış bir veri modeli için akış <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> üzerinde <xref:System.Data.Services.Providers.ResourceType> , bir varlık türü için veri modelindeki temsil eder.</span><span class="sxs-lookup"><span data-stu-id="4516c-187">Feed customization for a data model defined by using a custom data service provider is defined for a resource type by calling the <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> on the <xref:System.Data.Services.Providers.ResourceType> that represents an entity type in the data model.</span></span> <span data-ttu-id="4516c-188">Daha fazla bilgi için bkz: [özel veri hizmeti sağlayıcıları](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4516c-188">For more information, see [Custom Data Service Providers](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).</span></span>  
  
## <a name="consuming-custom-feeds"></a><span data-ttu-id="4516c-189">Özel tüketen akışları</span><span class="sxs-lookup"><span data-stu-id="4516c-189">Consuming Custom Feeds</span></span>  
 <span data-ttu-id="4516c-190">Olduğunda, uygulamanızın doğrudan tüketir bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akış, bunun herhangi bir özelleştirilmiş öğeleri ve özniteliklerinin döndürülen akıştaki işleyebilmesi olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="4516c-190">When your application directly consumes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, it must be able to process any customized elements and attributes in the returned feed.</span></span> <span data-ttu-id="4516c-191">Veri hizmeti sağlayıcısı bağımsız olarak, veri modelinde özel akışları uygulamış `$metadata` uç nokta döndüren özel veri hizmet tarafından döndürülen csdl'deki olarak özel akış öznitelikleri bilgi akışı.</span><span class="sxs-lookup"><span data-stu-id="4516c-191">When you have implemented custom feeds in your data model, regardless of the data service provider, the `$metadata` endpoint returns custom feed information as custom feed attributes in the CSDL returned by the data service.</span></span> <span data-ttu-id="4516c-192">Kullandığınızda **hizmet Başvurusu Ekle** iletişim veya [datasvcutil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) istemci veri hizmeti sınıfları, özelleştirilmiş akış öznitelikleri isteklerine güvence altına almak için kullanılır ve yanıtları oluşturmak için aracı veri hizmeti doğru şekilde işlenir.</span><span class="sxs-lookup"><span data-stu-id="4516c-192">When you use the **Add Service Reference** dialog or the [datasvcutil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool to generate client data service classes, the customized feed attributes are used to guarantee that requests and responses to the data service are handled correctly.</span></span>  
  
## <a name="feed-customization-considerations"></a><span data-ttu-id="4516c-193">Akış özelleştirme konuları</span><span class="sxs-lookup"><span data-stu-id="4516c-193">Feed Customization Considerations</span></span>  
 <span data-ttu-id="4516c-194">Aşağıdaki özel akış eşlemeleri tanımlarken düşünmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="4516c-194">You should consider the following when defining custom feed mappings.</span></span>  
  
-   <span data-ttu-id="4516c-195">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] İstemci değerlendirir eşlenmiş öğeleri akış boş olarak yalnızca boşluk içeriyorsa.</span><span class="sxs-lookup"><span data-stu-id="4516c-195">The [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client treats mapped elements in a feed as empty when they contain only whitespace.</span></span> <span data-ttu-id="4516c-196">Bu nedenle, yalnızca boşluk içeren eşlenmiş öğeleri aynı boşluk ile istemcide gerçekleştirilip değil.</span><span class="sxs-lookup"><span data-stu-id="4516c-196">Because of this, mapped elements that contain only whitespace are not materialized on the client with the same whitespace.</span></span> <span data-ttu-id="4516c-197">Bu istemcideki korumak için değerini ayarlamalısınız `KeepInContext` için `true` akış eşleme öznitelik.</span><span class="sxs-lookup"><span data-stu-id="4516c-197">To preserve this whitespace on the client, you must set the value of `KeepInContext` to `true` in the feed mapping attribute.</span></span>  
  
## <a name="versioning-requirements"></a><span data-ttu-id="4516c-198">Sürüm oluşturma gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="4516c-198">Versioning Requirements</span></span>  
 <span data-ttu-id="4516c-199">Akış özelleştirme olan aşağıdaki [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] iletişim kuralı sürüm gereksinimleri:</span><span class="sxs-lookup"><span data-stu-id="4516c-199">Feed customization has the following [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol versioning requirements:</span></span>  
  
-   <span data-ttu-id="4516c-200">Akış özelleştirme gerektiren bu hem istemci hem de veri hizmeti destek 2.0 sürümünü [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protokolü ve sonraki sürümler.</span><span class="sxs-lookup"><span data-stu-id="4516c-200">Feed customization requires that both the client and data service support version 2.0 of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol and later versions.</span></span>  
  
 <span data-ttu-id="4516c-201">Daha fazla bilgi için bkz: [veri hizmeti sürüm](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4516c-201">For more information, see [Data Service Versioning](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4516c-202">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4516c-202">See Also</span></span>  
 [<span data-ttu-id="4516c-203">Yansıma sağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="4516c-203">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)  
 [<span data-ttu-id="4516c-204">Entity Framework sağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="4516c-204">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)