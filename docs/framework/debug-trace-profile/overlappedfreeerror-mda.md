---
title: overlappedFreeError MDA
description: Zapoznaj się z asystentem debugowania zarządzanego w programie overlappedFreeError (MDA) w programie .NET, który może aktywować w przypadku naruszeń dostępu lub uszkodzenia sterty zebranych przez elementy bezużyteczne.
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
ms.openlocfilehash: 1bedb8ad3b9801f0d235371a397c8951ff8723b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254535"
---
# <a name="overlappedfreeerror-mda"></a>overlappedFreeError MDA

`overlappedFreeError`Asystent debugowania zarządzanego (MDA) jest uaktywniany, gdy <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> Metoda jest wywoływana przed ukończeniem operacji nakładania się.  
  
## <a name="symptoms"></a>Objawy  

 Naruszenia dostępu lub uszkodzenie sterty zebranych przez elementy bezużyteczne.  
  
## <a name="cause"></a>Przyczyna  

 Nakładająca się struktura została zwolniona przed ukończeniem operacji. Funkcja, która używa nakładającego się wskaźnika, może później pisać do struktury, po jej zwolnieniu. Może to spowodować uszkodzenie sterty, ponieważ inny obiekt może teraz zajmować ten region.  
  
 To zdarzenie MDA może nie reprezentować błędu, jeśli nakładająca się operacja nie została pomyślnie uruchomiona.  
  
## <a name="resolution"></a>Rozwiązanie  

 Przed wywołaniem metody upewnij się, że operacja we/wy z nakładającą się strukturą została ukończona <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> .  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 To zdarzenie MDA nie ma wpływu na środowisko CLR.  
  
## <a name="output"></a>Dane wyjściowe  

 Poniżej przedstawiono przykładowe dane wyjściowe dla tego MDA.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a>Konfigurowanie  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Organizowanie międzyoperacyjne](../interop/interop-marshaling.md)
