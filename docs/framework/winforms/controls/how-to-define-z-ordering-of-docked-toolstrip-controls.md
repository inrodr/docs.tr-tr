---
title: 'Nasıl yapılır: Yerleştirilmiş ToolStrip Denetimlerinin Z Sıralamasını Tanımlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 34d600454a7fa63c7ba59bebded6365cd5401cb4
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45747225"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a>Nasıl yapılır: Yerleştirilmiş ToolStrip Denetimlerinin Z Sıralamasını Tanımlama
Konumuna bir <xref:System.Windows.Forms.ToolStrip> denetimi doğru şekilde yerleştirme ile denetim doğru formun z düzeninde hizalamanız gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl düzenleneceğini gösterir bir <xref:System.Windows.Forms.ToolStrip> denetimi ve bir yerleşik <xref:System.Windows.Forms.MenuStrip> z düzenini belirterek denetimi.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 Z düzenini sıralarına göre belirlenir <xref:System.Windows.Forms.ToolStrip> ve <xref:System.Windows.Forms.MenuStrip>  
  
 denetimler, formun eklenir <xref:System.Windows.Forms.Control.Controls%2A> koleksiyonu.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 Bu çağrılar için sırasını ters <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> yöntemi ve görünüm düzenini üzerindeki etkisi.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   System.Windows.Forms System.Design ve System.Drawing derlemelerine başvurular.  
  
 Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.  Ayrıca se [nasıl yapılır: derleme ve çalıştırma bir tam Windows Formları kod örneği kullanarak Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [ToolStrip Denetimi](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
