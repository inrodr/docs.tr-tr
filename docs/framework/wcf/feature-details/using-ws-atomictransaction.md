---
title: WS-AtomicTransaction Kullanma
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7046add86f1255b222640912be02c08b98cb9cae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="4ce68-102">WS-AtomicTransaction Kullanma</span><span class="sxs-lookup"><span data-stu-id="4ce68-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="4ce68-103">WS-AtomicTransaction (WS-AT) bir birlikte çalışabilen işlem protokolüdür.</span><span class="sxs-lookup"><span data-stu-id="4ce68-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="4ce68-104">Web hizmeti iletileri kullanarak dağıtılmış işlemler akış ve heterojen işlem altyapıları arasında birlikte çalışabilir bir şekilde koordine sağlar.</span><span class="sxs-lookup"><span data-stu-id="4ce68-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="4ce68-105">WS-AT dağıtılmış uygulamalar, işlem yöneticileri ve kaynak yöneticileri arasında bir atomik sonucu sürücü için iki aşamalı yürütme protokolü kullanır.</span><span class="sxs-lookup"><span data-stu-id="4ce68-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="4ce68-106">WS-AT uygulama [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sağlayan Microsoft Dağıtılmış İşlem Düzenleyicisi (MSDTC) işlem Manager'a yerleşik bir protokolü hizmeti içerir.</span><span class="sxs-lookup"><span data-stu-id="4ce68-106">The WS-AT implementation [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="4ce68-107">WS-AT kullanarak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamaları işlemleri üçüncü taraf teknolojisi kullanılarak oluşturulan birlikte çalışabilen Web Hizmetleri dahil olmak üzere diğer uygulamalar için akış.</span><span class="sxs-lookup"><span data-stu-id="4ce68-107">Using WS-AT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="4ce68-108">İşlem bir istemci uygulaması ve bir sunucu uygulaması arasında akan, kullanılan işlem protokolü sunucunun seçili istemci uç noktada sunan bağlama tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="4ce68-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="4ce68-109">Bazı [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] belirtmek için sistem tarafından sağlanan bağlamalar varsayılan `OleTransactions` Protokolü başkalarının WS-AT belirtmek için varsayılan sırada işlem yayma biçimi olarak.</span><span class="sxs-lookup"><span data-stu-id="4ce68-109">Some [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="4ce68-110">Belirtilen bağlama içindeki işlem protokolü seçimi program aracılığıyla da değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4ce68-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="4ce68-111">Protokol etkiler Seçimi:</span><span class="sxs-lookup"><span data-stu-id="4ce68-111">The choice of protocol influences:</span></span>  
  
-   <span data-ttu-id="4ce68-112">İstemciden sunucuya işlem akış için kullanılan ileti üstbilgilerini biçimi.</span><span class="sxs-lookup"><span data-stu-id="4ce68-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
-   <span data-ttu-id="4ce68-113">İşlem sonucunu çözümlemek amacıyla sunucunun işlem istemcinin işlem yöneticisi arasında iki aşamalı yürütme Protokolü çalıştırmak için kullanılan ağ protokolü.</span><span class="sxs-lookup"><span data-stu-id="4ce68-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="4ce68-114">Sunucu ve istemci kullanılarak yazılan, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], WS-AT kullanmanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="4ce68-114">If the server and client are written using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you do not need to use WS-AT.</span></span> <span data-ttu-id="4ce68-115">Bunun yerine, varsayılan ayarları kullanabilir `NetTcpBinding` ile `TransactionFlow` kullanacağı etkin öznitelik `OleTransactions` yerine protokol.</span><span class="sxs-lookup"><span data-stu-id="4ce68-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="4ce68-116">[ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4ce68-116"> [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="4ce68-117">Aksi takdirde, üçüncü taraf teknolojilerini yerleşik Web hizmetlerine işlemleri akan gerekiyorsa, WS-AT kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4ce68-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce68-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4ce68-118">See Also</span></span>  
 [<span data-ttu-id="4ce68-119">WS-Atomic işlem desteğini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="4ce68-119">Configuring WS-Atomic Transaction Support</span></span>](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)