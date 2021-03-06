---
title: SQL Server CLR tümleştirmesine giriş
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: df5ead7d640446a3832b485ecf82cd4a2a11b1fb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523011"
---
# <a name="introduction-to-sql-server-clr-integration"></a>SQL Server CLR tümleştirmesine giriş
Ortak dil çalışma zamanı (CLR), Microsoft .NET Framework kalbidir ve tüm .NET Framework kod yürütme ortamı sağlar. CLR içinde çalışan kod, yönetilen kod olarak adlandırılır. CLR, ayırma ve bellek, tür güvenliği, özel durum işleme, iş parçacığı yönetimi ve güvenlik zorlama yönetme çeşitli işlevleri ve tam zamanında (JIT) derleme dahil olmak üzere, program yürütme için gerekli hizmetleri sağlar.  
  
 Microsoft SQL Server (CLR tümleştirme olarak adlandırılır) barındırılan CLR ile saklı yordamlar, Tetikleyiciler, kullanıcı tanımlı işlevleri, kullanıcı tanımlı türler ve kullanıcı tanımlı toplamlarda yönetilen kod yazabilirsiniz. Yürütme önce yerel kod için yönetilen kodu derler olduğundan, bazı senaryolarda önemli performans artışları elde edebilirsiniz.  
  
 Yönetilen kod kullandığı kod erişim güvenliği (CAS), kodu bağlantıları ve belirli işlemleri gerçekleştirmeyi derlemeleri önlemek için uygulama etki alanları. Yönetilen kod güvenli ve veritabanı sunucusu ve işletim sistemi güvenliğinin aşılması önlemeye yardımcı olmak için CAS SQL Server kullanır.  
  
 Bu bölümde, SQL Server CLR Tümleştirmesi ile programlamaya başlamak için yeterli bilgi yalnızca sağlamaya yöneliktir ve kapsamlı olacak şekilde tasarlanmamıştır. Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü kullandığınız SQL Server sürümü için bkz.  
  
 **SQL Server Çevrimiçi Kitapları**  
  
-   [Ortak dil çalışma zamanı (CLR) tümleştirme genel bakış](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a>CLR tümleştirmesini etkinleştirme  
 Ortak dil çalışma zamanı (CLR) tümleştirme özelliği, Microsoft SQL Server'da varsayılan olarak kapalıdır ve CLR tümleştirmesini kullanılarak yüklenen nesneler kullanmak için etkinleştirilmesi gerekir. Transact-SQL kullanarak CLR tümleştirmesini etkinleştirmek için `clr enabled` seçeneği `sp_configure` gösterildiği saklı yordam:  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 Ayarlayarak CLR tümleştirmesini devre dışı bırakabilirsiniz `clr enabled` seçeneğini 0. CLR tümleştirmesini devre dışı bıraktığınızda, SQL Server CLR tüm yordamları yürütme durdurur ve tüm uygulama etki alanları kaldırır.  
  
 Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü kullandığınız SQL Server sürümü için bkz.  
  
 **SQL Server Çevrimiçi Kitapları**  
  
-   [CLR tümleştirmesini etkinleştirme](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a>Bir CLR derlemesi dağıtma  
 CLR yöntemleri test ve test sunucusunda doğrulandı sonra dağıtım betiğini kullanarak üretim sunucularına dağıtılabilir. Dağıtım betiği, el ile veya SQL Server Management Studio kullanılarak oluşturulabilir. Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü kullandığınız SQL Server sürümü için bkz.  
  
 **SQL Server Çevrimiçi Kitapları**  
  
1.  [CLR veritabanı nesneleri dağıtma](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a>CLR tümleştirme güvenliği  
 Microsoft .NET Framework ortak dil çalışma zamanı (CLR) ile Microsoft SQL Server Tümleştirme güvenlik modelinin yönetir ve farklı içinde SQL Server çalıştıran CLR ve CLR olmayan nesneler arasında erişim güvenliğini sağlar. Bu nesneler, bir Transact-SQL deyimi veya server çalıştıran başka bir CLR nesnesi tarafından çağrılabilir.  
  
 Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü kullandığınız SQL Server sürümü için bkz.  
  
 **SQL Server Çevrimiçi Kitapları**  
  
-   [CLR tümleştirme güvenliği](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a>Bir CLR derlemesi hata ayıklama  
 Microsoft SQL Server Transact-SQL ve ortak dil çalışma zamanı (CLR) nesneleri veritabanındaki hata ayıklama için destek sağlar. Diller arasında çalışan hata ayıklama: kullanıcılar adım sorunsuz bir şekilde CLR nesnelerini Transact-SQL'den ve bunun tersi de geçerlidir.  
  
 Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü kullandığınız SQL Server sürümü için bkz.  
  
 **SQL Server Çevrimiçi Kitapları**  
  
-   [Hata ayıklama CLR veritabanı nesneleri](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda SQL Server 2005 nesneleri oluşturma](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Kod Erişimi Güvenliği ve ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi](https://go.microsoft.com/fwlink/?LinkId=217917)
