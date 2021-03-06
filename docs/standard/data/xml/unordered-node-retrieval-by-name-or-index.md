---
title: Ada veya dizine göre sırasız düğüm alma
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da1c9f25052bb2354b435cd28b7ff55d4a754ed1
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584006"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a>Ada veya dizine göre sırasız düğüm alma
**XmlNamedNodeMap** NamedNodeMap olarak World Wide Web Consortium (W3C) belirtimi açıklanmıştır ve bunların adı veya dizin tarafından başvuru düğümleri olanağı sırasız bir dizi düğümü işlemek için gerekli değildir. Tek yolu erişiminiz bir **XmlNamedNodeMap** olduğunda bir **XmlNamedNodeMap** bir yöntem veya özellik ile döndürülür. Üç yöntem veya döndüren özellikler bir **XmlNamedNodeMap**:  
  
-   XmlElement.Attributes  
  
-   XmlDocumentType.Entities  
  
-   XmlDocumentType.Notations  
  
 Örneğin, **XmlDocumentType.Entities** özellik koleksiyonunu alır **XmlEntity** düğümleri belge türü bildirimi içinde bildirilmiş. Bu koleksiyonu olarak döndürülür bir **XmlNamedNodeMap**, ve kullanımı ile bir koleksiyon üzerinden yineleme **sayısı** özelliği ve görüntü varlık bilgileri. Bir örnek üzerinden yineleme için bir **XmlNamedNodeMap**, bkz: <xref:System.Xml.XmlDocumentType.Entities%2A>.  
  
 **XmlAttributeCollection** türetilir **XmlNamedNodeMap** ve gösterimler ve varlıkların salt okunur olsa yalnızca öznitelikler değiştirilebilir,. Kullanarak **XmlNamedNodeMap** öznitelikler için kendi XML adlarına göre bu öznitelikleri için düğümleri alabilirsiniz. Bu, bir öğe düğümü üzerinde özniteliklerin koleksiyonunu yönetmek için kolay bir yöntemini sağlar. Bu doğrudan karşıtlıklar **XmlNodeList**, ayrıca uygulayan **IEnumerable** arabirimi, ancak dizin erişimci yerine bir dize. **RemoveNamedItem** ve **SetNamedItem** yöntemleri karşı kullanılan yalnızca bir **XmlAttributeCollection**. Ekleme veya bir öznitelik koleksiyonundan olup olmadığını kaldırma **AttributeCollection** veya **XmlNamedNodeMap** uygulama, öznitelik koleksiyonundan öğesindeki değiştirir. Aşağıdaki kod örneği, bir özniteliği Taşı ve yeni bir öznitelik oluşturmak gösterilmektedir.  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 Öğesinden kaldırılan bir öznitelik gösteren ek kod örneği görmek için bir **AttributeCollection**, bkz: [XmlNamedNodeMap.RemoveNamedItem yöntemi](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem). Özellikler ve yöntemler hakkında daha fazla bilgi için bkz. [XmlNamedNodeMap üyeleri](AllMembers.T:System.Xml.XmlNamedNodeMap).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XML Belge Nesne Modeli (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
