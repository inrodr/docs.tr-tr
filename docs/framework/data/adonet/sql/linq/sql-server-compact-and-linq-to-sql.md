---
title: SQL Server Compact ve LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 1229fcb285038875950776a924870c9be6bef13b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529994"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact ve LINQ to SQL
SQL Server Compact ile Visual Studio yüklü varsayılan bir veritabanıdır. Daha fazla bilgi için [PAVE üzerinden kullanarak SQL Server Compact (Visual Studio)](https://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 Bu konuda kullanımı, yapılandırma, özellik kümeleri ve kapsamı temel farklılıklar özetlenmiştir [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] destekler.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>SQL Server Compact LINQ to SQL ile ilgili özellikleri  
 Varsayılan olarak, SQL Server Compact için tüm Visual Studio sürümleri yüklenir ve bu nedenle ile kullanmak için geliştirme bilgisayarında kullanılabilir [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Ancak SQL Server Compact kullanan bir uygulama dağıtımını ve [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , SQL Server uygulama için farklıdır. SQL Server Compact .NET Framework'ün bir parçası değil ve bu nedenle uygulamayla paketlenmiş veya gerekir Microsoft sitesinden ayrı olarak indirilir.  
  
 Aşağıdaki özelliklere dikkat edin:  
  
-   SQL Server Compact veritabanı dosyaları (.sdf uzantısına) karşı doğrudan kullanılabilen bir DLL paketlenir.  
  
-   SQL Server Compact istemci uygulama ile aynı işlemde çalıştırır. SQL Server Compact ile iletişimi verimliliğini, bu nedenle SQL Server ile iletişim kurarken daha önemli ölçüde daha yüksek olabilir. Öte yandan, SQL Server Compact Katılımcısı giderlerini ile yönetilen ve yönetilmeyen kod arasındaki birlikte çalışabilirlik gerektirir.  
  
-   SQL Server Compact DLL'si boyutu küçüktür. Bu özellik, genel uygulama boyutunu azaltır.  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Çalışma zamanı ve SQLMetal komut satırı aracı SQL Server Compact destekler.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] SQL Server Compact desteklemez.  
  
## <a name="feature-set"></a>Özellik kümesi  
 SQL Server Compact özellik kümesini etkileyen aşağıdaki yollarla SQL Server özellik kümesini çok daha kolay [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uygulamalar:  
  
-   SQL Server Compact saklı yordamları veya görünümleri desteklemez.  
  
-   SQL Server Compact, yalnızca bir alt kümesini veri türleri ve SQL işlevleri destekler.  
  
-   SQL Server Compact, SQL yapıları yalnızca bir kısmını destekler.  
  
-   SQL Server Compact, en az bir iyileştirici sağlar. Bazı sorgular zaman aşımına uğrayabilir mümkündür.  
  
-   SQL Server Compact, kısmi güven desteklemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
