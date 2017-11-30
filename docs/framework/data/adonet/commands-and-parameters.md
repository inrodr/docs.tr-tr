---
title: "Komutları ve parametreleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e1bfd3e88df4bd90cbcebfa645c2a50159f836db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="commands-and-parameters"></a><span data-ttu-id="f5a57-102">Komutları ve parametreleri</span><span class="sxs-lookup"><span data-stu-id="f5a57-102">Commands and Parameters</span></span>
<span data-ttu-id="f5a57-103">Bir veri kaynağına bağlantı kurulduktan sonra komutları yürütün ve sonuçları kullanarak veri kaynağının dönmek bir <xref:System.Data.Common.DbCommand> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="f5a57-103">After establishing a connection to a data source, you can execute commands and return results from the data source using a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="f5a57-104">Komut oluşturuculardan birine çalıştığınız .NET Framework veri sağlayıcısı kullanarak bir komut oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f5a57-104">You can create a command using one of the command constructors for the .NET Framework data provider you are working with.</span></span> <span data-ttu-id="f5a57-105">Oluşturucular, veri kaynağında yürütmek için bir SQL deyimi gibi isteğe bağlı bağımsız değişkenler gerçekleştirebileceğiniz bir <xref:System.Data.Common.DbConnection> nesnesi veya bir <xref:System.Data.Common.DbTransaction> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="f5a57-105">Constructors can take optional arguments, such as an SQL statement to execute at the data source, a <xref:System.Data.Common.DbConnection> object, or a <xref:System.Data.Common.DbTransaction> object.</span></span> <span data-ttu-id="f5a57-106">Bu nesneler komutu özelliklerini de yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f5a57-106">You can also configure those objects as properties of the command.</span></span> <span data-ttu-id="f5a57-107">Belirli bir bağlantısı kullanmak için bir komut oluşturabilirsiniz <xref:System.Data.Common.DbConnection.CreateCommand%2A> yöntemi bir `DbConnection` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="f5a57-107">You can also create a command for a particular connection using the <xref:System.Data.Common.DbConnection.CreateCommand%2A> method of a `DbConnection` object.</span></span> <span data-ttu-id="f5a57-108">Komutu tarafından yürütülen SQL deyimi kullanılarak yapılandırılabilir <xref:System.Data.Common.DbCommand.CommandText%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="f5a57-108">The SQL statement being executed by the command can be configured using the <xref:System.Data.Common.DbCommand.CommandText%2A> property.</span></span>  
  
 <span data-ttu-id="f5a57-109">.NET Framework ile dahil her .NET Framework veri sağlayıcısı sahip bir `Command` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="f5a57-109">Each .NET Framework data provider included with the .NET Framework has a `Command` object.</span></span> <span data-ttu-id="f5a57-110">OLE DB için .NET Framework veri sağlayıcısı içerir bir <xref:System.Data.OleDb.OleDbCommand> nesnesi, SQL Server için .NET Framework veri sağlayıcısı içerir bir <xref:System.Data.SqlClient.SqlCommand> nesne ODBC için .NET Framework veri sağlayıcısı içeren bir <xref:System.Data.Odbc.OdbcCommand> nesne ve .NET Framework Oracle için veri sağlayıcı içeren bir <xref:System.Data.OracleClient.OracleCommand> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="f5a57-110">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5a57-111">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="f5a57-111">In This Section</span></span>  
 [<span data-ttu-id="f5a57-112">Bir komutu yürütme</span><span class="sxs-lookup"><span data-stu-id="f5a57-112">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 <span data-ttu-id="f5a57-113">ADO.NET açıklar `Command` nesne ve nasıl sorgular ve bir veri kaynağına karşı komutları yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f5a57-113">Describes the ADO.NET `Command` object and how to use it to execute queries and commands against a data source.</span></span>  
  
 [<span data-ttu-id="f5a57-114">Yapılandırma parametreleri ve parametre veri türleri</span><span class="sxs-lookup"><span data-stu-id="f5a57-114">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 <span data-ttu-id="f5a57-115">İle çalışmayı açıklar `Command` yönü, veri türleri ve parametre söz dizimi dahil parametreleri.</span><span class="sxs-lookup"><span data-stu-id="f5a57-115">Describes working with `Command` parameters, including direction, data types, and parameter syntax.</span></span>  
  
 [<span data-ttu-id="f5a57-116">Komutları CommandBuilders ile oluşturma</span><span class="sxs-lookup"><span data-stu-id="f5a57-116">Generating Commands with CommandBuilders</span></span>](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 <span data-ttu-id="f5a57-117">Komut oluşturucuları için INSERT, UPDATE ve DELETE komutları otomatik olarak oluşturmak için nasıl kullanılacağını açıklar bir `DataAdapter` tek tablo SELECT komutu sahip.</span><span class="sxs-lookup"><span data-stu-id="f5a57-117">Describes how to use command builders to automatically generate INSERT, UPDATE, and DELETE commands for a `DataAdapter` that has a single-table SELECT command.</span></span>  
  
 [<span data-ttu-id="f5a57-118">Tek bir değer veritabanından alma</span><span class="sxs-lookup"><span data-stu-id="f5a57-118">Obtaining a Single Value from a Database</span></span>](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 <span data-ttu-id="f5a57-119">Nasıl kullanılacağını açıklar `ExecuteScalar` yöntemi bir `Command` nesnesi bir veritabanından döndürdüğünüz tek bir değer.</span><span class="sxs-lookup"><span data-stu-id="f5a57-119">Describes how to use the `ExecuteScalar` method of a `Command` object to return a single value from a database query.</span></span>  
  
 [<span data-ttu-id="f5a57-120">Verileri değiştirmek için komutları kullanarak</span><span class="sxs-lookup"><span data-stu-id="f5a57-120">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 <span data-ttu-id="f5a57-121">Bir veri sağlayıcısı saklı yordamları veya veri tanım dili (DDL) deyimlerini yürütmek için nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="f5a57-121">Describes how to use a data provider to execute stored procedures or data definition language (DDL) statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a57-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f5a57-122">See Also</span></span>  
 [<span data-ttu-id="f5a57-123">DataAdapters ve DataReader</span><span class="sxs-lookup"><span data-stu-id="f5a57-123">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="f5a57-124">Veri kümeleri, DataTable ve DataView</span><span class="sxs-lookup"><span data-stu-id="f5a57-124">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="f5a57-125">Bir veri kaynağına bağlanma</span><span class="sxs-lookup"><span data-stu-id="f5a57-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="f5a57-126">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="f5a57-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)