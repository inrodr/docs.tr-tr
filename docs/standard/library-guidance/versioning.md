---
title: Sürüm oluşturma ve .NET kitaplıkları
description: Sürüm oluşturma .NET kitaplıkları için en iyi yöntem önerileri.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: f95c8ade1f91af5c13184b839b327c9397c6fe5a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187864"
---
# <a name="versioning"></a><span data-ttu-id="fe070-103">Sürüm oluşturma</span><span class="sxs-lookup"><span data-stu-id="fe070-103">Versioning</span></span>

<span data-ttu-id="fe070-104">Yazılım kitaplığı sürüm 1.0 nadiren tamamlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fe070-104">A software library is rarely complete in version 1.0.</span></span> <span data-ttu-id="fe070-105">İyi kitaplıkları ekleme özellikleri, hataları düzeltiyor ve performansı iyileştirme zamanla evrim.</span><span class="sxs-lookup"><span data-stu-id="fe070-105">Good libraries evolve over time, adding features, fixing bugs and improving performance.</span></span> <span data-ttu-id="fe070-106">Mevcut kullanıcıları bozmadan her sürümü ile ek değer sağlayan bir .NET Kitaplığı'nın yeni sürümleri serbest bırakabilirsiniz önemlidir.</span><span class="sxs-lookup"><span data-stu-id="fe070-106">It is important that you can release new versions of a .NET library, providing additional value with each version, without breaking existing users.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="fe070-107">Bozucu değişiklikler</span><span class="sxs-lookup"><span data-stu-id="fe070-107">Breaking changes</span></span>

<span data-ttu-id="fe070-108">Sürümleri arasında bozucu değişiklikleri işleme hakkında daha fazla bilgi için bkz: [bozucu değişiklikler](./breaking-changes.md).</span><span class="sxs-lookup"><span data-stu-id="fe070-108">For information about handling breaking changes between versions, see [Breaking changes](./breaking-changes.md).</span></span>

## <a name="version-numbers"></a><span data-ttu-id="fe070-109">Sürüm numaraları</span><span class="sxs-lookup"><span data-stu-id="fe070-109">Version numbers</span></span>

<span data-ttu-id="fe070-110">Bir .NET kitaplığı, bir sürüm belirtmek için çeşitli yolları vardır.</span><span class="sxs-lookup"><span data-stu-id="fe070-110">A .NET library has many ways to specify a version.</span></span> <span data-ttu-id="fe070-111">Bu sürümleri en önemli şunlardır:</span><span class="sxs-lookup"><span data-stu-id="fe070-111">These versions are the most important:</span></span>

### <a name="nuget-package-version"></a><span data-ttu-id="fe070-112">NuGet Paket sürümü</span><span class="sxs-lookup"><span data-stu-id="fe070-112">NuGet package version</span></span>

<span data-ttu-id="fe070-113">[NuGet paketi sürüm](/nuget/reference/package-versioning) NuGet.org, Visual Studio NuGet Paket Yöneticisi görüntülenir ve paketi kullanıldığında, kaynak koda eklenir.</span><span class="sxs-lookup"><span data-stu-id="fe070-113">The [NuGet package version](/nuget/reference/package-versioning) is displayed on NuGet.org, the Visual Studio NuGet package manager, and is added to source code when the package is used.</span></span> <span data-ttu-id="fe070-114">NuGet Paket sürümü, sürüm numarası kullanıcıların sık bakın ve bunlar kullanmakta olduğunuz kitaplığa sürümü hakkında konuşurken bunlar için başvuracağınız ' dir.</span><span class="sxs-lookup"><span data-stu-id="fe070-114">The NuGet package version is the version number users will commonly see, and they'll refer to it when they talk about the version of a library they're using.</span></span> <span data-ttu-id="fe070-115">NuGet Paket sürümü NuGet tarafından kullanılır ve çalışma zamanı davranışı üzerinde hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="fe070-115">The NuGet package version is used by NuGet and has no effect on runtime behavior.</span></span>

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

<span data-ttu-id="fe070-116">NuGet Paket sürümü ile birleştirilmiş NuGet paket tanımlayıcısı, bir NuGet paketi tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fe070-116">The NuGet package identifier combined with the NuGet package version is used to identify a package in NuGet.</span></span> <span data-ttu-id="fe070-117">Örneğin, `Newtonsoft.Json`  +  `11.0.2`.</span><span class="sxs-lookup"><span data-stu-id="fe070-117">For example, `Newtonsoft.Json` + `11.0.2`.</span></span> <span data-ttu-id="fe070-118">Bir sonekine sahip bir paketi bir yayın öncesi paketidir ve test için ideal kılan Özel davranışa sahiptir.</span><span class="sxs-lookup"><span data-stu-id="fe070-118">A package with a suffix is a pre-release package and has special behavior that makes it ideal for testing.</span></span> <span data-ttu-id="fe070-119">Daha fazla bilgi için [yayın öncesi paketleri](./nuget.md#pre-release-packages).</span><span class="sxs-lookup"><span data-stu-id="fe070-119">For more information, see [Pre-release packages](./nuget.md#pre-release-packages).</span></span>

<span data-ttu-id="fe070-120">NuGet Paket sürümü geliştiriciler için en çok görünen sürümü olduğundan, onu kullanarak güncelleştirmek için iyi bir fikirdir [Semantic Versioning (SemVer)](https://semver.org/).</span><span class="sxs-lookup"><span data-stu-id="fe070-120">Because the NuGet package version is the most visible version to developers, it's a good idea to update it using [Semantic Versioning (SemVer)](https://semver.org/).</span></span> <span data-ttu-id="fe070-121">SemVer sürümü arasındaki değişiklikleri önemini gösterir ve geliştiricilerin bilinçli bir karar, hangi sürümün kullanılacağını seçerken olun yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="fe070-121">SemVer indicates the significance of changes between release and helps developers make an informed decision when choosing what version to use.</span></span> <span data-ttu-id="fe070-122">Örneğin, gitmek `1.0` için `2.0` potansiyel olarak en son değişiklikleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="fe070-122">For example, going from `1.0` to `2.0` indicates that there are potentially breaking changes.</span></span>

<span data-ttu-id="fe070-123">**✔️ DÜŞÜNÜN** kullanarak [SemVer 2.0.0](https://semver.org/) sürümüne NuGet paketinizi.</span><span class="sxs-lookup"><span data-stu-id="fe070-123">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="fe070-124">**✔️ YAPMAK** kullanıcıların yaygın olarak göreceği sürüm numarası olduğu gibi genel belgelerinde NuGet Paket sürümü kullanın.</span><span class="sxs-lookup"><span data-stu-id="fe070-124">**✔️ DO** use the NuGet package version in public documentation as it's the version number that users will commonly see.</span></span>

<span data-ttu-id="fe070-125">**✔️ YAPMAK** yayın öncesi son kararlı olmayan paket yayınlarken içerir.</span><span class="sxs-lookup"><span data-stu-id="fe070-125">**✔️ DO** include a pre-release suffix when releasing a non-stable package.</span></span>

> <span data-ttu-id="fe070-126">Kullanıcılar, yayın öncesi paketleri paket tamamlanmadı anlayabileceği şekilde almak için etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fe070-126">Users must opt in to getting pre-release packages, so they will understand that the package is not complete.</span></span>

### <a name="assembly-version"></a><span data-ttu-id="fe070-127">Derleme sürümü</span><span class="sxs-lookup"><span data-stu-id="fe070-127">Assembly version</span></span>

<span data-ttu-id="fe070-128">Derleme sürümü hangi CLR çalışma zamanında hangi sürümünü yüklemek için bir derleme seçin için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fe070-128">The assembly version is what the CLR uses at runtime to select which version of an assembly to load.</span></span> <span data-ttu-id="fe070-129">Tanımlayıcı bir ada sahip derlemeleri sürüm oluşturma yalnızca bir derlemeyi seçme geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="fe070-129">Selecting an assembly using versioning only applies to assemblies with a strong name.</span></span>

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

<span data-ttu-id="fe070-130">Windows .NET Framework CLR adlı derleme güçlü yüklemek için tam bir eşleşme ihtiyaç duyar.</span><span class="sxs-lookup"><span data-stu-id="fe070-130">The Windows .NET Framework CLR demands an exact match to load a strong named assembly.</span></span> <span data-ttu-id="fe070-131">Örneğin, `Libary1, Version=1.0.0.0` başvuru ile derlenen `Newtonsoft.Json, Version=11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="fe070-131">For example, `Libary1, Version=1.0.0.0` was compiled with a reference to `Newtonsoft.Json, Version=11.0.0.0`.</span></span> <span data-ttu-id="fe070-132">.NET Framework yalnızca o tam sürümünü yükler `11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="fe070-132">The .NET Framework will only load that exact version `11.0.0.0`.</span></span> <span data-ttu-id="fe070-133">Çalışma zamanında farklı bir sürümünü yüklemek için bir bağlama yeniden yönlendirmesi .NET uygulama yapılandırma dosyasına eklenmelidir.</span><span class="sxs-lookup"><span data-stu-id="fe070-133">To load a different version at runtime, a binding redirect must be added to the .NET application's config file.</span></span>

<span data-ttu-id="fe070-134">Derleme sürümü ile birleştirilmiş bir tanımlayıcı adlandırma sağlayan [katı derleme sürümü yükleme](../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="fe070-134">Strong naming combined with assembly version enables [strict assembly version loading](../../framework/app-domains/assembly-versioning.md).</span></span> <span data-ttu-id="fe070-135">Bir kitaplık tanımlayıcı adlandırma çok sayıda fayda olsa da bir derleme bulunamıyor çalışma zamanı özel durumları genellikle sonuç ve [bağlama yönlendirmeleri gerektirir](../../framework/configure-apps/redirect-assembly-versions.md) içinde `app.config` / `web.config` düzeltilmesi için.</span><span class="sxs-lookup"><span data-stu-id="fe070-135">While strong naming a library has a number of benefits, it often results in runtime exceptions that an assembly can't be found and [requires binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` to be fixed.</span></span> <span data-ttu-id="fe070-136">.NET core derleme yükleme gevşek olmuştur ve .NET Core CLR derlemeleri daha yüksek bir sürüm ile çalışma zamanında otomatik olarak yüklenecektir.</span><span class="sxs-lookup"><span data-stu-id="fe070-136">.NET Core assembly loading has been relaxed, and the .NET Core CLR will automatically load assemblies at runtime with a higher version.</span></span>

<span data-ttu-id="fe070-137">**✔️ DÜŞÜNÜN** yalnızca bir ana sürüm AssemblyVersion dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="fe070-137">**✔️ CONSIDER** only including a major version in the AssemblyVersion.</span></span>

> <span data-ttu-id="fe070-138">Örneğin, bir AssemblyVersion kitaplığı 1.0 ve kitaplık 1.0.1 hem sahip `1.0.0.0`, kitaplığı 2.0, AssemblyVersion sahipken `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="fe070-138">e.g. Library 1.0 and Library 1.0.1 both have an AssemblyVersion of `1.0.0.0`, while Library 2.0 has AssemblyVersion of `2.0.0.0`.</span></span> <span data-ttu-id="fe070-139">Daha az sıklıkta derleme sürümü değiştiğinde, bağlama yeniden yönlendirmeleri azaltır.</span><span class="sxs-lookup"><span data-stu-id="fe070-139">When the assembly version changes less often, it reduces binding redirects.</span></span>

<span data-ttu-id="fe070-140">**✔️ DÜŞÜNÜN** AssemblyVersion ve NuGet Paket sürümü ana sürüm numarasını eşitlenmiş durumda kalmasını.</span><span class="sxs-lookup"><span data-stu-id="fe070-140">**✔️ CONSIDER** keeping the major version number of the AssemblyVersion and the NuGet package version in sync.</span></span>

> <span data-ttu-id="fe070-141">Kullanıcıya görüntülenen bazı bilgi iletilerini AssemblyVersion dahildir ve örn bütünleştirilmiş kod ve derleme adı Tür adları içinde özel durum iletileri.</span><span class="sxs-lookup"><span data-stu-id="fe070-141">The AssemblyVersion is included in some informational messages displayed to the user, e.g. the assembly name and assembly qualified type names in exception messages.</span></span> <span data-ttu-id="fe070-142">Sürümleri arasında bir ilişki koruma sürümden kullandıkları geliştiriciler için daha fazla bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="fe070-142">Maintaining a relationship between the versions provides more information to developers about which version they are using.</span></span>

<span data-ttu-id="fe070-143">**❌ SAĞLAMADIĞI** sabit bir AssemblyVersion sahip.</span><span class="sxs-lookup"><span data-stu-id="fe070-143">**❌ DO NOT** have a fixed AssemblyVersion.</span></span>

> <span data-ttu-id="fe070-144">Değişmeyen bir AssemblyVersion bağlama yönlendirmeleri gereksinimini ortadan kaldırır, ancak yalnızca tek bir sürüm derlemenin Genel Derleme Önbelleği'ne (GAC) yüklenmesi anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="fe070-144">While an unchanging AssemblyVersion avoids the need for binding redirects, it means that only a single version of the assembly can be installed in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="fe070-145">Ayrıca, başka bir uygulama derlemeyi GAC bozucu değişiklikler güncelleştiriyorsa derlemenin GAC'deki başvuruda bulunan uygulamaları çalışmamasına neden olur.</span><span class="sxs-lookup"><span data-stu-id="fe070-145">Also, the applications that reference the assembly in the GAC will break if another application updates the GAC assembly with breaking changes.</span></span>

### <a name="assembly-file-version"></a><span data-ttu-id="fe070-146">Derleme dosyası sürümü</span><span class="sxs-lookup"><span data-stu-id="fe070-146">Assembly file version</span></span>

<span data-ttu-id="fe070-147">Derleme dosyası sürümü Windows dosya sürümünü görüntülemek için kullanılır ve çalışma zamanı davranışı üzerinde hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="fe070-147">The assembly file version is used to display a file version in Windows and has no effect on runtime behavior.</span></span> <span data-ttu-id="fe070-148">Bu sürümü isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="fe070-148">Setting this version is optional.</span></span> <span data-ttu-id="fe070-149">Windows Gezgini'nde dosya özellikleri iletişim kutusu görünür:</span><span class="sxs-lookup"><span data-stu-id="fe070-149">It's visible in the File Properties dialog in Windows Explorer:</span></span>

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

<span data-ttu-id="fe070-150">![Windows Gezgini](./media/versioning/win-properties.png "Windows Gezgini")</span><span class="sxs-lookup"><span data-stu-id="fe070-150">![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")</span></span>

> [!NOTE]
> <span data-ttu-id="fe070-151">Bu sürüm biçimi izlemiyorsa zararsız bir yapı uyarısı tetiklenir `Major.Minor.Build.Revision`.</span><span class="sxs-lookup"><span data-stu-id="fe070-151">An innocuous build warning is raised if this version does not follow the format `Major.Minor.Build.Revision`.</span></span> <span data-ttu-id="fe070-152">Uyarıyı güvenle yoksayılabilir.</span><span class="sxs-lookup"><span data-stu-id="fe070-152">The warning can be safely ignored.</span></span>

<span data-ttu-id="fe070-153">**✔️ DÜŞÜNÜN** sürekli tümleştirme dahil olmak üzere, yapı numarası olarak AssemblyFileVersion düzeltme.</span><span class="sxs-lookup"><span data-stu-id="fe070-153">**✔️ CONSIDER** including a continuous integration build number as the AssemblyFileVersion revision.</span></span>

> <span data-ttu-id="fe070-154">Örneğin, sürüm 1.0.0 projenizin oluşturuyorsanız ve, AssemblyFileVersion 1.0.0.99 sürekli tümleştirme yapı numarası 99 olduğundan.</span><span class="sxs-lookup"><span data-stu-id="fe070-154">For example, you are building version 1.0.0 of your project, and the continuous integration build number is 99 so your AssemblyFileVersion is 1.0.0.99.</span></span>

### <a name="assembly-informational-version"></a><span data-ttu-id="fe070-155">Derleme Bilgilendirme sürümü</span><span class="sxs-lookup"><span data-stu-id="fe070-155">Assembly informational version</span></span>

<span data-ttu-id="fe070-156">Derleme Bilgilendirme sürümü ek sürüm bilgileri kaydetmek için kullanılır ve çalışma zamanı davranışı üzerinde hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="fe070-156">The assembly informational version is used to record additional version information and has no effect on runtime behavior.</span></span> <span data-ttu-id="fe070-157">Bu sürümü isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="fe070-157">Setting this version is optional.</span></span> <span data-ttu-id="fe070-158">SourceLink kullanıyorsanız, bu sürüm derleme NuGet Paket sürümü Ayrıca kaynak denetimi sürümü ile ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="fe070-158">If you're using SourceLink, this version will be set on build with the NuGet package version plus a source control version.</span></span> <span data-ttu-id="fe070-159">Örneğin, `1.0.0-beta1+204ff0a` işleme karması gelen derlemenin derlendiği kaynak kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="fe070-159">For example, `1.0.0-beta1+204ff0a` includes the commit hash of the source code the assembly was built from.</span></span> <span data-ttu-id="fe070-160">Daha fazla bilgi için [SourceLink](./sourcelink.md).</span><span class="sxs-lookup"><span data-stu-id="fe070-160">For more information, see [SourceLink](./sourcelink.md).</span></span>

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

<span data-ttu-id="fe070-161">**❌ KAÇININ** derleme Bilgilendirme sürümü kendiniz ayarlama.</span><span class="sxs-lookup"><span data-stu-id="fe070-161">**❌ AVOID** setting the assembly informational version yourself.</span></span>

> <span data-ttu-id="fe070-162">NuGet ve kaynak denetimi meta verilerini içeren sürüm otomatik olarak oluşturulacak SourceLink izin verir.</span><span class="sxs-lookup"><span data-stu-id="fe070-162">Allow SourceLink to automatically generate the version containing NuGet and source control metadata.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="fe070-163">[Önceki](./publish-nuget-package.md)
[İleri](./breaking-changes.md)</span><span class="sxs-lookup"><span data-stu-id="fe070-163">[Previous](./publish-nuget-package.md)
[Next](./breaking-changes.md)</span></span>