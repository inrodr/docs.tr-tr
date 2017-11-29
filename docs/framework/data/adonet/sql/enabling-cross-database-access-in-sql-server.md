---
title: "SQL Server'da veritabanları arası erişimini etkinleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 720c4c8eecc20b971eb9ecf1abb85da1e72e3c54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-cross-database-access-in-sql-server"></a><span data-ttu-id="2a70b-102">SQL Server'da veritabanları arası erişimini etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="2a70b-102">Enabling Cross-Database Access in SQL Server</span></span>
<span data-ttu-id="2a70b-103">Veritabanları arası sahiplik zincirleme nesneleri başka bir veritabanındaki bir veritabanı yordamda bağlı olduğunda oluşur.</span><span class="sxs-lookup"><span data-stu-id="2a70b-103">Cross-database ownership chaining occurs when a procedure in one database depends on objects in another database.</span></span> <span data-ttu-id="2a70b-104">Tüm nesne sahiplerini aynı oturum açma hesabıyla eşlenir kırık sahiplik zinciri gerektirir veritabanları arası sahiplik zinciri içinde tek bir veritabanı, sahipliği zincirleme olarak aynı şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="2a70b-104">A cross-database ownership chain works in the same way as ownership chaining within a single database, except that an unbroken ownership chain requires that all the object owners are mapped to the same login account.</span></span> <span data-ttu-id="2a70b-105">Kaynak veritabanındaki kaynak nesnesi ve hedef veritabanlarına hedef nesneleri aynı oturum açma hesabı tarafından sahip olunan, SQL Server hedef nesneler üzerindeki izinleri denetlemez.</span><span class="sxs-lookup"><span data-stu-id="2a70b-105">If the source object in the source database and the target objects in the target databases are owned by the same login account, SQL Server does not check permissions on the target objects.</span></span>  
  
## <a name="off-by-default"></a><span data-ttu-id="2a70b-106">Varsayılan olarak kapalıdır</span><span class="sxs-lookup"><span data-stu-id="2a70b-106">Off By Default</span></span>  
 <span data-ttu-id="2a70b-107">Veritabanları arasında sahipliği zincirleme varsayılan olarak kapalıdır.</span><span class="sxs-lookup"><span data-stu-id="2a70b-107">Ownership chaining across databases is turned off by default.</span></span> <span data-ttu-id="2a70b-108">Microsoft, aşağıdaki güvenlik risklerini kullanıma sunan çünkü veritabanları arası sahiplik zincirleme devre dışı bırakmak önerir:</span><span class="sxs-lookup"><span data-stu-id="2a70b-108">Microsoft recommends that you disable cross-database ownership chaining because it exposes you to the following security risks:</span></span>  
  
-   <span data-ttu-id="2a70b-109">Veritabanı sahipleri ve üyeleri `db_ddladmin` veya `db_owners` veritabanı rolleri, diğer kullanıcılar tarafından sahip olunan nesneler oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="2a70b-109">Database owners and members of the `db_ddladmin` or the `db_owners` database roles can create objects that are owned by other users.</span></span> <span data-ttu-id="2a70b-110">Bu nesneler, büyük olasılıkla diğer veritabanlarındaki nesneler hedefleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2a70b-110">These objects can potentially target objects in other databases.</span></span> <span data-ttu-id="2a70b-111">Bu veritabanları arası sahiplik zincirleme etkinleştirirseniz, bu kullanıcılar tüm veritabanlarındaki veriler ile tam olarak güvenmelidir anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="2a70b-111">This means that if you enable cross-database ownership chaining, you must fully trust these users with data in all databases.</span></span>  
  
-   <span data-ttu-id="2a70b-112">CREATE DATABASE iznine sahip kullanıcılar, yeni veritabanları oluşturabilir ve varolan veritabanları ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2a70b-112">Users with CREATE DATABASE permission can create new databases and attach existing databases.</span></span> <span data-ttu-id="2a70b-113">Veritabanları arası sahiplik zincirleme etkinse, bu kullanıcılar oluşturdukları yeni oluşturulan veya ekli veritabanlarından bunlar ayrıcalıklara sahip olmayabilir diğer veritabanlarındaki nesnelere erişebilir.</span><span class="sxs-lookup"><span data-stu-id="2a70b-113">If cross-database ownership chaining is enabled, these users can access objects in other databases that they might not have privileges in from the newly created or attached databases that they create.</span></span>  
  
## <a name="enabling-cross-database-ownership-chaining"></a><span data-ttu-id="2a70b-114">Veritabanları arası sahiplik zincirleme etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="2a70b-114">Enabling Cross-database Ownership Chaining</span></span>  
 <span data-ttu-id="2a70b-115">Veritabanları arası sahiplik zincirleme yüksek ayrıcalıklı kullanıcıların tam olarak güvenebildiğiniz ortamlarda yalnızca etkinleştirilmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2a70b-115">Cross-database ownership chaining should only be enabled in environments where you can fully trust highly-privileged users.</span></span> <span data-ttu-id="2a70b-116">Tüm veritabanları için veya seçmeli olarak kullanarak belirli veritabanları için Kurulum sırasında yapılandırılabilir [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] komutları `sp_configure` ve `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="2a70b-116">It can be configured during setup for all databases, or selectively for specific databases using the [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] commands `sp_configure` and `ALTER DATABASE`.</span></span>  
  
 <span data-ttu-id="2a70b-117">Veritabanları arası sahiplik zincirleme seçmeli olarak yapılandırmak için kullanın `sp_configure` sunucu için devre dışı bırakma.</span><span class="sxs-lookup"><span data-stu-id="2a70b-117">To selectively configure cross-database ownership chaining, use `sp_configure` to turn it off for the server.</span></span> <span data-ttu-id="2a70b-118">Ardından yalnızca gerektiren veritabanları için zincirleme veritabanları arası sahiplik yapılandırmak için SET DB_CHAINING ON ile ALTER DATABASE komutunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="2a70b-118">Then use the ALTER DATABASE command with SET DB_CHAINING ON to configure cross-database ownership chaining for only the databases that require it.</span></span>  
  
 <span data-ttu-id="2a70b-119">Aşağıdaki örnek veritabanları arası sahiplik tüm veritabanları için zincirleme açar:</span><span class="sxs-lookup"><span data-stu-id="2a70b-119">The following sample turns on cross-database ownership chaining for all databases:</span></span>  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 <span data-ttu-id="2a70b-120">Aşağıdaki örnek veritabanları arası sahiplik belirli veritabanları için zincirleme açar:</span><span class="sxs-lookup"><span data-stu-id="2a70b-120">The following sample turns on cross-database ownership chaining for specific databases:</span></span>  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a><span data-ttu-id="2a70b-121">Dinamik SQL</span><span class="sxs-lookup"><span data-stu-id="2a70b-121">Dynamic SQL</span></span>  
 <span data-ttu-id="2a70b-122">Veritabanları arası sahiplik zincirleme, aynı kullanıcı her iki veritabanı olmadığı sürece dinamik olarak oluşturulan SQL deyimlerini yürütüldüğü durumlarda çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="2a70b-122">Cross-database ownership chaining does not work in cases where dynamically created SQL statements are executed unless the same user exists in both databases.</span></span> <span data-ttu-id="2a70b-123">Bu geçici çözüm [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] başka bir veritabanındaki verilere erişen bir saklı yordam oluşturarak ve yordam her iki veritabanlarınızda var olan bir sertifika ile imzalama.</span><span class="sxs-lookup"><span data-stu-id="2a70b-123">You can work around this in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] by creating a stored procedure that accesses data in another database and signing the procedure with a certificate that exists in both databases.</span></span> <span data-ttu-id="2a70b-124">Bu kullanıcılar veritabanı erişimi ya da izin vermeden yordamı tarafından kullanılan veritabanı kaynaklarına erişmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="2a70b-124">This gives users access to the database resources used by the procedure without granting them database access or permissions.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="2a70b-125">Dış Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="2a70b-125">External Resources</span></span>  
 <span data-ttu-id="2a70b-126">Daha fazla bilgi için aşağıdaki kaynaklara bakın.</span><span class="sxs-lookup"><span data-stu-id="2a70b-126">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="2a70b-127">Kaynak</span><span class="sxs-lookup"><span data-stu-id="2a70b-127">Resource</span></span>|<span data-ttu-id="2a70b-128">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2a70b-128">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2a70b-129">[EXECUTE AS kullanarak veritabanı kimliğe bürünme genişletme](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) ve [arası seçeneği zincirleme DB sahipliği](http://msdn.microsoft.com/library/ms188694.aspx) [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Çevrimiçi Kitapları.</span><span class="sxs-lookup"><span data-stu-id="2a70b-129">[Extending Database Impersonation by Using EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) and [Cross DB Ownership Chaining Option](http://msdn.microsoft.com/library/ms188694.aspx)[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>|<span data-ttu-id="2a70b-130">Konular açıklayan bir örneği için veritabanları arası sahiplik zincirleme yapılandırma [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a70b-130">Topics describe how to configure cross-database ownership chaining for an instance of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a70b-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2a70b-131">See Also</span></span>  
 [<span data-ttu-id="2a70b-132">ADO.NET uygulamalarının güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="2a70b-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="2a70b-133">SQL Server güvenlik genel bakış</span><span class="sxs-lookup"><span data-stu-id="2a70b-133">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="2a70b-134">Saklı yordamlar SQL Server'daki izinlerle yönetme</span><span class="sxs-lookup"><span data-stu-id="2a70b-134">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="2a70b-135">SQL Server'da güvenli dinamik SQL yazma</span><span class="sxs-lookup"><span data-stu-id="2a70b-135">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="2a70b-136">Saklı yordamlar SQL Server'daki imzalama</span><span class="sxs-lookup"><span data-stu-id="2a70b-136">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="2a70b-137">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="2a70b-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)