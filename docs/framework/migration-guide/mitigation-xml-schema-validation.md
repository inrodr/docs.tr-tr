---
title: 'Azaltma: XML Şema Doğrulaması'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e757962f02cce104d8c5ab805d0481861cab426e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389219"
---
# <a name="mitigation-xml-schema-validation"></a>Azaltma: XML Şema Doğrulaması
İçinde [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD şema doğrulaması, bileşik bir anahtar kullanılıyor ve bir anahtar boş ise benzersiz kısıtlamayı ihlal algılar.  
  
## <a name="impact"></a>Etki  
 Bu değişikliğin etkisini en az olmalıdır: şema belirtimine dayalı olarak, şema doğrulama hatası varsa beklenen `xsd:unique` boş bir anahtar ile bir bileşik anahtarı kullanılarak ihlal etti.  
  
## <a name="mitigation"></a>Azaltma  
 Bileşik anahtar bir boş anahtar varsa, şema doğrulama hatası olup olmadığını algıladı yapılandırılabilir bir özelliğidir:  
  
-   Hedefleyen uygulamalarla başlangıç [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], şema doğrulama hatası algılama, varsayılan olarak etkindir; böylece şema doğrulama hatası algılanmadı ancak bunun dışında geri çevirme mümkündür.  
  
-   Altında çalışacağı uygulamalarda [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ancak hedef [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] ve önceki sürümleri, varsayılan olarak bir şema doğrulama hatası algılanmadı; böylece şema doğrulama hatası algılandı ancak onu kabul etmek mümkündür.  
  
 Bu davranış kullanarak yapılandırılabilir <xref:System.AppContext> değerini tanımlamak için sınıf `System.Xml.IgnoreEmptyKeySequences` geçin. Anahtarın varsayılan değeri olduğundan `false` (boş anahtar sıraları değil yoksayılır), hedef uygulamaları [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] dışında davranış anahtarın değerini ayarlamak için aşağıdaki kodu kullanarak seçebilirsiniz `true`:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Hedef uygulamalar için [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] ve önceki sürümleri, anahtarın varsayılan değeri olduğundan `true` (boş anahtar sıraları yoksayılır) kullanarak bir şema doğrulama hatası boş anahtarlı bileşik bir anahtar oluşturmak emin olmak mümkündür anahtarın değerini ayarlamak için kod aşağıdaki `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden Hedefleme Değişiklikleri](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
