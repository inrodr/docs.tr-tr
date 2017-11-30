---
title: "Esnek uygulamaları uygulama"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Esnek uygulamaları uygulama"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a6fc2f4c963d857be06e194468e2f8514437dd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="f908d-104">Esnek uygulamaları uygulama</span><span class="sxs-lookup"><span data-stu-id="f908d-104">Implementing Resilient Applications</span></span>

<span data-ttu-id="f908d-105">*Mikro hizmet ve bulut tabanlı uygulamalar kesinlikle sonuçta ortaya çıkan kısmi hataları çekirdeğin gerekir. Bu kısmi hatalarına dayanıklı olması için uygulamanız tasarlamanız gerekir.*</span><span class="sxs-lookup"><span data-stu-id="f908d-105">*Your microservice and cloud based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="f908d-106">Dayanıklılık, arızalardan kurtarmak ve çalışmaya devam yeteneğidir.</span><span class="sxs-lookup"><span data-stu-id="f908d-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="f908d-107">Hataları, önleme ancak hataları olacağını olgu kabul ettiğini ve bunlara kapalı kalma süresi veya veri kaybı engelleyen bir şekilde yanıt hakkında değil.</span><span class="sxs-lookup"><span data-stu-id="f908d-107">It is not about avoiding failures, but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="f908d-108">Dayanıklılık bir hatadan sonra uygulamaya tam çalışır bir duruma geri dönmek için hedefidir.</span><span class="sxs-lookup"><span data-stu-id="f908d-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="f908d-109">Tasarım ve mikro tabanlı bir uygulama dağıtım için yeterli görevdir.</span><span class="sxs-lookup"><span data-stu-id="f908d-109">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="f908d-110">Ancak uygulamanızın hatası çeşit belirli olduğu bir ortamda çalışmaya devam etmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="f908d-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="f908d-111">Bu nedenle, uygulamanızın dayanıklı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="f908d-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="f908d-112">Ağ kesintileri veya düğümler veya bulutta kilitlenen VM'ler gibi kısmi hatalarıyla başa çıkacak şekilde tasarlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f908d-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="f908d-113">Bir küme içinde farklı bir düğüme taşınmasını bile mikro (kapsayıcı), uygulama içinde aralıklı kısa hatalarına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="f908d-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="f908d-114">Uygulamanızın birçok ayrı bileşen sistem durumu izleme özelliklerini de eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="f908d-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="f908d-115">Bu bölümdeki yönergeleri izleyerek, karmaşık ve bulut tabanlı dağıtımlarda geçici kapalı kalma süresi tüm sorunsuz çalışabilmeniz için bir uygulama veya ortaya normal duraklamalarla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f908d-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f908d-116">[Önceki] (.. / microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [sonraki] (tanıtıcı kısmi failure.md)</span><span class="sxs-lookup"><span data-stu-id="f908d-116">[Previous] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Next] (handle-partial-failure.md)</span></span>