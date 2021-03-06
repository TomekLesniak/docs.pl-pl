---
title: invalidIUnknown MDA
description: Przejrzyj invalidIUnknown Managed Debug Assistant (MDA), który jest uaktywniany po przekazaniu nieprawidłowego wskaźnika IUnknown do kodu zarządzanego z kodu natywnego.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 8e7ca6c9c43c4f507d235c879498b2e831c6eba9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272543"
---
# <a name="invalidiunknown-mda"></a>invalidIUnknown MDA

`invalidIUnknown`Asystent debugowania zarządzanego (MDA) jest uaktywniany podczas przekazywania nieprawidłowego `IUnknown` wskaźnika do kodu zarządzanego z kodu natywnego. `IUnknown`Nie można zwrócić sukcesu, gdy zapytanie dotyczące `IUnknown` interfejsu.  
  
## <a name="symptoms"></a>Objawy  

 Wystąpił nieoczekiwany błąd podczas organizowania wskaźnika interfejsu COM podczas organizowania argumentów.  
  
## <a name="cause"></a>Przyczyna  

 Niepoprawna `QueryInterface` Implementacja interfejsu com przeniesiona do środowiska CLR.  
  
## <a name="resolution"></a>Rozwiązanie  

 Popraw `QueryInterface` implementację.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 To zdarzenie MDA nie ma wpływu na środowisko CLR.  
  
## <a name="output"></a>Dane wyjściowe  

 Opis błędu.  
  
## <a name="configuration"></a>Konfigurowanie  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Organizowanie międzyoperacyjne](../interop/interop-marshaling.md)
