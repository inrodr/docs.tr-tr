---
title: "Varsayılan paragraf stili (C#) bulma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e2664620127e6e3ed9f723a7c23012905be3781b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="70f04-102">Varsayılan paragraf stili (C#) bulma</span><span class="sxs-lookup"><span data-stu-id="70f04-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="70f04-103">İlk WordprocessingML belge öğretici düzenleme bilgileri belgede paragrafları varsayılan stilini bulmak için bir görevdir.</span><span class="sxs-lookup"><span data-stu-id="70f04-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70f04-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="70f04-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70f04-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70f04-105">Description</span></span>  
 <span data-ttu-id="70f04-106">Aşağıdaki örnek, bir Office Açık XML WordprocessingML belgesini açar, paket belge ve stil bölümlerini bulur ve varsayılan stil adı bulan bir sorgu yürütür.</span><span class="sxs-lookup"><span data-stu-id="70f04-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="70f04-107">Office Açık XML belge paketleri ve bunların oluşur bölümleri hakkında daha fazla bilgi için bkz: [ayrıntıları, Office Açık XML WordprocessingML belgeleri (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="70f04-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="70f04-108">Sorgu adlı bir düğüm bulana `w:style` adlı bir özniteliği olan `w:type` "paragraf" değerini ve ayrıca sahip bir öznitelik adlı `w:default` "1" değerine sahip.</span><span class="sxs-lookup"><span data-stu-id="70f04-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="70f04-109">Bu öznitelikler ile yalnızca bir XML düğümü olacağından sorgusu kullanan <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> için tek bir koleksiyon dönüştürmek için işleci.</span><span class="sxs-lookup"><span data-stu-id="70f04-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="70f04-110">Ardından adı olan özniteliğin değerini alır `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="70f04-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="70f04-111">Bu örnek WindowsBase derlemeden sınıfları kullanır.</span><span class="sxs-lookup"><span data-stu-id="70f04-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="70f04-112">Türlerinde kullanan <xref:System.IO.Packaging?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="70f04-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70f04-113">Kod</span><span class="sxs-lookup"><span data-stu-id="70f04-113">Code</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="70f04-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="70f04-114">Comments</span></span>  
 <span data-ttu-id="70f04-115">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="70f04-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="70f04-116">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="70f04-116">Next Steps</span></span>  
 <span data-ttu-id="70f04-117">Sonraki örnekte, bir belge ve bunların stiller tüm paragrafları bulur benzer bir sorgu oluşturursunuz:</span><span class="sxs-lookup"><span data-stu-id="70f04-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="70f04-118">Paragrafları ve bunların stilleri (C#)</span><span class="sxs-lookup"><span data-stu-id="70f04-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="70f04-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70f04-119">See Also</span></span>  
 [<span data-ttu-id="70f04-120">Öğretici: İçeriği WordprocessingML belgesinde düzenleme</span><span class="sxs-lookup"><span data-stu-id="70f04-120">Tutorial: Manipulating Content in a WordprocessingML Document</span></span>](http://msdn.microsoft.com/library/2696355e-4f83-4eaf-91b2-baa721f42fb4)