---
title: 'Nasıl yapılır: Windows Forms Denetimini Bir Türe Bağlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: fdf2134d487787404cccbde1ba0f8c95cb6a4a3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503911"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Nasıl yapılır: Windows Forms Denetimini Bir Türe Bağlama
Verilerle etkileşimde bulunmak denetimleri oluştururken, bazı durumlarda, bir nesne yerine bir tür bir denetimin bağlanması gerekli bulacaksınız. Bu durum, ne zaman veri kullanılamıyor olabilir, ancak bir türün ortak arabirim bilgilerini görüntülemek, verilere bağlı denetimler hala gerekir özellikle, tasarım zamanında ortaya çıkar. Örneğin, bağlama bir <xref:System.Windows.Forms.DataGridView> denetlemek için bir Web hizmeti tarafından kullanıma sunulan bir nesne ve istediğiniz <xref:System.Windows.Forms.DataGridView> sütunlarını tasarım zamanında bir özel tür adlarını üyesiyle etiket denetimi.  
  
 Bir denetim türü ile kolayca bağlayabilirsiniz <xref:System.Windows.Forms.BindingSource> bileşeni.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl bağlanacağını gösterir. bir <xref:System.Windows.Forms.DataGridView> kullanarak özel bir tür denetimi bir <xref:System.Windows.Forms.BindingSource> bileşeni. Örneği çalıştırdığınızda, fark edeceksiniz <xref:System.Windows.Forms.DataGridView> özelliklerini yansıtan sütunları etiketli bir `Customer` nesne önce denetimin verilerle doldurulur. Örnek verileri eklemek için bir müşteri Ekle düğmesine sahip <xref:System.Windows.Forms.DataGridView> denetimi. Düğmeye tıkladığınızda yeni bir `Customer` eklenir <xref:System.Windows.Forms.BindingSource>. Gerçek hayattaki bir senaryoda, verileri bir Web hizmeti veya başka bir veri kaynağı için bir çağrı tarafından alınabilir.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem ve System.Windows.Forms öğelerini derlemelerine başvurular.  
  
 Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.  Ayrıca bkz: [nasıl yapılır: derleme ve çalıştırma bir tam Windows Formları kod örneği kullanarak Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [BindingSource Bileşeni](../../../../docs/framework/winforms/controls/bindingsource-component.md)
