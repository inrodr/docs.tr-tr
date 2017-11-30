---
title: ".NET ve Docker giriş"
description: Anlama Docker ve .NET Core
keywords: .NET, .NET core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="c16f1-104">.NET ve Docker giriş</span><span class="sxs-lookup"><span data-stu-id="c16f1-104">Introduction to .NET and Docker</span></span>

 <span data-ttu-id="c16f1-105">Bu makalede, bir giriş ve Docker .NET ile çalışmaya kavramsal arka plan sağlar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-105">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span> 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="c16f1-106">Docker: dağıtmak ve her yerden çalıştırmak için uygulamalarınızı paketleme</span><span class="sxs-lookup"><span data-stu-id="c16f1-106">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="c16f1-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) geliştiricilerinin ve yöneticilerinin oluşturmak bir açık Platform [görüntüleri](https://docs.docker.com/glossary/?term=image)sevk ve dağıtılmış uygulamaları adlı geniş yalıtılmış bir ortamda çalıştırmak bir [kapsayıcı](https://www.docker.com/what-container).</span><span class="sxs-lookup"><span data-stu-id="c16f1-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="c16f1-108">Bu yaklaşım, geliştirme, QA ve üretim ortamlarını arasında verimli uygulama yaşam döngüsü yönetimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-108">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="c16f1-109">[Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) kullanan [Docker altyapısına](https://docs.docker.com/engine/docker-overview/#docker-engine) hızlı bir şekilde oluşturmak ve uygulamaları olarak paketlemek için [Docker görüntüleri](https://docs.docker.com/glossary/?term=image) yazılan dosyaları kullanılarak oluşturulan [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) sonra dağıtılır ve Çalıştır biçimde bir [kapsayıcı katmanlı](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="c16f1-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="c16f1-110">Oluşturabilir ya da kendi [görüntüleri katmanlı](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) dockerfiles veya var olanları gelen kullanım olarak bir [kayıt defteri](https://docs.docker.com/glossary/?term=registry)gibi [Docker hub'a](https://docs.docker.com/glossary/?term=Docker%20Hub).</span><span class="sxs-lookup"><span data-stu-id="c16f1-110">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="c16f1-111">[Docker kapsayıcıları, görüntüler ve kayıt defterleri arasındaki ilişkiyi](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) önemli bir kavramdır zaman [mimarisi oluşturma ve derleme kapsayıcılı uygulamalar veya mikro](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/).</span><span class="sxs-lookup"><span data-stu-id="c16f1-111">The [relationship between Docker containers, images, and registries](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) is an important concept when [architecting and building containerized applications or microservices](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/).</span></span> <span data-ttu-id="c16f1-112">Bu yaklaşım, geliştirme ve dağıtım arasındaki süreyi büyük ölçüde kısaltır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-112">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="c16f1-113">Daha fazla bilgi (ve izleyen)</span><span class="sxs-lookup"><span data-stu-id="c16f1-113">Further reading (and watching)</span></span>

* [<span data-ttu-id="c16f1-114">Windows tabanlı kapsayıcıları: Kurumsal düzeyde denetim ile Modern uygulama geliştirme.</span><span class="sxs-lookup"><span data-stu-id="c16f1-114">Windows-based containers: Modern app development with enterprise-grade control.</span></span>](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [<span data-ttu-id="c16f1-115">Docker genel bakış</span><span class="sxs-lookup"><span data-stu-id="c16f1-115">Docker overview</span></span>](https://docs.docker.com/engine/docker-overview/)
* [<span data-ttu-id="c16f1-116">Windows kapsayıcılarında Dockerfile</span><span class="sxs-lookup"><span data-stu-id="c16f1-116">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="c16f1-117">Dockerfiles yazmak için en iyi uygulamalar</span><span class="sxs-lookup"><span data-stu-id="c16f1-117">Best practices for writing Dockerfiles</span></span>](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [<span data-ttu-id="c16f1-118">.NET Core uygulamaları için yapı Docker görüntüleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-118">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="c16f1-119">.NET Docker görüntüleri alma</span><span class="sxs-lookup"><span data-stu-id="c16f1-119">Getting .NET Docker Images</span></span>

<span data-ttu-id="c16f1-120">Resmi .NET Docker görüntüleri oluşturulur ve Microsoft tarafından en iyi duruma getirilmiş.</span><span class="sxs-lookup"><span data-stu-id="c16f1-120">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="c16f1-121">Bunlar Microsoft depoları Docker hub'ındaki genel olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-121">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="c16f1-122">Her depo işletim sistemi sürümleri ve .NET sürümleri bağlı olarak birden fazla görüntü içerebilir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-122">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="c16f1-123">Çoğu görüntü depoları belirli framework sürümünü ve (Linux distro veya Windows sürümü) bir işletim sistemi seçmenize yardımcı olmak için kapsamlı etiketleme sağlar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-123">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="c16f1-124">Senaryo tabanlı Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="c16f1-124">Scenario Based Guidance</span></span>

<span data-ttu-id="c16f1-125">Microsoft'un hedefi .NET depoları için belirli bir senaryoyu ya da iş yükünü temsil ayrıntılı ve odaklanmış depoları olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-125">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="c16f1-126">`microsoft/aspnetcore` Görüntüleri en iyi duruma getirilmiş Docker, ASP.NET Core uygulamaları için kapsayıcıları daha hızlı başlatabilmeniz.</span><span class="sxs-lookup"><span data-stu-id="c16f1-126">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="c16f1-127">.NET Core görüntüleri (`microsoft/dotnet`) .NET Core üzerinde dayalı konsol uygulamalar için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-127">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="c16f1-128">Örneğin, toplu işlemler, Azure Web işleri ve diğer konsol senaryoları en iyi duruma getirilmiş .NET Core görüntüleri kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-128">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="c16f1-129">Docker ve .NET uygulamaları kullanmak için en bariz yatay Üretim dağıtımı ve barındırmak için bir senaryodur.</span><span class="sxs-lookup"><span data-stu-id="c16f1-129">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="c16f1-130">Bu üretim yalnızca bir senaryodur ve diğer eşit yararlı olanlardır ortaya çıkmıştır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-130">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="c16f1-131">Bu senaryolar için .NET belirli değildir, ancak çoğu Geliştirici platformları uygulamalıdır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-131">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="c16f1-132">**Düşük uyuşmazlık yüklemek** — .NET yerel bir yükleme deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c16f1-132">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="c16f1-133">Yalnızca .NET Docker görüntüsüyle da indirin.</span><span class="sxs-lookup"><span data-stu-id="c16f1-133">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="c16f1-134">**Bir kapsayıcıda geliştirmek** — tutarlı bir ortamda, geliştirme ve üretim ortamlarını benzer (Geliştirici makinelerde genel durum gibi sorunlarını önleme) yapmadan geliştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c16f1-134">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="c16f1-135">Docker için Visual Studio Araçları bile doğrudan Visual Studio'dan bir kapsayıcı başlatmak etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="c16f1-135">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="c16f1-136">**Test bir kapsayıcıda** — yanlış yapılandırılmış ortamları kaynaklanan hatalar azaltma bir kapsayıcıda test edebilirsiniz veya başka değişiklikler geride bıraktığı son testten.</span><span class="sxs-lookup"><span data-stu-id="c16f1-136">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="c16f1-137">**Bir kapsayıcıda yapı** — paylaşılan yapı makineleri çoklu ortamlar için doğru yapılandırma ancak bunun yerine bir "BYOC" taşımak için gereken önleme kod içinde bir kapsayıcı oluşturabilirsiniz (kendi kapsayıcı Getir) yaklaşım.</span><span class="sxs-lookup"><span data-stu-id="c16f1-137">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="c16f1-138">**Tüm ortamlar dağıtımda** — bir görüntü tüm ortamlarınızın dağıtabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c16f1-138">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="c16f1-139">Bu yaklaşım, genellikle dış yapılandırması (örneğin, eklenen ortam değişkenleri) aracılığıyla görüntü davranışı değiştirme yapılandırma farklılıkları nedeniyle hataları azaltır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-139">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="c16f1-140">[Genel rehberlik](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) .NET Core ve .NET Framework arasında Docker kapsayıcısı geliştirme için karar verme.</span><span class="sxs-lookup"><span data-stu-id="c16f1-140">[General guidance](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="c16f1-141">Docker geliştirme senaryoları</span><span class="sxs-lookup"><span data-stu-id="c16f1-141">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="c16f1-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="c16f1-142">.NET Core</span></span>

<span data-ttu-id="c16f1-143">**.NET core kaynaklar**</span><span class="sxs-lookup"><span data-stu-id="c16f1-143">**.NET Core resources**</span></span>

 <span data-ttu-id="c16f1-144">İlgilenilen senaryolarınızı sığacak .NET Core örnekleri seçin.</span><span class="sxs-lookup"><span data-stu-id="c16f1-144">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="c16f1-145">Tüm örnek yönergeleri, Windows, Linux veya macOS ana bilgisayar Windows veya Linux Docker görüntü hedef açıklar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-145">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="c16f1-146">Örnekleri .NET Core 2.0 kullanın.</span><span class="sxs-lookup"><span data-stu-id="c16f1-146">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="c16f1-147">Docker kullandıkları [çok aşama yapı](https://github.com/dotnet/announcements/issues/18) ve [çok yay etiketleri](https://github.com/dotnet/announcements/issues/14) uygun olduğunda.</span><span class="sxs-lookup"><span data-stu-id="c16f1-147">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="c16f1-148">.NET core DockerHub görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-148">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="c16f1-149">.NET Core uygulama dockerize</span><span class="sxs-lookup"><span data-stu-id="c16f1-149">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="c16f1-150">Bu .NET Core Docker örnek gösterilmektedir nasıl [Docker .NET Core geliştirme sürecinizde kullanmak](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span><span class="sxs-lookup"><span data-stu-id="c16f1-150">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="c16f1-151">Örnek, Linux ve Windows kapsayıcılarını ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-151">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="c16f1-152">Bu .NET Core Docker örneği için en iyi yöntem deseni gösterir [üretim için .NET Core uygulamaları için Docker görüntülerinizi oluşturmak.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="c16f1-152">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="c16f1-153">Örnek, Linux ve Windows kapsayıcılarını ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-153">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="c16f1-154">Bu [.NET Core Docker örnek](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) için Docker görüntülerinizi oluşturmak için en iyi yöntem desen gösteren [müstakil .NET Core uygulamaları](https://docs.microsoft.com/dotnet/core/deploying/).</span><span class="sxs-lookup"><span data-stu-id="c16f1-154">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](https://docs.microsoft.com/dotnet/core/deploying/).</span></span> <span data-ttu-id="c16f1-155">Bir avantajı olmadan küçük üretim kapsayıcısı için kullanılan [kapsayıcılar arasındaki temel görüntüleri paylaşımı](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span><span class="sxs-lookup"><span data-stu-id="c16f1-155">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="c16f1-156">Ancak, daha düşük Docker Katmanlar paylaşılan.</span><span class="sxs-lookup"><span data-stu-id="c16f1-156">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="c16f1-157">ARM32 / Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="c16f1-157">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="c16f1-158">Duyuru .NET çekirdeği çalışma zamanı ARM32 derlemeler</span><span class="sxs-lookup"><span data-stu-id="c16f1-158">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="c16f1-159">ARM32 / Raspberry Pi .NET Core üzerinde DockerHub görüntüleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-159">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="c16f1-160">ARM32 / Böğürtlenli Pi .NET Core Docker Github'da örnekleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-160">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="c16f1-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c16f1-161">.NET Framework</span></span>

* <span data-ttu-id="c16f1-162">[.NET framework DockerHub görüntülerinde](https://hub.docker.com/r/microsoft/dotnet-framework/) bu depodaki çeşitli .NET Framework Docker yapılandırmaları gösteren örnekleri içerir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-162">[.NET Framework images on DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="c16f1-163">Bu görüntüler, kendi Docker görüntülerinizi temel olarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c16f1-163">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="c16f1-164">**.NET framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="c16f1-164">**.NET Framework 4.7**</span></span>

<span data-ttu-id="c16f1-165">[ [Dotnet-framework: 4.7 örnek](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) temel "hello world" kullanımını gösteren [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47).</span><span class="sxs-lookup"><span data-stu-id="c16f1-165">[The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47).</span></span> <span data-ttu-id="c16f1-166">Size nasıl derleme ve güvenmek uygulama dağıtma gösterir [.NET Framework 4.7 docker görüntü](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="c16f1-166">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span></span>

<span data-ttu-id="c16f1-167">**.NET framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="c16f1-167">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="c16f1-168">[Dotnet-framework: 4.6.2 örnek](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) temel "hello world" kullanımını gösteren [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462).</span><span class="sxs-lookup"><span data-stu-id="c16f1-168">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462).</span></span> <span data-ttu-id="c16f1-169">Size nasıl derleme ve güvenmek uygulama dağıtma gösterir [.NET Framework 4.6.2 docker görüntü](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span><span class="sxs-lookup"><span data-stu-id="c16f1-169">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span></span>

<span data-ttu-id="c16f1-170">**.NET framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="c16f1-170">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="c16f1-171">[Dotnet-framework: 3.5 örnek](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) temel "hello world" kullanımını gösteren [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span><span class="sxs-lookup"><span data-stu-id="c16f1-171">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span></span> <span data-ttu-id="c16f1-172">Size nasıl derleme ve .NET Framework 3. 5'Docker ' bağlı olan bir proje dağıtma gösterir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-172">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="c16f1-173">ASP.NET Çekirdeği</span><span class="sxs-lookup"><span data-stu-id="c16f1-173">ASP.NET Core</span></span>

* <span data-ttu-id="c16f1-174">[Bu ASP.NET Core Docker örnek](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) Docker görüntülerinizi ASP.NET Core için üretim için uygulamalar oluşturmak için en iyi yöntem desen gösterir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-174">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="c16f1-175">Örnek, Linux ve Windows kapsayıcılarını ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-175">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="c16f1-176">ASP.NET Core DockerHub görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-176">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="c16f1-177">Github'da ASP.NET Core görüntüleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-177">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="c16f1-178">ASP.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c16f1-178">ASP.NET Framework</span></span> 

* [<span data-ttu-id="c16f1-179">DockerHub ASP.NET Framework görüntülerde</span><span class="sxs-lookup"><span data-stu-id="c16f1-179">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="c16f1-180">ASP.NET Web Forms uygulama .NET Framework 4.6.2 örneği</span><span class="sxs-lookup"><span data-stu-id="c16f1-180">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="c16f1-181">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="c16f1-181">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="c16f1-182">Windows Communication Framework (WCF) DockerHub görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-182">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="c16f1-183">Windows Communication Framework (WCF) görüntüleri github'da</span><span class="sxs-lookup"><span data-stu-id="c16f1-183">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

* [<span data-ttu-id="c16f1-184">Tam .NET Framework 4.6.2 kullanarak Windows Communication Framework (WCF) Docker örnekleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-184">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="c16f1-185">Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="c16f1-185">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="c16f1-186">Internet Information Server (IIS) DockerHub görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-186">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="c16f1-187">Github'da Internet Information Server (IIS) görüntüleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-187">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="c16f1-188">Diğer Microsoft yığın kapsayıcı görüntüleri ile etkileşim</span><span class="sxs-lookup"><span data-stu-id="c16f1-188">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="c16f1-189">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="c16f1-189">Microsoft SQL Server</span></span>

* [<span data-ttu-id="c16f1-190">Linux 2017 kapsayıcı görüntüsü için Microsoft SQL Server ile Docker Quickstart çalıştırın</span><span class="sxs-lookup"><span data-stu-id="c16f1-190">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="c16f1-191">Microsoft SQL Server DockerHub Linux görüntülerinde için</span><span class="sxs-lookup"><span data-stu-id="c16f1-191">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="c16f1-192">DockerHub Windows kapsayıcıları için Microsoft SQL Server görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-192">Microsoft SQL Server for Windows Containers images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="c16f1-193">Microsoft SQL Server Express Edition görüntüleri DockerHub üzerinde Windows kapsayıcıları için</span><span class="sxs-lookup"><span data-stu-id="c16f1-193">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="c16f1-194">Microsoft SQL Server Developer Edition görüntüleri DockerHub üzerinde Windows kapsayıcıları için</span><span class="sxs-lookup"><span data-stu-id="c16f1-194">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="c16f1-195">Visual Studio Team Services (VSTS) aracısı</span><span class="sxs-lookup"><span data-stu-id="c16f1-195">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="c16f1-196">Visual Studio Team Services (VSTS) aracısı görüntüleri DockerHub üzerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-196">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="c16f1-197">Github'da Visual Studio Team Services (VSTS) aracısı görüntüleri</span><span class="sxs-lookup"><span data-stu-id="c16f1-197">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="c16f1-198">Operations Management Suite (OMS) Linux Aracısı</span><span class="sxs-lookup"><span data-stu-id="c16f1-198">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="c16f1-199">Operations Management Suite (OMS) Linux Aracısı genel bakış</span><span class="sxs-lookup"><span data-stu-id="c16f1-199">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [<span data-ttu-id="c16f1-200">Operations Management Suite (OMS) DockerHub görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-200">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [<span data-ttu-id="c16f1-201">Operations Management Suite (OMS) görüntüleri github'da</span><span class="sxs-lookup"><span data-stu-id="c16f1-201">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="c16f1-202">Microsoft Azure komut satırı arabirimi (CLI)</span><span class="sxs-lookup"><span data-stu-id="c16f1-202">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="c16f1-203">DockerHub görüntülerinde Microsoft Azure komut satırı arabirimi (CLI)</span><span class="sxs-lookup"><span data-stu-id="c16f1-203">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](Docker image for Microsoft Azure Command Line Interface) 

* [<span data-ttu-id="c16f1-204">GitHub görüntülerinde Microsoft Azure komut satırı arabirimi (CLI)</span><span class="sxs-lookup"><span data-stu-id="c16f1-204">Microsoft Azure Command Line Interface (CLI) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

> [!Note]
> <span data-ttu-id="c16f1-205">Bir Azure aboneliğiniz yoksa [bugün kaydolun](https://azure.microsoft.com/free/?b=16.48) Ücretsiz 30 günlük hesabı ve Azure Hizmetleri herhangi bir bileşimini denemek için Azure KREDİLERİ 200 ABD Doları alın.</span><span class="sxs-lookup"><span data-stu-id="c16f1-205">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="c16f1-206">Microsoft Azure Cosmos DB öykünücü (yalnızca Windows kapsayıcıları)</span><span class="sxs-lookup"><span data-stu-id="c16f1-206">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="c16f1-207">Microsoft Azure Cosmos DB öykünücüsü DockerHub görüntülerinde</span><span class="sxs-lookup"><span data-stu-id="c16f1-207">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="c16f1-208">Yerel geliştirme ve sınama için Azure Cosmos DB öykünücüsünü kullanma</span><span class="sxs-lookup"><span data-stu-id="c16f1-208">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="c16f1-209">Zengin Docker geliştirme ekosistemi keşfetme</span><span class="sxs-lookup"><span data-stu-id="c16f1-209">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="c16f1-210">Farklı Docker görüntüler ve Docker platform hakkında öğrendiniz, zengin Docker ekosistemi keşfetmek için sonraki adım olacaktır.</span><span class="sxs-lookup"><span data-stu-id="c16f1-210">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="c16f1-211">Aşağıdaki bağlantılar nasıl Microsoft araçları kapsayıcı geliştirme tamamlayan gösterir.</span><span class="sxs-lookup"><span data-stu-id="c16f1-211">The following links show you how the Microsoft tools complement container development.</span></span>

* [<span data-ttu-id="c16f1-212">.NET ve Docker birlikte kullanma</span><span class="sxs-lookup"><span data-stu-id="c16f1-212">Using .NET and Docker together</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [<span data-ttu-id="c16f1-213">Tasarlama ve birden çok kapsayıcı ve mikro hizmet tabanlı .NET uygulamaları geliştirme</span><span class="sxs-lookup"><span data-stu-id="c16f1-213">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [<span data-ttu-id="c16f1-214">Visual Studio kod Docker uzantısı</span><span class="sxs-lookup"><span data-stu-id="c16f1-214">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile) 
* [<span data-ttu-id="c16f1-215">Azure Service Fabric kullanmayı öğrenin</span><span class="sxs-lookup"><span data-stu-id="c16f1-215">Learn how to use Azure Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/) 
* [<span data-ttu-id="c16f1-216">Örnek Service Fabric alma başlatıldı</span><span class="sxs-lookup"><span data-stu-id="c16f1-216">Service Fabric Getting Started Sample</span></span>](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [<span data-ttu-id="c16f1-217">Windows kapsayıcıları yararları</span><span class="sxs-lookup"><span data-stu-id="c16f1-217">Benefits of Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="c16f1-218">Visual Studio Docker araçları ile çalışma</span><span class="sxs-lookup"><span data-stu-id="c16f1-218">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="c16f1-219">Azure kapsayıcı örneklerine Azure kapsayıcı kayıt defterinden Docker görüntüleri dağıtma</span><span class="sxs-lookup"><span data-stu-id="c16f1-219">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="c16f1-220">Visual Studio Code ile hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="c16f1-220">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="c16f1-221">Ellere Visual Studio ile Mac, kapsayıcıları ve sunucusuz kodu bulutta hakkında alma</span><span class="sxs-lookup"><span data-stu-id="c16f1-221">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="c16f1-222">Mac Laboratuvar için Docker ve Visual Studio ile çalışmaya başlama</span><span class="sxs-lookup"><span data-stu-id="c16f1-222">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a><span data-ttu-id="c16f1-223">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="c16f1-223">Next Steps</span></span>

* [<span data-ttu-id="c16f1-224">.NET Core ile Docker temellerini öğrenin</span><span class="sxs-lookup"><span data-stu-id="c16f1-224">Learn Docker Basics with .NET Core</span></span>](../docker/docker-basics-dotnet-core.md)
* [<span data-ttu-id="c16f1-225">.NET Core Docker görüntülerinizi oluşturmak</span><span class="sxs-lookup"><span data-stu-id="c16f1-225">Building .NET Core Docker Images</span></span>](../docker/building-net-docker-images)