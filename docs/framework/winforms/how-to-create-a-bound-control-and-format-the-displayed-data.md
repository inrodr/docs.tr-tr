---
title: 'Nasıl yapılır: Bağlantılı Denetim Oluşturma ve Görüntülenen Verileri Biçimlendirme'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 8f4d3c4c738e31ab83d506dc7afb4e49b142765b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615004"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Nasıl yapılır: Bağlantılı Denetim Oluşturma ve Görüntülenen Verileri Biçimlendirme
Windows Forms veri bağlama ile kullanarak bir veri bağlı denetim içinde görüntülenen verileri biçimlendirebilirsiniz **biçimlendirme ve Gelişmiş bağlama** iletişim kutusu.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>Bir denetimi bağlama ve görüntülenen verileri biçimlendirme  
  
1.  Bir veri kaynağına bağlanın.  
  
     Daha fazla bilgi için [bir veri kaynağına bağlanma](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Form denetimi seçin ve ardından Özellikler penceresini açın.  
  
3.  Genişletin **(DataBindings)** özelliği ve ardından **(Gelişmiş)** kutusunda, üç nokta düğmesini (![VisualStudioEllipsesButton ekran](../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) görüntülenecek **biçimlendirme ve Gelişmiş bağlama** iletişim kutusunda, bu denetimin özelliklerini tam bir listesi bulunur.  
  
4.  Bağlama ve ardından istediğiniz özelliği seçin **bağlama** oku.  
  
     Kullanılabilir veri kaynaklarının bir listesi görüntülenir.  
  
5.  İstediğiniz tek veri öğesi bulana kadar bağlamak istediğiniz veri kaynağını genişletin.  
  
     Örneğin, bir veri kümesi tablodaki bir sütun değerine bağlanıyorsanız, veri kümesinin adını genişletin ve ardından sütun adlarını görüntülemek için tablo adını genişletin.  
  
6.  Bağlanılacak bir öğe adına tıklayın.  
  
7.  İçinde **türünü biçimlendirme** kutusunda, denetimde görüntülenen verilere uygulamak istediğiniz biçime tıklayın.  
  
     Her durumda, veri kaynağı içeriyorsa denetimde görüntülenen değeri belirtebilirsiniz <xref:System.DBNull>. Aksi takdirde, Seçenekler, seçtiğiniz biçim türüne bağlı olarak biraz değişir. Biçimlendirme türleri ve seçenekleri aşağıdaki tabloda gösterilmektedir.  
  
    |Biçim türü|Biçimlendirme seçeneği|  
    |-----------------|-----------------------|  
    |Biçimlendirme yok|Seçenek yok.|  
    |Sayısal|Ondalık basamak sayısını kullanarak belirtin **ondalık** yukarı-aşağı denetimi.|  
    |Para Birimi|Ondalık basamak sayısını kullanarak belirtin **ondalık** yukarı-aşağı denetimi.|  
    |Tarih saat|Nasıl tarih ve saat öğelerden birini seçerek görüntüleneceğini seçin **türü** seçim kutusu.|  
    |Bilimsel|Ondalık basamak sayısını kullanarak belirtin **ondalık** yukarı-aşağı denetimi.|  
    |Özel|Kullanarak bir özel biçim dizesi belirtin.<br /><br /> Daha fazla bilgi için [biçimlendirme türleri](../../../docs/standard/base-types/formatting-types.md). **Not:** özel biçim dizeleri başarıyla ilişkili denetim ve veri kaynağı arasında gidiş dönüş için garanti edilmez. Bunun yerine işlemek <xref:System.Windows.Forms.Binding.Parse> veya <xref:System.Windows.Forms.Binding.Format> bağlama için olay ve olay işleme kodda özel biçimlendirme uygulayın.|  
  
8.  Tıklayın **Tamam** kapatmak için **biçimlendirme ve Gelişmiş bağlama** iletişim kutusu ve Özellikler penceresinin başı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Bir Windows Formunda Basit Bağlantılı Denetim Oluşturma](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Windows Forms'ta Kullanıcı Girdisi Doğrulama](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [Windows Forms Veri Bağlama](../../../docs/framework/winforms/windows-forms-data-binding.md)
