---
title: '&lt;contractTypeNames&gt; &lt;ekleme&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bebea15e6d1f24c95905355dbced33aa9c5150f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="9209a-102">&lt;contractTypeNames&gt; &lt;ekleme&gt;</span><span class="sxs-lookup"><span data-stu-id="9209a-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="9209a-103">Aranan Hizmetleri ve genellikle ararken bir hizmet için kullanılan ölçüt sözleşme adını belirtir. bir yapılandırma öğesi.</span><span class="sxs-lookup"><span data-stu-id="9209a-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="9209a-104">Birden fazla sözleşme adı belirtilmezse, yalnızca hizmet uç noktaları tüm sözleşmeleri eşleşen yanıt gönderir.</span><span class="sxs-lookup"><span data-stu-id="9209a-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="9209a-105">İçinde unutmayın [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], bir uç nokta yalnızca bir sözleşme destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="9209a-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="9209a-106">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9209a-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="9209a-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="9209a-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9209a-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9209a-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9209a-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="9209a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9209a-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="9209a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9209a-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="9209a-111">Attributes</span></span>  
  
|<span data-ttu-id="9209a-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="9209a-112">Attribute</span></span>|<span data-ttu-id="9209a-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9209a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9209a-114">name</span><span class="sxs-lookup"><span data-stu-id="9209a-114">name</span></span>|<span data-ttu-id="9209a-115">Sözleşme türünün adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="9209a-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="9209a-116">ad alanı</span><span class="sxs-lookup"><span data-stu-id="9209a-116">namespace</span></span>|<span data-ttu-id="9209a-117">Sözleşme türünün ad alanını belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="9209a-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9209a-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="9209a-118">Child Elements</span></span>  
 <span data-ttu-id="9209a-119">Yok.</span><span class="sxs-lookup"><span data-stu-id="9209a-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9209a-120">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="9209a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9209a-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="9209a-121">Element</span></span>|<span data-ttu-id="9209a-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9209a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9209a-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="9209a-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="9209a-124">Sözleşme tür adları topluluğu.</span><span class="sxs-lookup"><span data-stu-id="9209a-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9209a-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9209a-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>