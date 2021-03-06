---
title: WPF'de Tipografi
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 0ec1c227196e9118f9174feb103a3ecbf5bcb7c4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528090"
---
# <a name="typography-in-wpf"></a>WPF'de Tipografi
Bu konu, ana tipografik özelliklerini tanıtır [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Geliştirilmiş kalitesini ve metin işleme performansını bu özellikler [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tipografi destek, Gelişmiş uluslararası metin yazı tipi desteği geliştirilmiştir ve yeni metin uygulama programlama arabirimleri (API).  
  

  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Geliştirilmiş kalitesini ve performansını metin  
 Metinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanılarak oluşturulması [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], netliği ve okunabilirliği metin geliştirir. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] bir yazılım teknolojisi tarafından geliştirilen [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] , dizüstü ekranları, Pocket PC ekranları ve düz panel izleyiciler gibi mevcut LCD'ler (Sıvı Crystal gösterir), metnin okunabilirliğini artırır. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] büyük bir aslına uygunluk, doğru şekilde ile bir piksel kesirli bir kısmını hizalama karakterleri tarafından görüntülenecek metni veren alt piksel işleme kullanır. Ek çözümleme uzun süreler okumak çok daha kolay hale metin görüntüleme, küçük ayrıntıları netliğini artırır. Başka bir geliştirme [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] içinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y yönünde düzgünleştirme, hangi düzgünleştirir kırpın ve basit metin karakterleri Eğriler altında olduğu. Daha fazla ayrıntı için [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] özellikler bkz [ClearType genel bakışı](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 ![ClearType y metinle&#45;anti yönü&#45;yumuşatma](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.gif "TypographyInWPF02")  
ClearType y yönünde düzgünleştirme ile metin  
  
 Tüm metin işleme işlem hattı içindeki Donanım hızlandırmalı [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] makinenizin en düşük gerekli donanım düzeyini karşılaması koşuluyla. İşleme, yazılım işleme geri donanım döner kullanılarak gerçekleştirilemiyor. Donanım hızlandırma etkileyen tüm metin işlenen ardışık düzen aşamaları — efektleri uygulamak için uygulama depolamasını tek tek karakter, karakter çalıştığında, içine birleştirme karakterleri [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] son görüntülenen çıktının algoritmaya karıştırma. Donanım hızlandırma hakkında daha fazla bilgi için bkz. [grafik işleme katmanları](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 ![Metin işleme işlem hattı diyagramı](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
Metin işleme işlem hattı diyagramı  
  
 Ayrıca, animasyonlu metin karakterin veya karakter, grafik donanım özelliği etkinleştirilmiş yararlanır [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Bu düz metin animasyonda sonuçlanır.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Zengin tipografi  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Yazı biçimi uzantısıdır [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] yazı biçimi. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Yazı biçimi ortaklaşa tarafından geliştirilen [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] ve Adobe ve Gelişmiş tipografik özellikleri zengin bir listesini sağlar. <xref:System.Windows.Documents.Typography> Nesne sunan birçok gelişmiş özelliği [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] yazı tipleri, stil alternatifleri ve süsler gibi. [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] Örnek takımına [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles ve Pescadero yazı tipleri gibi zengin özellikleriyle tasarlanmıştır yazı tipi. Daha fazla bilgi için [örnek OpenType yazı tipi paketi](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Pericles [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] yazı tipi standart karakter kümesini biçimsel alternatifler sağlayan ek karakterleri içerir. Aşağıdaki metni diğer biçimsel görüntüler.  
  
 ![OpenType diğer biçimsel kullanarak metin](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
OpenType diğer biçimsel kullanarak metin  
  
 Süsler genellikle calligraphy ile ilişkili ayrıntılı süsleme kullanan dekoratif karakterlerdir. Standart ve dalgalı karakterleri Palatino yazı tipi için aşağıdaki metni görüntüler.  
  
 ![OpenType standart ve swash karakterleri kullanarak metin](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
OpenType standart ve swash karakterleri kullanarak metin  
  
 Daha fazla ayrıntı için [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] özellikler bkz [OpenType yazı tipi özellikleri](../../../../docs/framework/wpf/advanced/opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>Gelişmiş uluslararası metin desteği  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Aşağıdaki özellikleri sağlayarak Gelişmiş uluslararası metin desteği sağlar:  
  
-   Otomatik satır aralığı Uyarlamalı ölçümü kullanarak, tüm yazma sistemleri.  
  
-   Uluslararası metin için geniş destek. Daha fazla bilgi için [WPF için genelleştirme](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   Dil temelli satır kesme, heceleme ve gerekçe.  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>Gelişmiş yazı tipi desteği  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Aşağıdaki özellikleri sağlayarak gelişmiş yazı tipi desteği sağlar:  
  
-   Tüm metni için Unicode. Yazı tipi davranışı ve artık seçim charset veya kod gerektirir.  
  
-   Yazı tipi davranışı sistem yerel ayarları gibi genel ayarlar bağımsızdır.  
  
-   Ayrı <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, ve <xref:System.Windows.FontStyle> türleri tanımlamak için bir <xref:System.Windows.Media.FontFamily>. Bu kıyasla daha fazla esneklik sağlar [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] programlama, hangi Boolean birleşimlerini italik ve kalın yazı tipi ailesi tanımlamak için kullanılır.  
  
-   Yönü (yatay ve dikey) yazma bağımsız yazı tipi adı olarak işlenir.  
  
-   Yazı tipi bağlama ve yazı tipi taşınabilir geri dönüş [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] bileşik yazı tipi teknolojisi kullanılarak dosya. Bileşik yazı tiplerinin tam aralığı çok dilli yazı tipleri oluşumu için izin verin. Bileşik yazı tipleri, ayrıca eksik karakter görüntüleme engelleyen bir mekanizma sağlar. Daha fazla bilgi için konusundaki yorumlara bakın <xref:System.Windows.Media.FontFamily> sınıfı.  
  
-   Bir grup tek dili yazı tipi kullanarak bileşik yazı oluşturulan uluslararası yazı tipleri. Birden çok dil için yazı tiplerini geliştirirken kaynak maliyetleri kaydeder.  
  
-   Bileşik yazı tipleri, böylece belge taşınabilirliği sağlayan bir belgeye katıştırılır. Daha fazla bilgi için konusundaki yorumlara bakın <xref:System.Windows.Media.FontFamily> sınıfı.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Yeni metin uygulama programlama arabirimleri (API)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] birkaç metin sağlar [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] geliştiricilerin uygulamalarında metin dahil olmak üzere kullanın. Bunlar [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] üç kategoriye ayrılır:  
  
-   **Düzen ve kullanıcı arabirimi**. Genel metin denetimleri için [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
-   **Basit Metin çizim**. Nesneleri doğrudan metin çizme sağlar.  
  
-   **Gelişmiş metin biçimlendirme**. Bir özel metin altyapısı olanak tanır.  
  
### <a name="layout-and-user-interface"></a>Düzen ve kullanıcı arabirimi  
 En üst düzeyde işlevsellik, metin [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] ortak sağlamak [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] gibi denetimler <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, ve <xref:System.Windows.Controls.TextBox>. Bu denetimlerin temel sağlamak [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] öğeleri içinde bir uygulama ve teklif sunmak ve metin ile etkileşim kurmak için kolay bir yol. Gibi denetimler <xref:System.Windows.Controls.RichTextBox> ve <xref:System.Windows.Controls.PasswordBox> etkinleştir daha gelişmiş veya özel metin işleme. Gibi sınıfları <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, ve <xref:System.Windows.Documents.TextPointer> yararlı metin düzenlemesini etkinleştirin. Bunlar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] denetimleri sağlar özellikleri gibi <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, ve <xref:System.Windows.Controls.Control.FontStyle%2A>, metin işlemek için kullanılan yazı tipi denetlemenize olanak tanır.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Bit eşlem efektleri ve dönüşümler Yazı efektleri  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] metnin görsel açıdan ilgi çekici kullanır, bit eşlem efektleri ve dönüşümler Yazı efektleri gibi kullandığı özellikler tarafından oluşturmanıza olanak sağlar. Aşağıdaki örnek, tipik bir metne uygulanacak gölge etkisi türünü gösterir.  
  
 ![Metin gölgesinin Yumuşaklık ile &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Gölge metin  
  
 Aşağıdaki örnek, bir gölge efektini ve metin uygulanan gürültü gösterir.  
  
 ![Metin gölgesinin gürültü ile](../../../../docs/framework/wpf/advanced/media/shadowtext04.jpg "ShadowText04")  
Gölge ve gürültü metin  
  
 Aşağıdaki örnek, metin için uygulanan bir dış parlaklık efekti gösterir.  
  
 ![Metin gölgesinin OuterGlowBitmapEffect kullanarak](../../../../docs/framework/wpf/advanced/media/shadowtext05.jpg "ShadowText05")  
Dış parlaklık efekti metin  
  
 Aşağıdaki örnek metni uygulanan bir bulanıklaştırma etkisini gösterir.  
  
 ![Metin gölgesinin BlurBitmapEffect kullanarak](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Bulanıklaştırma etkisi olan metin  
  
 Aşağıdaki örnek, % 150 x ekseni boyunca ölçeği metnin ikinci satırı ve y ekseni boyunca % 150 ölçeklendirilmiş metin üçüncü satır gösterir.  
  
 ![ScaleTransform kullanılarak ölçeklendirilen metin](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
ScaleTransform kullanarak metin  
  
 Aşağıdaki örnek x ekseni boyunca Eğilmiş metin gösterir.  
  
 ![SkewTransform kullanılarak Eğilmiş metin](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
SkewTransform kullanarak metin  
  
 A <xref:System.Windows.Media.TextEffect> nesnedir metne metin dizesindeki karakterlerin bir veya daha fazla grup olarak davranmanıza imkan tanıyan bir yardımcı nesnesi. Aşağıdaki örnek, tek bir karakteri Döndürülmüş gösterir. Her karakter, 1 saniyelik aralıklarla bağımsız olarak döndürülür.  
  
 ![Ekran döndürme metin metin etkisinin](../../../../docs/framework/wpf/advanced/media/texteffect01.jpg "TextEffect01")  
Bir döndürme metin efekt animasyonu örneği  
  
#### <a name="using-flow-documents"></a>Akış belgeleri kullanma  
 Ortak yanı sıra [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] denetimleri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] metin sunu için bir düzen denetimi sunar — <xref:System.Windows.Documents.FlowDocument> öğesi. <xref:System.Windows.Documents.FlowDocument> Birlikte öğesi <xref:System.Windows.Controls.DocumentViewer> öğe, metin düzeni gereksinimleri değişen ile büyük miktarda bir denetim sağlar. Düzen denetimleri Gelişmiş tipografi erişim sağlar <xref:System.Windows.Documents.Typography> nesne ve yazı tipi ile ilgili diğer özellikleri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] kontrol eder.  
  
 Aşağıdaki örnek, barındırılan içerik metni gösterir. bir <xref:System.Windows.Controls.FlowDocumentReader>, arama, gezinti, sayfalandırma ve Destek ölçeklendirme içeriği sağlar.  
  
 ![Örnek ekran görüntüsü kullanarak OpenType yazı tipleri](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF_03")  
İçinde bir FlowDocumentReader barındırılan metin  
  
 Daha fazla bilgi için [WPF'deki Belgeler](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Basit metin çizme  
 Doğrudan metin çizme [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanarak nesneleri <xref:System.Windows.Media.DrawingContext.DrawText%2A> yöntemi <xref:System.Windows.Media.DrawingContext> nesne. Bu yöntemi kullanmak için oluşturduğunuz bir <xref:System.Windows.Media.FormattedText> nesne. Bu nesne, ayrı ayrı metindeki her karakter biçimlendirilebilir, çok satırlı metin çizme sağlar. İşlevselliğini <xref:System.Windows.Media.FormattedText> nesne Win32 API DrawText bayrakları işlevselliğinin içerir. Ayrıca, <xref:System.Windows.Media.FormattedText> nesnesi üç nokta görüntülendiği metin sınırlarının aştığında, üç nokta desteği gibi işlevsellik içerir. Aşağıdaki örnek, uygulanan ikinci ve üçüncü sözcükleri doğrusal gradyan dahil olmak üzere çeşitli biçimlerde olan metni gösterir.  
  
 ![FormattedText nesnesi kullanılarak görüntülenen metin](../../../../docs/framework/wpf/advanced/media/formattedtext01.jpg "FormattedText01")  
Görüntülenen metni BiçimlendirilmişMetin nesnesi kullanma  
  
 Biçimlendirilmiş metin dönüştürebilirsiniz <xref:System.Windows.Media.Geometry> görsel metin ilginç diğer tür oluşturmanızı sağlayan nesneler. Örneğin, aşağıdakileri oluşturabilirsiniz bir <xref:System.Windows.Media.Geometry> nesne tabanlı bir metin dizesinin çerçevesinde.  
  
 ![Doğrusal gradyan fırçası kullanma metin anahat](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Metin anahat doğrusal gradyan fırçası kullanma  
  
 Aşağıdaki örnekler, ilgi çekici görsel efektler vuruş dolgu ve dönüştürülen metin vurgulama değiştirerek oluşturmanın birkaç yolu gösterilmektedir.  
  
 ![Metin doldurup için farklı renklerde](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Fırça darbesi ve dolgu farklı renkleri ayarlama örneği  
  
 ![Resim fırçası uygulandığı metinle](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Bir resim fırçası uygulandığı örneği  
  
 ![Resim fırçası uygulandığı metinle](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Fırça darbesi ve vurgulamaya uygulanan bir resim fırçası örneği  
  
 Daha fazla bilgi için <xref:System.Windows.Media.FormattedText> nesne, bkz: [çizim biçimlendirilmiş metin](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Gelişmiş Metin Biçimlendirme  
 En gelişmiş düzeyde metnin [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanarak özel metin düzenini oluşturma olanağı sunan <xref:System.Windows.Media.TextFormatting.TextFormatter> nesne ve diğer türleri <xref:System.Windows.Media.TextFormatting> ad alanı. <xref:System.Windows.Media.TextFormatting.TextFormatter> Ve ilişkili sınıfları, karakter biçimlerini, stilleri, kendi tanımını destekleyen özel metin düzenini uygulamak için satır kesme kuralları ve diğer düzen özellikleri için Uluslararası metin izin verir. İstediğiniz varsayılan uygulamasını geçersiz kılmak çok az sayıda durumlar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] metin düzeni desteği. Bununla birlikte, metin denetim ya da uygulama düzenleme oluşturuyorsanız, varsayılandan farklı bir uygulama gerektirebilir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uygulaması.  
  
 Geleneksel bir metin aksine [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> metin düzeni istemcisi kümesi geri çağırma yöntemleri ile etkileşime geçer. Bu yöntemleri uygulaması sağlamak için istemcinin gerektirir <xref:System.Windows.Media.TextFormatting.TextSource> sınıfı. Aşağıdaki diyagram, istemci uygulama arasındaki metin düzeni etkileşimi gösterir ve <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Metin düzeni istemcisi ve TextFormatter diyagramı](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Uygulama TextFormatter arasındaki etkileşimi  
  
 Özel metin düzenini oluşturma hakkında daha fazla ayrıntı için bkz. [Gelişmiş metin biçimlendirme](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Media.FormattedText>  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>  
 [ClearType Genel Bakışı](../../../../docs/framework/wpf/advanced/cleartype-overview.md)  
 [OpenType Yazı Tipi Özellikleri](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [Biçimlendirilmiş Metin Çizme](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [Gelişmiş Metin Biçimlendirme](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)  
 [Metin](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Microsoft tipografi](https://www.microsoft.com/typography/default.mspx)
