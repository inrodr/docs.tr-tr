---
title: "Etkinlik Kimliği Yayma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c61087102148688678d868ce25a9cb63315ed65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="activity-id-propagation"></a><span data-ttu-id="efd1d-102">Etkinlik Kimliği Yayma</span><span class="sxs-lookup"><span data-stu-id="efd1d-102">Activity ID Propagation</span></span>
<span data-ttu-id="efd1d-103">ServiceModel Etkinlik izleme etkin (ServiceModel yayma) ya da devre dışı (kullanıcıdan kullanıcıya Etkinlik yayma) olduğunda yayma gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="efd1d-103">Propagation happens when ServiceModel activity tracing is enabled (ServiceModel propagation) or disabled (User-to-User activity propagation).</span></span>  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a><span data-ttu-id="efd1d-104">ServiceModel Etkinlik izleme etkin</span><span class="sxs-lookup"><span data-stu-id="efd1d-104">ServiceModel Activity Tracing is Enabled</span></span>  
 <span data-ttu-id="efd1d-105">ServiceModel ActivityTracing etkinleştirilirse, yayma ProcessAction etkinlikler arasında gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="efd1d-105">If ServiceModel ActivityTracing is enabled, propagation happens between ProcessAction activities.</span></span>  
  
### <a name="server"></a><span data-ttu-id="efd1d-106">Sunucu</span><span class="sxs-lookup"><span data-stu-id="efd1d-106">Server</span></span>  
 <span data-ttu-id="efd1d-107">Zaman `propagateActivity` özniteliği `true` hem istemci hem de sunucu Kimliğini `ProcessAction` sunucu etkinliğinde, yayılan Kimliğinde aynıdır `ActivityId` ileti üstbilgisi.</span><span class="sxs-lookup"><span data-stu-id="efd1d-107">When the `propagateActivity` attribute is set to `true` on both the client and server, the ID of the `ProcessAction` activity in the server is identical to the ID in the propagated `ActivityId` message header.</span></span>  
  
 <span data-ttu-id="efd1d-108">Durumlarda `ActivityId` başlığıdır iletide (diğer bir deyişle, `propagateActivity` = `false` istemci üzerinde), veya ne zaman `propagateActivity` = `false` sunucuda, sunucunun yeni bir etkinlik kimliği oluşturur.</span><span class="sxs-lookup"><span data-stu-id="efd1d-108">When no `ActivityId` header is present in the message (that is, `propagateActivity`=`false` on the client), or when `propagateActivity`=`false` on the server, the server generates a new activity ID.</span></span>  
  
### <a name="client"></a><span data-ttu-id="efd1d-109">İstemci</span><span class="sxs-lookup"><span data-stu-id="efd1d-109">Client</span></span>  
 <span data-ttu-id="efd1d-110">İstemci zaman uyumlu olarak tek iş parçacıklı ise, istemci, herhangi bir ayarı yok sayar `propagateActivity` istemci veya sunucu.</span><span class="sxs-lookup"><span data-stu-id="efd1d-110">If the client is synchronously single threaded, the client disregards any settings of `propagateActivity` at the client or server.</span></span> <span data-ttu-id="efd1d-111">Bunun yerine, yanıt isteği etkinliğinde ele alınır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-111">Instead, the response is handled in the request activity.</span></span> <span data-ttu-id="efd1d-112">İstemci zaman uyumsuz veya zaman uyumlu ise birden çok iş parçacıklı, `propagateActivity` = `true` istemci ve sunucu tarafından gönderilen ileti içinde bir etkinlik kimliği üstbilgisi yok, istemci etkinlik kimliği gelen iletiyi alır ve aktarır Yayılan etkinlik kimliğini içeren bir işlem eylem etkinliği</span><span class="sxs-lookup"><span data-stu-id="efd1d-112">If the client is asynchronous or synchronous multithreaded, `propagateActivity`=`true` in the client, and there is an activity ID header in the message sent by the server, the client retrieves the activity ID from the message, and transfers to the Process Action activity that contains the propagated activity ID.</span></span> <span data-ttu-id="efd1d-113">Aksi durumda, istemci yeni bir işlem eylem etkinlik işlemi iletisi etkinliğinden aktarır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-113">Otherwise, the client transfers from Process Message activity to a new Process Action activity.</span></span> <span data-ttu-id="efd1d-114">Yeni bir işlem eylem etkinlik için fazladan bu aktarım tutarlılık için yapılır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-114">This extra transfer to a new Process Action activity is done for consistency.</span></span> <span data-ttu-id="efd1d-115">İş parçacığı yanıt iletisi işlenmek üzere atandığında bu etkinliği içinde istemci yerel iş parçacığı bağlamından BeginCall etkinliğin etkinlik kimliği alır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-115">Inside this activity, the client retrieves the activity ID of the BeginCall activity from the local thread context, when the thread is allocated for response message processing.</span></span> <span data-ttu-id="efd1d-116">Ardından, ilk işlem eylem etkinlik aktarır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-116">It then transfers to the initial Process Action activity.</span></span>  
  
 <span data-ttu-id="efd1d-117">İstemci, istemci çift yönlü ise, iletiyi alan sunucuda görür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-117">If the client is duplex, the client acts as server on receiving the message.</span></span>  
  
### <a name="propagation-in-fault-messages"></a><span data-ttu-id="efd1d-118">Hata iletileri yayma</span><span class="sxs-lookup"><span data-stu-id="efd1d-118">Propagation in Fault Messages</span></span>  
 <span data-ttu-id="efd1d-119">Geçerli işleme ve hata iletileri arasında fark yoktur.</span><span class="sxs-lookup"><span data-stu-id="efd1d-119">There is no difference in handling valid and fault messages.</span></span> <span data-ttu-id="efd1d-120">Varsa `propagateActivity` = `true`, SOAP hata ileti üstbilgilerini eklenen etkinlik kimliği ortam etkinlik aynıdır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-120">If `propagateActivity`=`true`, the activity ID added to the SOAP fault message headers is identical to the ambient activity.</span></span>  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a><span data-ttu-id="efd1d-121">ServiceModel etkinliği izleme devre dışı bırakıldı</span><span class="sxs-lookup"><span data-stu-id="efd1d-121">ServiceModel Activity Tracing is Disabled</span></span>  
 <span data-ttu-id="efd1d-122">ServiceModel ActivityTracing devre dışıysa, yayma ServiceModel etkinlikleri giderek olmadan doğrudan kullanıcı kodu etkinlikler arasında oluşur.</span><span class="sxs-lookup"><span data-stu-id="efd1d-122">If ServiceModel ActivityTracing is disabled, propagation occurs between user code activities directly without going through ServiceModel activities.</span></span> <span data-ttu-id="efd1d-123">Kullanıcı tanımlı etkinlik kimliği de ileti etkinlik kimliği üstbilgisi dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-123">A user-defined activity ID is also propagated through the message activity ID header.</span></span>  
  
 <span data-ttu-id="efd1d-124">Varsa `propagateActivity` = `true` ve `ActivityTracing` = `off` ServiceModel izleme dinleyicisi (bağımsız olarak izleme üzerinde ServiceModel etkinleştirilip etkinleştirilmediğini gösterir) istemci veya sunucu üzerinde aşağıdakiler:</span><span class="sxs-lookup"><span data-stu-id="efd1d-124">If `propagateActivity`=`true` and `ActivityTracing`=`off` for a ServiceModel trace listener (regardless of whether tracing is enabled on ServiceModel), the following happen on either the client or server:</span></span>  
  
-   <span data-ttu-id="efd1d-125">Bir ileti biçimlendirilmiş kadar işlem isteği veya yanıtı göndermeyi, TLS etkinlik kimliği kullanıcı kodu dışında yayılır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-125">On operation request or sending response, the activity ID in TLS is propagated out of user code until a message is formed.</span></span> <span data-ttu-id="efd1d-126">Gönderilmeden önce bir etkinlik kimliği üstbilgisi da iletisine eklenir.</span><span class="sxs-lookup"><span data-stu-id="efd1d-126">An activity ID header is also inserted into the message before it is sent.</span></span>  
  
-   <span data-ttu-id="efd1d-127">Alınan ileti nesne oluşturulduktan hemen sonra isteği alındığında veya yanıt alma, etkinlik kimliği ileti başlığından alınır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-127">On receiving request or receiving response, the activity ID is retrieved from the message header as soon as the received message object is created.</span></span> <span data-ttu-id="efd1d-128">Kullanıcı kodu ulaşılana kadar kapsamdan ileti kaybolur hemen TLS etkinlik kimliği yayılır.</span><span class="sxs-lookup"><span data-stu-id="efd1d-128">The activity ID in TLS is propagated as soon as the message disappears from scope until user code is reached.</span></span>  
  
 <span data-ttu-id="efd1d-129">Bu eylemler güvence altına kullanıcı izleri yayma açıksa aynı etkinlik içindeki görünür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-129">These actions guarantee that user traces will appear in the same activity if propagation is on.</span></span> <span data-ttu-id="efd1d-130">Ancak, üzerinde ServiceModel izlemeleri garanti etmez.</span><span class="sxs-lookup"><span data-stu-id="efd1d-130">However, it makes no guarantee on ServiceModel traces.</span></span> <span data-ttu-id="efd1d-131">ServiceModel izlemeleri bir kullanıcı kodu etkinliğini ortaya yalnızca bu izlemeler işlenmesini kullanıcı kodu etkinliği belirlendiği aynı iş parçacığı üzerinde yürütülür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-131">ServiceModel traces occur in a user code activity only if the processing of those traces is executed on the same thread where the user code activity was set.</span></span>  
  
 <span data-ttu-id="efd1d-132">Genel olarak, ServiceModel izlemelerini aşağıdaki konumlarda gösterilebilir:</span><span class="sxs-lookup"><span data-stu-id="efd1d-132">In general, ServiceModel traces can be observed in the following places:</span></span>  
  
-   <span data-ttu-id="efd1d-133">ServiceModel izleme devre dışıysa, tüm verilmiş izlemeleri kullanıcı etkinlikleri görünür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-133">If ServiceModel tracing is disabled, all emitted traces appear in user activities.</span></span> <span data-ttu-id="efd1d-134">Yayma hem sunucu hem de istemci etkinleştirildiğinde bu izleri aynı etkinlik içindeki olur.</span><span class="sxs-lookup"><span data-stu-id="efd1d-134">If propagation is enabled at both the server and client, these traces will be in the same activity.</span></span>  
  
-   <span data-ttu-id="efd1d-135">Yayma üzerindeki her iki End etkinleştirilirse ServiceModel izleme etkinleştirilir, ancak ActivityTracing devre dışı ise, kullanıcı izlemeleri aynı etkinlik içindeki görünür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-135">If ServiceModel tracing is enabled, but ActivityTracing is disabled, user traces appear in the same activity if propagation is enabled on both ends.</span></span> <span data-ttu-id="efd1d-136">İş parçacığı etkinliği başlangıçta ayarlandığı kullanıcı kodu işleme olarak da meydana gelen sürece ServiceModel izlemeleri varsayılan 0000 etkinlik görünür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-136">ServiceModel traces appear in the default 0000 activity, unless they occur in the same thread as the user code processing where the activity is initially set.</span></span>  
  
-   <span data-ttu-id="efd1d-137">ServiceModel izleme ve ActivityTracing etkinleştirilirse, kullanıcı tanımlı aktivitelerde kullanıcı izlemeleri görünür ve ServiceModel izlemeleri ServiceModel tanımlı etkinlikler görünür.</span><span class="sxs-lookup"><span data-stu-id="efd1d-137">If both ServiceModel tracing and ActivityTracing are enabled, user traces appear in user-defined activities, and ServiceModel traces appear in ServiceModel-defined activities.</span></span> <span data-ttu-id="efd1d-138">Yayma ServiceModel düzeyinde gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="efd1d-138">Propagation happens at ServiceModel level.</span></span>