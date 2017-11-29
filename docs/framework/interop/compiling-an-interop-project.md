---
title: "Birlikte Çalışma Projesi Derleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc541911670c533caa97c645085ad09bde5eefdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="9314f-102">Birlikte Çalışma Projesi Derleme</span><span class="sxs-lookup"><span data-stu-id="9314f-102">Compiling an Interop Project</span></span>
<span data-ttu-id="9314f-103">İçeri aktarılan COM türlerini içeren bir veya daha fazla derlemeler başvuru COM birlikte çalışma projelerini gibi yönetilen diğer proje derlenir.</span><span class="sxs-lookup"><span data-stu-id="9314f-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="9314f-104">Visual Studio gibi geliştirme ortamında birlikte çalışma derlemeleri başvurusu yapabilir veya komut satırı derleyicisi kullandığınızda başvurabilir.</span><span class="sxs-lookup"><span data-stu-id="9314f-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="9314f-105">Her iki durumda da, diğer proje dosyaları ile aynı dizinde birlikte çalışma derlemesi düzgün derlemek için olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9314f-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>  
  
 <span data-ttu-id="9314f-106">Birlikte çalışma derlemeleri başvurmak iki yolu vardır:</span><span class="sxs-lookup"><span data-stu-id="9314f-106">There are two ways to reference interop assemblies:</span></span>  
  
-   <span data-ttu-id="9314f-107">Katıştırılmış birlikte çalışma türleri: itibaren [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ve [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], yürütülebilir dosyanın birlikte çalışma derlemeye tür bilgilerini katıştırma görevlendirin.</span><span class="sxs-lookup"><span data-stu-id="9314f-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="9314f-108">Önerilen yöntem budur.</span><span class="sxs-lookup"><span data-stu-id="9314f-108">This is the recommended technique.</span></span>  
  
-   <span data-ttu-id="9314f-109">Birlikte çalışma derlemeleri dağıtma: birlikte çalışma derlemesi için standart bir başvuru oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9314f-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="9314f-110">Bu durumda, uygulamanız ile birlikte çalışma derlemesi dağıtılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9314f-110">In this case, the interop assembly must be deployed with your application.</span></span>  
  
 <span data-ttu-id="9314f-111">Bu iki teknikler arasındaki farklar daha ayrıntılı olarak ele alınmıştır [COM türlerinde kullanarak yönetilen kod](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span><span class="sxs-lookup"><span data-stu-id="9314f-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
 <span data-ttu-id="9314f-112">Visual Studio ile birlikte çalışma türlerini katıştırma içinde gösterilmiştir [izlenecek yol: Microsoft Office derlemelerinden tür bilgilerini katıştırma](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) ve [izlenecek yol: yönetilen derlemelerden türler katıştırma](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="9314f-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) and [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="9314f-113">Komut satırı derleyicisi ile birlikte çalışma bir derleme başvurusu, yürütülebilir tür bilgilerini katıştırma, kullanın ve [/Link (C# Derleyici Seçenekleri)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) veya [/Link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) derleyici anahtar ve birlikte çalışma derlemesinin adını belirtin.</span><span class="sxs-lookup"><span data-stu-id="9314f-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9314f-114">Visual C++ uygulamalarını tür bilgilerini katıştırma olamaz, ancak uygulamalar veya yapmak eklentileri ile çalışabilirler.</span><span class="sxs-lookup"><span data-stu-id="9314f-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>  
  
 <span data-ttu-id="9314f-115">Birincil birlikte çalışma derlemesi dağıtıldığında içeren bir uygulama derlemek için kullanmak **/reference** derleyici geçin ve birlikte çalışma derlemesinin adını belirtin.</span><span class="sxs-lookup"><span data-stu-id="9314f-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9314f-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9314f-116">See Also</span></span>  
 [<span data-ttu-id="9314f-117">COM bileşenlerini .NET Framework'te gösterme</span><span class="sxs-lookup"><span data-stu-id="9314f-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="9314f-118">Dil bağımsızlığı ve dilden bağımsız bileşenler</span><span class="sxs-lookup"><span data-stu-id="9314f-118">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="9314f-119">Yönetilen kodda COM türlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="9314f-119">Using COM Types in Managed Code</span></span>](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
 [<span data-ttu-id="9314f-120">İzlenecek yol: Microsoft Office derlemelerinden tür bilgilerini katıştırma</span><span class="sxs-lookup"><span data-stu-id="9314f-120">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="9314f-121">İzlenecek yol: Yönetilen derlemelerden türler katıştırma</span><span class="sxs-lookup"><span data-stu-id="9314f-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="9314f-122">Tür kitaplığını derleme olarak içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="9314f-122">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)