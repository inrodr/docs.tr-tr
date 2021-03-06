---
title: 'Nasıl yapılır: ScrollViewer ile bir Genişletici Oluşturma'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 6c014d4f6a12bfb58c2ae68f580f632c9478c82f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553068"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Nasıl yapılır: ScrollViewer ile bir Genişletici Oluşturma
Bu örnek nasıl oluşturulacağını gösterir bir <xref:System.Windows.Controls.Expander> bir resim ve metin gibi karmaşık içerik içeren denetim. Bu örnek ayrıca içeriğini barındırır <xref:System.Windows.Controls.Expander> içinde bir <xref:System.Windows.Controls.ScrollViewer> denetim.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösterir bir <xref:System.Windows.Controls.Expander>. Örnek kullanan bir <xref:System.Windows.Controls.Primitives.BulletDecorator> tanımlamak için bir resim ve metin içeren denetim <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. A <xref:System.Windows.Controls.ScrollViewer> denetimi genişletilmiş içeriği kaydırmak için bir yöntem sağlar.  
  
 Örnek ayarlar Not <xref:System.Windows.FrameworkElement.Height%2A> özellikte <xref:System.Windows.Controls.ScrollViewer> yerine içerik üzerinde. Varsa <xref:System.Windows.FrameworkElement.Height%2A> içerik üzerinde ayarlanmış <xref:System.Windows.Controls.ScrollViewer> içeriği kaydırmak kullanıcının izin vermez. <xref:System.Windows.FrameworkElement.Width%2A> Özelliği ayarlanmış <xref:System.Windows.Controls.Expander> denetimi ve bu ayar uygulandığı <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> ve genişletilmiş içeriği.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Controls.Expander>  
 [Genişleticiye Genel Bakış](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
