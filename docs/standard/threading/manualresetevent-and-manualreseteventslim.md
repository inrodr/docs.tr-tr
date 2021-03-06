---
title: ManualResetEvent ve ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85d0c5c291743c6daac549e15d479fcf332235c
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452829"
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent ve ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Sınıf işareti verilen sonra el ile sıfırlamanız gerekir bir yerel bekleme tanıtıcısı olayı temsil eder. Bu sınıfın temel sınıfının, özel bir durum temsil <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Bkz: [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) el ile özellikleri ve kullanmak için kavramsal belgelerde olayların sıfırlayın.  
  
 A <xref:System.Threading.ManualResetEvent> nesne kadar sinyal kalır, <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> yöntemi çağrılır. Nesnenin durumu sinyal sırada iş parçacığı veya bu sinyal sonra olay beklemek iş parçacığı beklenirken, herhangi bir sayı serbest bırakılabilir.
  
 İçinde [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], kullanabileceğiniz <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> bekleme süresini çok kısa olması beklenir ve olay, bir işlem sınırını aşan değil zamanı daha iyi performans için sınıf. <xref:System.Threading.ManualResetEventSlim> Olayın sinyal haline beklerken kısa bir süre için dönen meşgul kullanır. Bekleme süresini kısa olduğunda dönme beklemeden çok daha düşük maliyetli bekleme tanıtıcıları kullanılarak olabilir. Ancak, olay belirli bir zaman döneminde sinyal haline değil <xref:System.Threading.ManualResetEventSlim> resorts normal olay işleyici bekleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [AutoResetEvent](autoresetevent.md)  
- [SpinWait](spinwait.md)  
- [Semaphore ve SemaphoreSlim](semaphore-and-semaphoreslim.md)
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [İş parçacığı nesneleri ve özellikleri](threading-objects-and-features.md)  
- [İş parçacığı oluşturma](index.md)  
