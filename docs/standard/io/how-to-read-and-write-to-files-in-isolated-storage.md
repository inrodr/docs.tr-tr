---
title: "Nasıl yapılır: Yalıtılmış Depolamadaki Dosyaları Okuma ve Yazma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8d733efc3d70070dd12f55c651033e97d1792c38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a><span data-ttu-id="7ba2d-102">Nasıl yapılır: Yalıtılmış Depolamadaki Dosyaları Okuma ve Yazma</span><span class="sxs-lookup"><span data-stu-id="7ba2d-102">How to: Read and Write to Files in Isolated Storage</span></span>
<span data-ttu-id="7ba2d-103">Okuma veya, bir yalıtılmış depolama dosyasında yazmak için kullanın bir <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> bir akış okuyucusunu nesnesiyle (<xref:System.IO.StreamReader> nesnesi) veya akış yazıcı (<xref:System.IO.StreamWriter> nesnesi).</span><span class="sxs-lookup"><span data-stu-id="7ba2d-103">To read from, or write to, a file in an isolated store, use an <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> object with a stream reader (<xref:System.IO.StreamReader> object) or stream writer (<xref:System.IO.StreamWriter> object).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ba2d-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="7ba2d-104">Example</span></span>  
 <span data-ttu-id="7ba2d-105">Aşağıdaki kod örneğinde bir yalıtılmış depolamada alır ve TestStore.txt adlı bir dosya deposunda mevcut olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="7ba2d-105">The following code example obtains an isolated store and checks whether a file named TestStore.txt exists in the store.</span></span> <span data-ttu-id="7ba2d-106">Yoksa, bir dosya oluşturur ve "Merhaba yalıtılmış depolama" dosyasına yazar.</span><span class="sxs-lookup"><span data-stu-id="7ba2d-106">If it doesn't exist, it creates the file and writes "Hello Isolated Storage" to the file.</span></span> <span data-ttu-id="7ba2d-107">TestStore.txt zaten varsa, örnek kod dosyasından okur.</span><span class="sxs-lookup"><span data-stu-id="7ba2d-107">If TestStore.txt already exists, the example code reads from the file.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7ba2d-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7ba2d-108">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 <xref:System.IO.FileMode?displayProperty=nameWithType>  
 <xref:System.IO.FileAccess?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader?displayProperty=nameWithType>  
 <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
 [<span data-ttu-id="7ba2d-109">Dosya ve akış t-O</span><span class="sxs-lookup"><span data-stu-id="7ba2d-109">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="7ba2d-110">Yalıtılmış Depolama</span><span class="sxs-lookup"><span data-stu-id="7ba2d-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)