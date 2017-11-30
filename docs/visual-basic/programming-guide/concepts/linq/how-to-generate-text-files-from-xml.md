---
title: "Nasıl yapılır: metin dosyaları (Visual Basic) XML'den oluştur"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b33f191-4abe-4419-b81b-3cb81d9a317f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 901d31b6dbac54740404a7dc182ecbadca5ddd74
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-generate-text-files-from-xml-visual-basic"></a><span data-ttu-id="1a101-102">Nasıl yapılır: metin dosyaları (Visual Basic) XML'den oluştur</span><span class="sxs-lookup"><span data-stu-id="1a101-102">How to: Generate Text Files from XML (Visual Basic)</span></span>
<span data-ttu-id="1a101-103">Bu örnek bir XML dosyasından bir virgülle ayrılmış değerler (CSV) dosyası oluşturmak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="1a101-103">This example shows how to generate a comma-separated values (CSV) file from an XML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a101-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="1a101-104">Example</span></span>  
 <span data-ttu-id="1a101-105">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Sürümünü dizeleri koleksiyon tek bir dize olarak toplamak için yordam kodu kullanır.</span><span class="sxs-lookup"><span data-stu-id="1a101-105">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] version uses procedural code to aggregate the collection of strings into a single string.</span></span>  
  
 <span data-ttu-id="1a101-106">Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: müşteriler ve siparişler (LINQ-XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1a101-106">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim strCollection As IEnumerable(Of String) = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select _  
        String.Format("{0},{1},{2},{3},{4},{5},{6},{7},{8},{9}{10}", _  
            el.@CustomerID, _  
            el.<CompanyName>.Value, _  
            el.<ContactName>.Value, _  
            el.<ContactTitle>.Value, _  
            el.<Phone>.Value, _  
            el.<FullAddress>.<Address>.Value, _  
            el.<FullAddress>.<City>.Value, _  
            el.<FullAddress>.<Region>.Value, _  
            el.<FullAddress>.<PostalCode>.Value, _  
            el.<FullAddress>.<Country>.Value, _  
            Environment.NewLine _  
        )  
Dim sb As StringBuilder = New StringBuilder()  
For Each str As String In strCollection  
    sb.Append(str)  
Next  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="1a101-107">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="1a101-107">This code produces the following output:</span></span>  
  
```  
GREAL,Great Lakes Food Market,Howard Snyder,Marketing Manager,(503) 555-7555,2732 Baker Blvd.,Eugene,OR,97403,USA  
HUNGC,Hungry Coyote Import Store,Yoshi Latimer,Sales Representative,(503) 555-6874,City Center Plaza 516 Main St.,Elgin,OR,97827,USA  
LAZYK,Lazy K Kountry Store,John Steel,Marketing Manager,(509) 555-7969,12 Orchestra Terrace,Walla Walla,WA,99362,USA  
LETSS,Let's Stop N Shop,Jaime Yorres,Owner,(415) 555-5938,87 Polk St. Suite 5,San Francisco,CA,94117,USA  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a101-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1a101-108">See Also</span></span>  
 [<span data-ttu-id="1a101-109">Projeksiyonlar ve dönüştürmeler (LINQ-XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a101-109">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)