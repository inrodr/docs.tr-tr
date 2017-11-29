---
title: "Uygulama Ayarları Şeması"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d51d06895e61be60bbe9153eacb2028cb32a1fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="app-settings-schema"></a><span data-ttu-id="ecbda-102">Uygulama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="ecbda-102">App Settings schema</span></span>

<span data-ttu-id="ecbda-103">Dosya yolları, XML Web hizmeti URL'leri veya diğer özel yapılandırma bilgilerini bir uygulama gibi özel uygulama ayarlarını içerir.</span><span class="sxs-lookup"><span data-stu-id="ecbda-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="ecbda-104">[**\<Yapılandırma >**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ecbda-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ecbda-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ecbda-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="ecbda-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ekleme >**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="ecbda-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="ecbda-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Clear >**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="ecbda-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="ecbda-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<kaldırma >**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="ecbda-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="ecbda-109">Öğe</span><span class="sxs-lookup"><span data-stu-id="ecbda-109">Element</span></span> | <span data-ttu-id="ecbda-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ecbda-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="ecbda-111">**\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="ecbda-111">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="ecbda-112">İçeren  **\<Ekle >**,  **\<temizleyin >**, ve  **\<kaldırmak >** etiketler denetim uygulama ayarları.</span><span class="sxs-lookup"><span data-stu-id="ecbda-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="ecbda-113">İsteğe bağlı bir sahip **dosya** özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ecbda-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="ecbda-114">**\<ekleme >**</span><span class="sxs-lookup"><span data-stu-id="ecbda-114">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="ecbda-115">Bir ayar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="ecbda-115">Defines a setting.</span></span> <span data-ttu-id="ecbda-116">Alt  **\<appSettings >**.</span><span class="sxs-lookup"><span data-stu-id="ecbda-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="ecbda-117">Gerektirir **anahtar** ve **değeri** öznitelikleri.</span><span class="sxs-lookup"><span data-stu-id="ecbda-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="ecbda-118">**\<Clear >**</span><span class="sxs-lookup"><span data-stu-id="ecbda-118">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="ecbda-119">Tüm ayarları siler.</span><span class="sxs-lookup"><span data-stu-id="ecbda-119">Clears all settings.</span></span> <span data-ttu-id="ecbda-120">Alt  **\<appSettings >**.</span><span class="sxs-lookup"><span data-stu-id="ecbda-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="ecbda-121">Öznitelikleri yok.</span><span class="sxs-lookup"><span data-stu-id="ecbda-121">Has no attributes.</span></span> |
| [<span data-ttu-id="ecbda-122">**\<kaldırma >**</span><span class="sxs-lookup"><span data-stu-id="ecbda-122">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="ecbda-123">Bir ayar kaldırır.</span><span class="sxs-lookup"><span data-stu-id="ecbda-123">Removes a setting.</span></span> <span data-ttu-id="ecbda-124">Alt  **\<appSettings >**.</span><span class="sxs-lookup"><span data-stu-id="ecbda-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="ecbda-125">Gerektiren bir **anahtar** özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ecbda-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="ecbda-126">\<appSettings > öğesi</span><span class="sxs-lookup"><span data-stu-id="ecbda-126">\<appSettings> element</span></span>

<span data-ttu-id="ecbda-127">Bu öğeyi içeren  **\<Ekle >**,  **\<temizleyin >**, ve  **\<Kaldır >** etiketler denetim uygulama ayarları.</span><span class="sxs-lookup"><span data-stu-id="ecbda-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="ecbda-128">İçin isteğe bağlı bir öznitelik tanımlar **dosya**.</span><span class="sxs-lookup"><span data-stu-id="ecbda-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="ecbda-129">\<Ekle > öğesi</span><span class="sxs-lookup"><span data-stu-id="ecbda-129">\<add> element</span></span>

<span data-ttu-id="ecbda-130">Özel uygulama ayarı ad/değer çifti olarak uygulama ayarları koleksiyonuna ekler.</span><span class="sxs-lookup"><span data-stu-id="ecbda-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="ecbda-131">Özniteliklerini tanımlayan **anahtar** ve **değeri**.</span><span class="sxs-lookup"><span data-stu-id="ecbda-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="ecbda-132">\<Clear > öğesi</span><span class="sxs-lookup"><span data-stu-id="ecbda-132">\<clear> element</span></span>

<span data-ttu-id="ecbda-133">Devralınan özel uygulama ayarlarına yapılan tüm başvuruları kaldırır ve tarafından eklenen başvurulara izin verir  **\<Ekle >** aşağıdaki öğeleri  **\<temizleyin >** öğesi.</span><span class="sxs-lookup"><span data-stu-id="ecbda-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="ecbda-134">Öznitelikleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="ecbda-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="ecbda-135">\<kaldırma > öğesi</span><span class="sxs-lookup"><span data-stu-id="ecbda-135">\<remove> element</span></span>

<span data-ttu-id="ecbda-136">Devralınan özel uygulama ayarı için bir başvuru uygulama ayarları koleksiyonundan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="ecbda-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="ecbda-137">İçin bir öznitelik tanımlar **anahtar**.</span><span class="sxs-lookup"><span data-stu-id="ecbda-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="ecbda-138">Örnek</span><span class="sxs-lookup"><span data-stu-id="ecbda-138">Example</span></span>

<span data-ttu-id="ecbda-139">Aşağıdaki örnek, bir dış uygulama ayarları dosyası gösterir (*custom.config*), özel uygulama ayarını tanımlar:</span><span class="sxs-lookup"><span data-stu-id="ecbda-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="ecbda-140">Aşağıdaki örnek, dış ayarları dosyasında ayarı kullanır ve bir uygulama ayarı kendi ayarlar uygulama yapılandırma dosyası gösterir:</span><span class="sxs-lookup"><span data-stu-id="ecbda-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ecbda-141">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ecbda-141">See also</span></span>

<span data-ttu-id="ecbda-142">[Uygulama ayarlarına genel bakış](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ecbda-142">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="ecbda-143">Uygulama ayarları mimarisi</span><span class="sxs-lookup"><span data-stu-id="ecbda-143">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)