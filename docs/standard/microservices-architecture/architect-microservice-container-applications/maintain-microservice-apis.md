---
title: "Oluşturma, Gelişmekte olan ve sürüm oluşturma mikro hizmet API'leri ve sözleşmeler"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Oluşturma, Gelişmekte olan ve sürüm oluşturma mikro hizmet API'leri ve sözleşmeler"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a><span data-ttu-id="7d440-104">Oluşturma, Gelişmekte olan ve sürüm oluşturma mikro hizmet API'leri ve sözleşmeler</span><span class="sxs-lookup"><span data-stu-id="7d440-104">Creating, evolving, and versioning microservice APIs and contracts</span></span>

<span data-ttu-id="7d440-105">Mikro hizmet API, hizmet ve istemcileri arasında bir sözleşmedir.</span><span class="sxs-lookup"><span data-stu-id="7d440-105">A microservice API is a contract between the service and its clients.</span></span> <span data-ttu-id="7d440-106">Yalnızca çok önemli bir sözleşmedir neden olan API sözleşmesinin bozmadığını varsa bir mikro hizmet bağımsız olarak gelişmesi kuramaz.</span><span class="sxs-lookup"><span data-stu-id="7d440-106">You will be able to evolve a microservice independently only if you do not break its API contract, which is why the contract is so important.</span></span> <span data-ttu-id="7d440-107">Sözleşme değiştirirseniz, istemci uygulamaları veya API ağ geçidi etkiler.</span><span class="sxs-lookup"><span data-stu-id="7d440-107">If you change the contract, it will impact your client applications or your API Gateway.</span></span>

<span data-ttu-id="7d440-108">API tanımı yapısını hangi protokolünü kullandığınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="7d440-108">The nature of the API definition depends on which protocol you are using.</span></span> <span data-ttu-id="7d440-109">Örneğin, ileti kullanıyorsanız (gibi [AMQP](https://www.amqp.org/)), ileti türlerini API oluşur.</span><span class="sxs-lookup"><span data-stu-id="7d440-109">For instance, if you are using messaging (like [AMQP](https://www.amqp.org/)), the API consists of the message types.</span></span> <span data-ttu-id="7d440-110">HTTP ve RESTful hizmetlerini kullanıyorsanız, API URL'leri ve istek ve yanıt JSON biçimleri oluşur.</span><span class="sxs-lookup"><span data-stu-id="7d440-110">If you are using HTTP and RESTful services, the API consists of the URLs and the request and response JSON formats.</span></span>

<span data-ttu-id="7d440-111">Ancak, ilk sözleşme hakkında Düşünceli olsa bile, bir hizmeti API'si zamanla değiştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7d440-111">However, even if you are thoughtful about your initial contract, a service API will need to change over time.</span></span> <span data-ttu-id="7d440-112">Bu durumda — ve özellikle, API birden çok istemci uygulamaları tarafından kullanılan ortak bir API olduğunda — tüm istemcilerin yeni API sözleşmesine yükseltmek için genellikle zorlayamaz.</span><span class="sxs-lookup"><span data-stu-id="7d440-112">When that happens—and especially if your API is a public API consumed by multiple client applications—you typically cannot force all clients to upgrade to your new API contract.</span></span> <span data-ttu-id="7d440-113">Genellikle, aynı anda bir hizmet sözleşmesini hem eski hem de yeni sürümlerini çalıştıran bir şekilde bir hizmetin yeni sürümler artımlı olarak dağıtmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="7d440-113">You usually need to incrementally deploy new versions of a service in a way that both old and new versions of a service contract are running simultaneously.</span></span> <span data-ttu-id="7d440-114">Bu nedenle, bir strateji, hizmet sürümü oluşturma için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="7d440-114">Therefore, it is important to have a strategy for your service versioning.</span></span>

<span data-ttu-id="7d440-115">API değişiklikleri API'nize öznitelikleri veya parametrelerini eklerseniz gibi küçük olduğunda, daha eski bir API kullanan istemciler geçin ve hizmet yeni sürümü ile çalışma.</span><span class="sxs-lookup"><span data-stu-id="7d440-115">When the API changes are small, like if you add attributes or parameters to your API, clients that use an older API should switch and work with the new version of the service.</span></span> <span data-ttu-id="7d440-116">Gerekli olan eksik öznitelikleri için varsayılan değerler sağlamak mümkün olabilir ve istemcilerin ek yanıt öznitelikleri yoksay olabilir.</span><span class="sxs-lookup"><span data-stu-id="7d440-116">You might be able to provide default values for any missing attributes that are required, and the clients might be able to ignore any extra response attributes.</span></span>

<span data-ttu-id="7d440-117">Ancak, bazen büyük uyumsuz bir hizmet API değişiklik yapmak ve gerekir.</span><span class="sxs-lookup"><span data-stu-id="7d440-117">However, sometimes you need to make major and incompatible changes to a service API.</span></span> <span data-ttu-id="7d440-118">İstemci uygulamaları veya hizmetleri hemen en yeni sürüme yükseltmek için zorlamak kuramamış olabilir çünkü bir hizmeti belirli bir süre için API eski sürümleri desteklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="7d440-118">Because you might not be able to force client applications or services to upgrade immediately to the new version, a service must support older versions of the API for some period.</span></span> <span data-ttu-id="7d440-119">Bir HTTP tabanlı mekanizması REST gibi kullanıyorsanız, bir URL veya bir HTTP üstbilgisi içine API sürüm numarası katıştırmak için yaklaşımdır.</span><span class="sxs-lookup"><span data-stu-id="7d440-119">If you are using an HTTP-based mechanism such as REST, one approach is to embed the API version number in the URL or into a HTTP header.</span></span> <span data-ttu-id="7d440-120">Sonra hizmet aynı anda aynı hizmet örneği içinde her iki sürümü uygulama veya her bir API sürümü işlemek farklı örnekleri dağıtma arasında karar verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7d440-120">Then you can decide between implementing both versions of the service simultaneously within the same service instance, or deploying different instances that each handle a version of the API.</span></span> <span data-ttu-id="7d440-121">Bunun için iyi bir yaklaşımdır [Dünyası düzeni](https://en.wikipedia.org/wiki/Mediator_pattern) (örneğin, [MediatR Kitaplığı](https://github.com/jbogard/MediatR)) bağımsız işleyicileri farklı uygulama sürümleri aynı şekilde.</span><span class="sxs-lookup"><span data-stu-id="7d440-121">A good approach for this is the [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern) (for example, [MediatR library](https://github.com/jbogard/MediatR)) to decouple the different implementation versions into independent handlers.</span></span>

<span data-ttu-id="7d440-122">Son olarak, bir REST mimarisi kullanıyorsanız [iletilir](https://www.infoq.com/articles/mark-baker-hypermedia) hizmetlerinizi sürüm oluşturma için en iyi çözüm olduğunu ve evolvable API'leri izin verme.</span><span class="sxs-lookup"><span data-stu-id="7d440-122">Finally, if you are using a REST architecture, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) is the best solution for versioning your services and allowing evolvable APIs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d440-123">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="7d440-123">Additional resources</span></span>

-   <span data-ttu-id="7d440-124">**Scott Hanselman. ASP.NET Core RESTful Web API'si sürüm kolaylaştırılmış**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span><span class="sxs-lookup"><span data-stu-id="7d440-124">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
<http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span></span>

-   <span data-ttu-id="7d440-125">**Sürüm oluşturma bir RESTful web API'si**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span><span class="sxs-lookup"><span data-stu-id="7d440-125">**Versioning a RESTful web API**
[*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span></span>

-   <span data-ttu-id="7d440-126">**Roy Fielding. Sürüm oluşturma, iletilir ve REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning></span><span class="sxs-lookup"><span data-stu-id="7d440-126">**Roy Fielding. Versioning, Hypermedia, and REST**
<https://www.infoq.com/articles/roy-fielding-on-versioning></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7d440-127">[Önceki] (zaman uyumsuz-ileti-tabanlı-communication.md) [sonraki] (mikro-çözümlenebilme-service-registry.md)</span><span class="sxs-lookup"><span data-stu-id="7d440-127">[Previous] (asynchronous-message-based-communication.md) [Next] (microservices-addressability-service-registry.md)</span></span>