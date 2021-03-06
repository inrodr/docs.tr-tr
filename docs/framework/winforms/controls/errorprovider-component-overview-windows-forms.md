---
title: ErrorProvider Bileşenine Genel Bakış (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 2272220917f2d5adf15f1ba84a5d4c3d0ec07165
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528892"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider Bileşenine Genel Bakış (Windows Forms)
Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) bileşen bir form veya denetim kullanıcı girdisi doğrulamak için kullanılır. Genellikle, bir form üzerinde kullanıcı girişini doğrulama veya dataset içindeki hataları görüntüleme ile birlikte kullanılır. Bir ileti kutusu kapatıldıktan sonra hata iletisi artık görünür olmadığı için bir hata sağlayıcısı bir hata iletisi bir ileti kutusu görüntüleme daha daha iyi bir seçenektir. <xref:System.Windows.Forms.ErrorProvider> Bileşen bir hata simgesi görüntüler (![ErrorProvider simgesi](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) kullanıcı üzerinden fare işaretçisini getirdiğinde metin kutusu gibi; ilgili denetim yanındaki hata simgesi, araç ipucu, hata iletisi dizesi gösteren görüntülenir.  
  
## <a name="key-properties"></a>Anahtar Özellikler  
 <xref:System.Windows.Forms.ErrorProvider> Bileşenin anahtar özellikleri <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, ve <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Kullanırken <xref:System.Windows.Forms.ErrorProvider> verilere bağlı denetimler ile bileşen <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> özelliği sırada bir hata simgesi formda göstermek için bileşeni için uygun bir kapsayıcı için (genellikle Windows formu) ayarlanmalıdır. Bileşen Tasarımcısı'nda eklendiğinde <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> özelliğini içeren formun ayarlayın; kodda denetimi eklerseniz, kendiniz ayarlamanız gerekir.  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> Özelliği, varsayılan yerine bir özel hata simgesi için ayarlanabilir. Zaman <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> özelliği ayarlanmış <xref:System.Windows.Forms.ErrorProvider> bileşeni, bir veri kümesi için hata iletileri görüntüleyebilirsiniz. Anahtar yöntemi <xref:System.Windows.Forms.ErrorProvider> bileşeni <xref:System.Windows.Forms.ErrorProvider.SetError%2A> hata ileti dizesi belirtir ve hata simgesi göründüğü yöntemi.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ErrorProvider> Bileşen erişilebilirlik istemciler için yerleşik destek sağlamaz. Bu bileşen kullanırken, uygulamanızın erişilebilir olması için bir ek, erişilebilir geri bildirim mekanizması sağlamanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.ErrorProvider>  
 [Nasıl yapılır: Windows Forms ErrorProvider Bileşeni ile DataSet İçindeki Hataları Görüntüleme](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [Nasıl yapılır: Windows Forms ErrorProvider Bileşeni ile Form Doğrulama için Hata Simgeleri Görüntüleme](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
