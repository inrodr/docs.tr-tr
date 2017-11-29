---
title: /vbruntime
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dda8ea7285a748bac53e30af8bd7a60099fe7411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="vbruntime"></a><span data-ttu-id="9ad7d-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="9ad7d-102">/vbruntime</span></span>
<span data-ttu-id="9ad7d-103">Visual Basic çalışma zamanı kitaplığı için veya belirli çalışma zamanı kitaplığı başvurusu olan bir başvuru olmadan derleyici derleme belirtir.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad7d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9ad7d-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="9ad7d-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="9ad7d-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="9ad7d-106">Visual Basic çalışma zamanı kitaplığı başvurusu olmadan derleyin.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="9ad7d-107">Visual Basic çalışma zamanı kitaplığı varsayılan başvuru derleyin.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="9ad7d-108">Visual Basic çalışma zamanı kitaplığı başvurusu olmadan derleyin ve Visual Basic Çalışma Zamanı Kitaplığı'ndaki çekirdek işlevselliğini derlemesini ekleme.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="9ad7d-109">Belirtilen kitaplığı (DLL) başvuru derleyin.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ad7d-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9ad7d-110">Remarks</span></span>  
 <span data-ttu-id="9ad7d-111">`/vbruntime` Derleyici seçeneği derleyici Visual Basic çalışma zamanı kitaplığı başvurusu olmadan derleme belirtmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="9ad7d-112">Visual Basic çalışma zamanı kitaplığı başvurusu olmadan derleme yaparsanız, hatalar veya uyarılar bir Visual Basic çalışma zamanı yardımcı çağrısına oluşturan kodu veya dil yapıları üzerinde kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="9ad7d-113">(A *Visual Basic çalışma zamanı yardımcı* anlamsal belirli bir dil yürütmek için çalışma zamanında adlı Microsoft.VisualBasic.dll içinde tanımlanan bir işlev.)</span><span class="sxs-lookup"><span data-stu-id="9ad7d-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="9ad7d-114">`/vbruntime+` Seçeneği yoksa oluşur aynı davranışı üreten `/vbruntime` anahtarı belirtilir.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="9ad7d-115">Kullanabileceğiniz `/vbruntime+` önceki geçersiz kılmak için seçeneği `/vbruntime` anahtarları.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="9ad7d-116">Çoğu nesnelerin `My` türü, kullandığınızda kullanılamaz `/vbruntime-` veya `vbruntime:``path` seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="9ad7d-117">Visual Basic çalışma zamanı çekirdek işlevselliğini katıştırma</span><span class="sxs-lookup"><span data-stu-id="9ad7d-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="9ad7d-118">`/vbruntime*` Seçeneği, bir çalışma zamanı kitaplığı başvurusu olmadan derleme olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="9ad7d-119">Bunun yerine, Visual Basic Çalışma Zamanı Kitaplığı'ndaki çekirdek işlevselliğini kullanıcı derlemede katıştırılır.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="9ad7d-120">Visual Basic çalışma zamanı içermeyen platformlarda uygulamanızı çalıştırıyorsa, bu seçeneği kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="9ad7d-121">Aşağıdaki çalışma zamanı üyeleri katıştırılmış:</span><span class="sxs-lookup"><span data-stu-id="9ad7d-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="9ad7d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>sınıfı</span><span class="sxs-lookup"><span data-stu-id="9ad7d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="9ad7d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>yöntemi</span><span class="sxs-lookup"><span data-stu-id="9ad7d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="9ad7d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>yöntemi</span><span class="sxs-lookup"><span data-stu-id="9ad7d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="9ad7d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>yöntemi</span><span class="sxs-lookup"><span data-stu-id="9ad7d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="9ad7d-126"><xref:Microsoft.VisualBasic.Constants.vbBack>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-127"><xref:Microsoft.VisualBasic.Constants.vbCr>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-130"><xref:Microsoft.VisualBasic.Constants.vbLf>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-134"><xref:Microsoft.VisualBasic.Constants.vbTab>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>sabiti</span><span class="sxs-lookup"><span data-stu-id="9ad7d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="9ad7d-136">Bazı nesnelerin `My` türü</span><span class="sxs-lookup"><span data-stu-id="9ad7d-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="9ad7d-137">Kullanarak derleme yaparsanız `/vbruntime*` seçeneği ve kodunuzu çekirdek işlevselliği ile gömülü olmayan Visual Basic Çalışma Zamanı Kitaplığı'ndan üyesi başvuruyor, derleyici üye kullanılamadığını belirten bir hata döndürür.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="9ad7d-138">Belirtilen kitaplık başvurma</span><span class="sxs-lookup"><span data-stu-id="9ad7d-138">Referencing a specified library</span></span>  
 <span data-ttu-id="9ad7d-139">Kullanabileceğiniz `path` özel çalışma zamanı kitaplığı Visual Basic çalışma zamanı kitaplığı varsayılan yerine başvuru derlemek için bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="9ad7d-140">Varsa değeri `path` bağımsız değişkeni bir dll dosyasının tam yoludur, derleyici bu dosyayı çalışma zamanı kitaplığı kullanır.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="9ad7d-141">Varsa değeri `path` bağımsız değişkeni bir DLL için tam bir yol değil, Visual Basic derleyici geçerli klasörde tanımlanan DLL ilk arar.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="9ad7d-142">Ardından, kullanarak belirttiğiniz yolda arar [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) derleyici seçeneği.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="9ad7d-143">Varsa `/sdkpath` derleyici seçeneği kullanılmaz, .NET Framework klasöründe tanımlanan DLL derleyici arar (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="9ad7d-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ad7d-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="9ad7d-144">Example</span></span>  
 <span data-ttu-id="9ad7d-145">Aşağıdaki örnekte nasıl kullanılacağını gösterir `/vbruntime` özel kitaplığına bir başvuru ile derleme seçeneği.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ad7d-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ad7d-146">See Also</span></span>  
 [<span data-ttu-id="9ad7d-147">Visual Basic çekirdek – Visual Studio 2010 SP1'de yeni derleme modu</span><span class="sxs-lookup"><span data-stu-id="9ad7d-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="9ad7d-148">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="9ad7d-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9ad7d-149">Örnek derleme komut satırları</span><span class="sxs-lookup"><span data-stu-id="9ad7d-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="9ad7d-150">/ sdkpath</span><span class="sxs-lookup"><span data-stu-id="9ad7d-150">/sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)