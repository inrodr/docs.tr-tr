---
title: '&lt;Federationconfiguration''a&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9abe07c065dbea67c5ebc4a4490d9f88258130c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltfederationconfigurationgt"></a><span data-ttu-id="bcce1-102">&lt;Federationconfiguration'a&gt;</span><span class="sxs-lookup"><span data-stu-id="bcce1-102">&lt;federationConfiguration&gt;</span></span>
<span data-ttu-id="bcce1-103">Yapılandırır <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) ve <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) kullanırken federe kimlik doğrulaması WS-Federasyon protokolü aracılığıyla.</span><span class="sxs-lookup"><span data-stu-id="bcce1-103">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="bcce1-104">Yapılandırır <xref:System.Security.Claims.ClaimsAuthorizationManager> kullanırken <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> veya <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> talep tabanlı erişim denetimi sağlamak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="bcce1-104">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
 <span data-ttu-id="bcce1-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="bcce1-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="bcce1-106">\<Federationconfiguration'a ></span><span class="sxs-lookup"><span data-stu-id="bcce1-106">\<federationConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcce1-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bcce1-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcce1-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="bcce1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bcce1-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcce1-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="bcce1-110">Attributes</span></span>  
  
|<span data-ttu-id="bcce1-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="bcce1-111">Attribute</span></span>|<span data-ttu-id="bcce1-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bcce1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcce1-113">name</span><span class="sxs-lookup"><span data-stu-id="bcce1-113">name</span></span>|<span data-ttu-id="bcce1-114">Bu Federasyon yapılandırma öğesinin adı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-114">The name of this federation configuration element.</span></span> <span data-ttu-id="bcce1-115">Bu öznitelik, gelecekteki iletişim kuralları için öncelikle bir genişletilebilirlik noktası sağlar.</span><span class="sxs-lookup"><span data-stu-id="bcce1-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="bcce1-116">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-116">Optional.</span></span>|  
|<span data-ttu-id="bcce1-117">identityConfigurationName</span><span class="sxs-lookup"><span data-stu-id="bcce1-117">identityConfigurationName</span></span>|<span data-ttu-id="bcce1-118">Belirtilen kimlik yapılandırma bölümünün adını bir [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) öğesi kullanın.</span><span class="sxs-lookup"><span data-stu-id="bcce1-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element to use.</span></span> <span data-ttu-id="bcce1-119">Bu özniteliği belirtilmezse, varsayılan kimlik yapılandırma bölümü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="bcce1-120">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcce1-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="bcce1-121">Child Elements</span></span>  
  
|<span data-ttu-id="bcce1-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="bcce1-122">Element</span></span>|<span data-ttu-id="bcce1-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bcce1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcce1-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="bcce1-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="bcce1-125">SAM tarafından kullanılan tanımlama bilgisi işleyicisi yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="bcce1-126">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-126">Optional.</span></span>|  
|[<span data-ttu-id="bcce1-127">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="bcce1-127">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="bcce1-128">Şifrelemek ve belirteçlerin şifresini çözmek için kullanılan sertifikayı yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="bcce1-129">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-129">Optional.</span></span>|  
|[<span data-ttu-id="bcce1-130">\<wsFederation ></span><span class="sxs-lookup"><span data-stu-id="bcce1-130">\<wsFederation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|<span data-ttu-id="bcce1-131">WS-Federasyon kimlik doğrulama Modülü (WSFAM) yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="bcce1-132">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bcce1-133">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="bcce1-133">Parent Elements</span></span>  
  
|<span data-ttu-id="bcce1-134">Öğe</span><span class="sxs-lookup"><span data-stu-id="bcce1-134">Element</span></span>|<span data-ttu-id="bcce1-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bcce1-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcce1-136">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="bcce1-136">\<system.identityModel.services></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|<span data-ttu-id="bcce1-137">WS-Federasyon protokolünü kullanarak kimlik doğrulaması için yapılandırma bölümü.</span><span class="sxs-lookup"><span data-stu-id="bcce1-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcce1-138">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bcce1-138">Remarks</span></span>  
 <span data-ttu-id="bcce1-139">\<Federationconfiguration'a > öğesi, iki farklı senaryolar ayarlarında sağlar:</span><span class="sxs-lookup"><span data-stu-id="bcce1-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
-   <span data-ttu-id="bcce1-140">WS-Federasyon pasif Web uygulamasında kullanırken, yapılandırdığınız ayarları ögesinin <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) ve <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="bcce1-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="bcce1-141">Güvenlik belirteci işleyicileri ve sertifikaları ve bileşenleri talep Yetkilendirme Yöneticisi ve talep gibi yapılandırmak için kullanılacak kimlik yapılandırması başvuruda bulunuyor.</span><span class="sxs-lookup"><span data-stu-id="bcce1-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
-   <span data-ttu-id="bcce1-142">Kullanırken <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> veya <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> kodunuzda talep tabanlı erişim denetimi sağlamak için sınıf, talep Yetkilendirme Yöneticisi'ni ve yetkilendirme yapmak için kullanılan ilke yapılandırır kimlik yapılandırması öğesine başvuruda bulunuyor kararlar.</span><span class="sxs-lookup"><span data-stu-id="bcce1-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="bcce1-143">Bu bile pasif Web senaryoları olmayan senaryolarda geçerlidir; Örneğin, Windows Communication Foundation (WCF) uygulamaları veya Web tabanlı olmayan bir uygulama.</span><span class="sxs-lookup"><span data-stu-id="bcce1-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="bcce1-144">Uygulama Pasif bir Web uygulaması değilse [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) öğesi (ve alt ilke öğeleri, varsa) tarafından başvurulan kimlik yapılandırmasının `<federationConfiguration>` öğesi yalnızca ayarları uygulanır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="bcce1-145">Diğerleri yoksayılır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="bcce1-146">Senaryo bağımsız olarak, varsayılan Federasyon yapılandırma çalışma zamanı yükler.</span><span class="sxs-lookup"><span data-stu-id="bcce1-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="bcce1-147">Davranışı aşağıdaki gibi tanımlanır:</span><span class="sxs-lookup"><span data-stu-id="bcce1-147">The behavior is defined as follows:</span></span>  
  
1.  <span data-ttu-id="bcce1-148">Varsa hiçbir `<federationConfiguration>` öğe yok, çalışma zamanı Federasyon yapılandırmasını oluşturur ve varsayılan değerlerle doldurur.</span><span class="sxs-lookup"><span data-stu-id="bcce1-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="bcce1-149">Bu varsayılan Federasyon yapılandırma, varsayılan kimlik yapılandırması başvurur.</span><span class="sxs-lookup"><span data-stu-id="bcce1-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2.  <span data-ttu-id="bcce1-150">Tek bir varsa `<federationConfiguration>` öğesi mevcutsa, olup, adlı adlandırılmamış veya bağımsız olarak varsayılan Federasyon yapılandırması.</span><span class="sxs-lookup"><span data-stu-id="bcce1-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="bcce1-151">Varsa, `identityConfiguration` özniteliği belirtilmediyse, adlandırılmış kimlik yapılandırması başvurulur; Aksi takdirde varsayılan kimlik yapılandırması başvuruluyor.</span><span class="sxs-lookup"><span data-stu-id="bcce1-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3.  <span data-ttu-id="bcce1-152">Bir adlandırılmamış varsa `<federationConfiguration>` öğe varsa, varsayılan Federasyon yapılandırma budur.</span><span class="sxs-lookup"><span data-stu-id="bcce1-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="bcce1-153">Varsa, `identityConfiguration` özniteliği belirtilmediyse, adlandırılmış kimlik yapılandırması başvurulur; Aksi takdirde varsayılan kimlik yapılandırması başvuruluyor.</span><span class="sxs-lookup"><span data-stu-id="bcce1-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4.  <span data-ttu-id="bcce1-154">Birden çok adlandırırsanız `<federationConfiguration>` öğeleri mevcut ve Hayır adlandırılmamış `<federationConfiguration>` öğesi mevcutsa, bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="bcce1-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="bcce1-155">Genellikle, yalnızca tek bir `<federationConfiguration>` bölümünde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="bcce1-156">Bu bölümde varsayılan Federasyon yapılandırmadır.</span><span class="sxs-lookup"><span data-stu-id="bcce1-156">This section is the default federation configuration.</span></span> <span data-ttu-id="bcce1-157">Birden çok, benzersiz olarak adlandırılmış belirtebilir `<federationConfiguration>` öğeleri; adlandırılmamış farklı bir Federasyon yapılandırma yüklemek istiyorsanız, ancak bu durumda, bir işleyici sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="bcce1-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="bcce1-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>Olay ve kümesi <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> özelliği işleyicisine içinde bir <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> uygun değerlerle başlatılan nesne `<federationConfiguration>` yapılandırma dosyası öğesi.</span><span class="sxs-lookup"><span data-stu-id="bcce1-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="bcce1-159">`<federationConfiguration>` Öğesi ile temsil edilir <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="bcce1-160">Yapılandırma nesnesi tarafından temsil edilen <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bcce1-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="bcce1-161">Tek bir <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> örneği ayarlanmış <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> özelliği ve uygulama için Federasyon yapılandırma sağlar.</span><span class="sxs-lookup"><span data-stu-id="bcce1-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcce1-162">Örnek</span><span class="sxs-lookup"><span data-stu-id="bcce1-162">Example</span></span>  
 <span data-ttu-id="bcce1-163">Aşağıdaki XML gösterildiği bir `<federationConfiguration>` WSFAM ayarlarını belirtir ve belirten öğesi varsayılan tanımlama bilgisi işleyicisi (örneği <xref:System.IdentityModel.Services.ChunkedCookieHandler> sınıfı) SAM tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="bcce1-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bcce1-164">Bu örnekte, tanımlama bilgisi işleyici ne WSFAM HTTPS kullanmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="bcce1-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="bcce1-165">Bunun nedeni, `requireHttps` özniteliği `<wsFederation>` öğesi ve `requireSsl` özniteliği `<cookieHandlerElement>` olan `false`.</span><span class="sxs-lookup"><span data-stu-id="bcce1-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="bcce1-166">Bir güvenlik riski sayılabilir gibi bu ayarların çoğu üretim ortamları için önerilmez.</span><span class="sxs-lookup"><span data-stu-id="bcce1-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"   
      issuer="http://localhost:15839/wsFederationSTS/Issue"   
      realm="http://localhost:50969/" reply="http://localhost:50969/"   
      requireHttps="false"   
      signOutReply="http://localhost:50969/SignedOutPage.html"   
      signOutQueryString="Param1=value2&Param2=value2"   
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcce1-167">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bcce1-167">See Also</span></span>  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="bcce1-168">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="bcce1-168">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)