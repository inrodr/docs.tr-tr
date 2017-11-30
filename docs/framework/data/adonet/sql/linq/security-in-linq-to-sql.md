---
title: "LINQ-SQL güvenlik"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 27e40221c22a91bb2a8c40ec4bcfd663eb05aaef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="6fcb6-102">LINQ-SQL güvenlik</span><span class="sxs-lookup"><span data-stu-id="6fcb6-102">Security in LINQ to SQL</span></span>
<span data-ttu-id="6fcb6-103">Güvenlik riskleri, her zaman bir veritabanına bağlandığında yok.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-103">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="6fcb6-104">LINQ-SQL SQL Server'daki verilerle çalışmak için bazı yeni yollarını içerebilir ancak herhangi bir ek güvenlik mekanizması sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-104">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="6fcb6-105">Erişim denetimi ve kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="6fcb6-105">Access Control and Authentication</span></span>  
 <span data-ttu-id="6fcb6-106">LINQ-SQL, kendi kullanıcı model veya kimlik doğrulama mekanizmaları yok.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-106">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="6fcb6-107">Veritabanı, veritabanı tabloları, görünümleri ve nesne modeline eşlenen saklı yordamlar erişimi denetlemek için SQL Server güvenlik kullanın.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-107">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="6fcb6-108">Kullanıcılar için gereken en düşük erişim ve güçlü parolalar için kullanıcı kimlik doğrulaması gerektirir.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-108">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="6fcb6-109">Eşleme ve şema bilgileri</span><span class="sxs-lookup"><span data-stu-id="6fcb6-109">Mapping and Schema Information</span></span>  
 <span data-ttu-id="6fcb6-110">Nesne modeli veya dış eşleme dosyası SQL CLR türü eşleme ve veritabanı şeması bilgileri dosya sistemindeki tüm bu dosyalara erişimi için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-110">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="6fcb6-111">Şema bilgileri nesne modeli veya dış eşleme dosyası erişebilen tüm kullanılabilir olacağını düşünün. Şema bilgileri için daha yaygın erişimi engellemek için kaynak dosyaları ve eşleme dosyaları korumak için dosya güvenlik mekanizmaları kullanın.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-111">Assume that schema information will be available to all who can access the object model or external mapping file.To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="6fcb6-112">Bağlantı dizeleri</span><span class="sxs-lookup"><span data-stu-id="6fcb6-112">Connection Strings</span></span>  
 <span data-ttu-id="6fcb6-113">Bağlantı dizeleri parolaları kullanmanızı mümkün olduğunca kaçınılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-113">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="6fcb6-114">Yalnızca bir bağlantı dizesi, kendi içinde bir güvenlik riski oluşturur, ancak bağlantı dizesini de düz metin olarak nesne modeli ya da dış eşleme dosyası Nesne İlişkisel Tasarımcısı veya SQLMetal komut satırı aracını kullanırken eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-114">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="6fcb6-115">(Bu bağlantı dizesinde varsa) nesne modeli veya dış eşleme dosyası dosya sistemi üzerinden erişimi olan herkes bağlantı parolası görebilir.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-115">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="6fcb6-116">Bu tür riskleri en aza indirmek için güvenilen bir bağlantıyla yapmak için tümleşik güvenliğini kullan [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fcb6-116">To minimize such risks, use integrated security to make a trusted connection with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6fcb6-117">Bu yaklaşımı kullanarak, bir parola bağlantı dizesinde depolamak gerekmez.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-117">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="6fcb6-118">Daha fazla bilgi için bkz: [SQL Server Güvenlik](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span><span class="sxs-lookup"><span data-stu-id="6fcb6-118">For more information, see [SQL Server Security](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span></span>  
  
 <span data-ttu-id="6fcb6-119">Tümleşik güvenlik olmaması durumunda bir düz metin parola bağlantı dizesinde gerekir.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-119">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="6fcb6-120">Artan düzende risk, bağlantı dizenizi güvenli hale getirmek için en iyi yolu aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="6fcb6-120">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
-   <span data-ttu-id="6fcb6-121">Tümleşik güvenlik kullanın.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-121">Use integrated security.</span></span>  
  
-   <span data-ttu-id="6fcb6-122">Bağlantı dizeleri parolalarla güvenli ve bağlantı dizeleri geçici geçirme en aza.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-122">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
-   <span data-ttu-id="6fcb6-123">Kullanım bir <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> Etkilenme süresini sınırlar bu yana bir bağlantı dizesi yerine sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-123">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="6fcb6-124">LINQ-SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> sınıfı kullanılarak oluşturulabilir bir <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-124">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
-   <span data-ttu-id="6fcb6-125">Yaşam süresi en aza indirmek ve noktaya tüm bağlantı dizeleri için dokunun.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-125">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fcb6-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6fcb6-126">See Also</span></span>  
 [<span data-ttu-id="6fcb6-127">Arka plan bilgileri</span><span class="sxs-lookup"><span data-stu-id="6fcb6-127">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="6fcb6-128">Sık sorulan sorular</span><span class="sxs-lookup"><span data-stu-id="6fcb6-128">Frequently Asked Questions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)