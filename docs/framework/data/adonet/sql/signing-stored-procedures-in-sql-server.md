---
title: "Saklı yordamlar SQL Server'daki imzalama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 86c2a6c3f2c84c931df15e4809980a76cb6d826c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="86bce-102">Saklı yordamlar SQL Server'daki imzalama</span><span class="sxs-lookup"><span data-stu-id="86bce-102">Signing Stored Procedures in SQL Server</span></span>
<span data-ttu-id="86bce-103">Saklı yordam bir sertifika veya asimetrik anahtar ile oturum açabilir.</span><span class="sxs-lookup"><span data-stu-id="86bce-103">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="86bce-104">Sahiplik zincirleme aracılığıyla izinleri devralınan olamaz veya sahiplik zinciri, dinamik SQL gibi bozuk olduğunda bu senaryoları için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="86bce-104">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="86bce-105">Sonra sertifikayı kullanıcı saklı yordamı erişmesi nesneleri izin verme sertifikayla eşleştirilmiş bir kullanıcı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="86bce-105">You then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>  
  
 <span data-ttu-id="86bce-106">Saklı yordam çalıştırıldığında, SQL Server çağıran olanlar sertifika kullanıcının izinleriyle birleştirir.</span><span class="sxs-lookup"><span data-stu-id="86bce-106">When the stored procedure is executed, SQL Server combines the permissions of the certificate user with those of the caller.</span></span> <span data-ttu-id="86bce-107">Aksine EXECUTE AS yan TÜMCESİNİ yordamı yürütme bağlamı değişmez.</span><span class="sxs-lookup"><span data-stu-id="86bce-107">Unlike the EXECUTE AS clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="86bce-108">Bu dönüş oturum açma yerleşik işlevler ve kullanıcı adları sertifika kullanıcı adı değil arayan adını döndürür.</span><span class="sxs-lookup"><span data-stu-id="86bce-108">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>  
  
 <span data-ttu-id="86bce-109">Dijital imza imzalayan özel anahtar ile şifrelenmiş veri Özet ' dir.</span><span class="sxs-lookup"><span data-stu-id="86bce-109">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="86bce-110">Özel anahtar dijital imza, taşıyıcı veya sahibi benzersiz olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="86bce-110">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="86bce-111">Saklı yordamlar, fonksiyon veya tetikleyici imzalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="86bce-111">You can sign stored procedures, functions, or triggers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86bce-112">Sunucu düzeyi izinleri vermek için ana veritabanında bir sertifika oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="86bce-112">You can create a certificate in the master database to grant server-level permissions.</span></span>  
  
## <a name="creating-certificates"></a><span data-ttu-id="86bce-113">Sertifikaları oluşturma</span><span class="sxs-lookup"><span data-stu-id="86bce-113">Creating Certificates</span></span>  
 <span data-ttu-id="86bce-114">Saklı yordam bir sertifika ile oturum açtığınızda, saklı yordam kod şifrelenmiş karmasını oluşan bir veri özeti özel anahtarı kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="86bce-114">When you sign a stored procedure with a certificate, a data digest consisting of the encrypted hash of the stored procedure code is created using the private key.</span></span> <span data-ttu-id="86bce-115">Çalışma zamanında veri Özet ortak anahtarla şifresi ve saklı yordam karma değeriyle karşılaştırılır.</span><span class="sxs-lookup"><span data-stu-id="86bce-115">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="86bce-116">Böylece dijital imza artık eşleşir saklı yordamı değiştirme karma değerini geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="86bce-116">Modifying the stored procedure invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="86bce-117">Bu saklı yordam kodunu değiştirme Access'ten özel anahtara sahip olmayan birisi önler.</span><span class="sxs-lookup"><span data-stu-id="86bce-117">This prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="86bce-118">Bu nedenle, yordam her değiştirdiğinizde yeniden oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="86bce-118">Therefore you must re-sign the procedure each time you modify it.</span></span>  
  
 <span data-ttu-id="86bce-119">Bir modül oturum açma dahil edilen dört adım vardır:</span><span class="sxs-lookup"><span data-stu-id="86bce-119">There are four steps involved in signing a module:</span></span>  
  
1.  <span data-ttu-id="86bce-120">Transact-SQL kullanarak bir sertifika oluşturmak `CREATE CERTIFICATE [certificateName]` deyimi.</span><span class="sxs-lookup"><span data-stu-id="86bce-120">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="86bce-121">Bu deyim bir başlangıç ve bitiş tarihi ve bir parola ayarlamak için birkaç seçenek vardır.</span><span class="sxs-lookup"><span data-stu-id="86bce-121">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="86bce-122">Bir yıl varsayılan sona erme tarihi olan</span><span class="sxs-lookup"><span data-stu-id="86bce-122">The default expiration date is one year</span></span>  
  
2.  <span data-ttu-id="86bce-123">Transact-SQL kullanarak bu sertifikayla ilişkili bir veritabanı kullanıcısı oluşturmalıdır `CREATE USER [userName] FROM CERTIFICATE [certificateName]` deyimi.</span><span class="sxs-lookup"><span data-stu-id="86bce-123">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="86bce-124">Bu kullanıcı yalnızca veritabanında var ve bir oturum ile ilişkili değil.</span><span class="sxs-lookup"><span data-stu-id="86bce-124">This user exists in the database only and is not associated with a login.</span></span>  
  
3.  <span data-ttu-id="86bce-125">Sertifika kullanıcı veritabanı nesneleri üzerinde gerekli izinleri verin.</span><span class="sxs-lookup"><span data-stu-id="86bce-125">Grant the certificate user the required permissions on the database objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86bce-126">Bir sertifika verme deyimi kullanarak iptal izinleri olan bir kullanıcı için izinleri olamaz.</span><span class="sxs-lookup"><span data-stu-id="86bce-126">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="86bce-127">REDDETME her zaman izin ver çağıran sertifika kullanıcıya verilen izinler devralmayı engelleme önceliklidir.</span><span class="sxs-lookup"><span data-stu-id="86bce-127">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>  
  
1.  <span data-ttu-id="86bce-128">Yordam Transact-SQL kullanarak sertifika ile oturum `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` deyimi.</span><span class="sxs-lookup"><span data-stu-id="86bce-128">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="86bce-129">Dış Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="86bce-129">External Resources</span></span>  
 <span data-ttu-id="86bce-130">Daha fazla bilgi için aşağıdaki kaynaklara bakın.</span><span class="sxs-lookup"><span data-stu-id="86bce-130">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="86bce-131">Kaynak</span><span class="sxs-lookup"><span data-stu-id="86bce-131">Resource</span></span>|<span data-ttu-id="86bce-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="86bce-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="86bce-133">[İmzalama Modülü](http://go.microsoft.com/fwlink/?LinkId=98590) SQL Server Çevrimiçi Kitapları'nda</span><span class="sxs-lookup"><span data-stu-id="86bce-133">[Module Signing](http://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server Books Online</span></span>|<span data-ttu-id="86bce-134">İmzalama, bir örnek senaryo ve ilgili Transact-SQL konulara bağlantılar sağlayan modülü açıklar.</span><span class="sxs-lookup"><span data-stu-id="86bce-134">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL topics.</span></span>|  
|<span data-ttu-id="86bce-135">[Saklı yordamlar bir sertifika ile imzalama](http://msdn.microsoft.com/library/bb283630.aspx) SQL Server Çevrimiçi Kitapları'nda</span><span class="sxs-lookup"><span data-stu-id="86bce-135">[Signing Stored Procedures with a Certificate](http://msdn.microsoft.com/library/bb283630.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="86bce-136">Saklı yordam bir sertifika ile imzalamak için bir öğretici sağlar.</span><span class="sxs-lookup"><span data-stu-id="86bce-136">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86bce-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="86bce-137">See Also</span></span>  
 [<span data-ttu-id="86bce-138">ADO.NET uygulamalarının güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="86bce-138">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="86bce-139">SQL Server güvenlik genel bakış</span><span class="sxs-lookup"><span data-stu-id="86bce-139">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="86bce-140">SQL Server'daki uygulama güvenlik senaryoları</span><span class="sxs-lookup"><span data-stu-id="86bce-140">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="86bce-141">Saklı yordamlar SQL Server'daki izinlerle yönetme</span><span class="sxs-lookup"><span data-stu-id="86bce-141">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="86bce-142">SQL Server'da güvenli dinamik SQL yazma</span><span class="sxs-lookup"><span data-stu-id="86bce-142">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="86bce-143">Kimliğe bürünme SQL Server'daki izinlerle özelleştirme</span><span class="sxs-lookup"><span data-stu-id="86bce-143">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [<span data-ttu-id="86bce-144">Saklı yordamlar verilerle değiştirme</span><span class="sxs-lookup"><span data-stu-id="86bce-144">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="86bce-145">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="86bce-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)