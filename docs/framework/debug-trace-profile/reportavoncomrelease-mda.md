---
title: reportAvOnComRelease MDA
description: Zapoznaj się z programem reportAvOnComRelease Managed Debug Assistant (MDA), który może być aktywowany z powodu naruszeń dostępu i uszkodzenia pamięci w programie .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
ms.openlocfilehash: c5047aa4005cdaa9ae6aabe8dcd7ee838ee13f58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267120"
---
# <a name="reportavoncomrelease-mda"></a>reportAvOnComRelease MDA

`reportAvOnComRelease`Asystent debugowania zarządzanego (MDA) jest uaktywniany, gdy wyjątki są zgłaszane z powodu błędów zliczania odwołań do użytkownika podczas wykonywania międzyoperacyjności modelu COM i używania <xref:System.Runtime.InteropServices.Marshal.Release%2A> metody lub w <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> połączeniu z nieprzetworzonymi wywołaniami com.  
  
## <a name="symptoms"></a>Objawy  

 Naruszenia dostępu i uszkodzenie pamięci.  
  
## <a name="cause"></a>Przyczyna  

 Czasami wyjątek jest zgłaszany z powodu błędów zliczania odwołań użytkownika podczas wykonywania międzyoperacyjności modelu COM i używania <xref:System.Runtime.InteropServices.Marshal.Release%2A> metody lub w <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> połączeniu z nieprzetworzonymi wywołaniami com. Zwykle ten wyjątek jest odrzucany, ponieważ nie spowoduje to naruszenia zasad dostępu w środowisku CLR. Po włączeniu tego asystenta takie wyjątki mogą być wykrywane i raportowane zamiast po prostu odrzucone.  
  
## <a name="resolution"></a>Rozwiązanie  

 Zbadaj kod zliczania odwołań i Wyszukaj błędy, a także Zbadaj natywnych klientów obiektu, aby uzyskać odwołania do błędów.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 Dostępne są dwa tryby. Jeśli `allowAv` atrybut ma wartość `true` , asystent uniemożliwia odrzucanie naruszenia zasad dostępu przez środowisko uruchomieniowe. Jeśli `allowAv` jest to `false` ustawienie domyślne, środowisko uruchomieniowe odrzuca naruszenie zasad dostępu, ale komunikat ostrzegawczy jest raportowany użytkownikowi, aby wskazać, że wyjątek został zgłoszony i odrzucony.  
  
## <a name="output"></a>Dane wyjściowe  

 Jeśli to możliwe, dane wyjściowe zawierają oryginalną tablicę sieciową wskaźnika interfejsu COM. W przeciwnym razie zostanie wyświetlony komunikat informacyjny.  
  
## <a name="configuration"></a>Konfigurowanie  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Organizowanie międzyoperacyjne](../interop/interop-marshaling.md)
