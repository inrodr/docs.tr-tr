---
title: 'Nasıl yapılır: Komut Satırı Derleyicisini Çağırma (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 0b835bb5654574a5aa6f32eede1e942b11e7dcb0
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932160"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Nasıl yapılır: Komut Satırı Derleyicisini Çağırma (Visual Basic)
Komut satırına, MS-DOS İstemi olarak da bilinen yürütülebilir dosyasının adını yazarak komut satırı derleyicisini çağırabilirsiniz. Windows komut istemi varsayılan derleme yaparsanız, yürütülebilir dosyanın tam yolunu yazmanız gerekir. Bu varsayılan davranışı geçersiz kılmak için Visual Studio Komut İstemi'ni kullanabilir veya PATH ortam değişkenini Değiştir. Her ikisi de, derleme adını yazarak herhangi bir dizinden derleme olanak tanır.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Visual Studio komut istemi kullanarak derleyici çağırmak için  
  
1.  Microsoft Visual Studio program grubu içinde Visual Studio Araçları program klasörü açın.  
  
2.  Visual Studio yüklüyse derleyici makinenizde, herhangi bir dizinden erişmek için Visual Studio Komut İstemi'ni kullanabilirsiniz.  
  
3.  Visual Studio Komut İstemi'ni çağırır.  
  
4.  Komut satırında `vbc.exe` *sourceFileName* yazıp ENTER tuşuna basın.  
  
     Örneğin, kaynak kodunuzu adlı dizinde depolanan `SourceFiles`, türü ve komut istemi açmak `cd SourceFiles` bu dizine gidin. Dizin adlı bir kaynak dosyası içeriyorsa `Source.vb`, yazarak derleme `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>PATH ortam değişkenine derleyicisi için Windows komut istemi ayarlamak için  
  
1.  Yerel diskinizde Vbc.exe bulmak için Windows Search özelliğini kullanın.  
  
     Derleyici bulunduğu dizinin tam adı, Windows dizin konumunu ve ".NET Framework'ün" sürüm bağlıdır. ".NET Framework'ün" birden fazla sürümü varsa, hangi sürümün (genellikle en son sürüm) kullanılacağını belirlemeniz gerekir.  
  
2.  Öğesinden, **Başlat** menüsünde sağ **Bilgisayarım**ve ardından **özellikleri** kısayol menüsünden.  
  
3.  Tıklayın **Gelişmiş** sekmesine ve ardından **ortam değişkenlerini**.  
  
4.  İçinde **sistem** değişkenleri bölmesinde **yolu** listesi ve **Düzenle**.  
  
5.  İçinde **düzenleme sistemi** değişken iletişim kutusunda, dizenin sonuna ekleme noktasını Taşı **değişken değeri** alan ve noktalı virgül (;) yazın ardından adım 1'de bulunan tam dizin adı.  
  
6.  Tıklayın **Tamam** yaptığınız düzenlemeleri onaylamak ve iletişim kutularını kapatmak için.  
  
     PATH ortam değişkenine değiştirdikten sonra Visual Basic Derleyicisi Windows komut isteminde herhangi bir dizinden bilgisayarda çalıştırabilirsiniz.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Windows komut istemi kullanarak derleyici çağırmak için  
  
1.  Gelen **Başlat** menüsünde tıklatın **Donatılar** klasörünü açın ve ardından açık **Windows Komut İstemi**.  
  
2.  Komut satırında `vbc.exe` *sourceFileName* yazıp ENTER tuşuna basın.  
  
     Örneğin, kaynak kodunuzu adlı dizinde depolanan `SourceFiles`, türü ve komut istemi açmak `cd SourceFiles` bu dizine gidin. Dizin adlı bir kaynak dosyası içeriyorsa `Source.vb`, yazarak derleme `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Koşullu Derleme](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
