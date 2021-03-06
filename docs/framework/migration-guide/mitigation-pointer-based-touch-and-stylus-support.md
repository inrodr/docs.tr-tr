---
title: 'Azaltma: İşaretçi tabanlı dokunma ve Kalem desteği'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da7d55b34bc21f0c11f13565d017587b4276bad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387786"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a>Azaltma: İşaretçi tabanlı dokunma ve Kalem desteği

.NET Framework 4.7 hedefleyen ve Windows 10 oluşturucuları güncelleştirmesi ile başlayarak Windows sistemlerinde çalışan WPF uygulamaları isteğe bağlı bir etkinleştirebilir `WM_POINTER`-WPF dokunma/kalem yığın tabanlı.

## <a name="impact"></a>Etki

İşaretçi tabanlı dokunma/kalem desteğini açıkça etkinleştirmeyin geliştiriciler WPF dokunma/kalem davranışında değişiklik görmeniz gerekir.

Aşağıdaki bilinen geçerli sorunlar isteğe bağlı olan `WM_POINTER`-touch/kalem yığın tabanlı:

- Gerçek zamanlı mürekkep desteği yoktur.

   Mürekkep ve Kalem eklentileri çalışmaya devam ederken, düşük performans açabilir kullanıcı Arabirimi iş parçacığı üzerinde işlenir.

- Davranış değişiklikleri fare olayları dokunma/kalem olaylardan yükseltmesine değişiklikleri nedeniyle.

  - İşleme farklı davranabilir.

  - Sürükle ve bırak dokunma girişi için uygun bildirim göstermez. (Bu kalem giriş etkilemez.)

  - Sürükle ve bırak artık dokunma/kalem olaylarına başlatılabilir.

      Fare girişi algılandığında kadar bu uygulama potansiyel olarak askıda kalabilir. Bunun yerine, geliştiricilerin Sürükle başlatmak ve bu fare olayları bırakma gerekir.

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a>Dokunma/kalem WM_POINTER tabanlı desteklemek için seçim

Bu yığın etkinleştirmek istediğiniz geliştiriciler, uygulamanın app.config dosyasına aşağıdaki ekleyebilirsiniz:

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

Bu girdi kaldırma veya değeri ayarını `false` Bu isteğe bağlı yığını kapatır.

## <a name="see-also"></a>Ayrıca bkz.

[.NET Framework 4.7 yeniden hedefleme değişiklikleri](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
