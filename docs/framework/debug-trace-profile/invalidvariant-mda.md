---
title: invalidVariant MDA
description: Zapoznaj się z asystentem zarządzanego debugowania invalidVariant, który jest wywoływany, jeśli wystąpił nieprawidłowy wariant w wywołaniu z natywnego/niezarządzanego kodu zarządzanego.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: f0667a54e950ead27000eb6b93ebd547dea1cfb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281303"
---
# <a name="invalidvariant-mda"></a>invalidVariant MDA

`invalidVariant`Asystent debugowania zarządzanego (MDA) jest uaktywniany po napotkaniu nieprawidłowej `VARIANT` struktury podczas wywołania z kodu natywnego lub niezarządzanego do kodu zarządzanego.  
  
## <a name="symptoms"></a>Objawy  

 Nieoczekiwane zachowanie podczas przejścia między kodem natywnym i zarządzanym obejmującym kierowanie `VARIANT` do obiektu.  
  
## <a name="cause"></a>Przyczyna  

 Kod natywny przekazuje nieprawidłowo sformułowaną `VARIANT` strukturę do kodu zarządzanego.  Środowisko uruchomieniowe próbuje zorganizować ten `VARIANT` obiekt w celu aktywowania go, jeśli element `VARIANT` jest nieprawidłowy. Przykłady nieprawidłowych wartości `VARIANT` S `VARIANT` obejmują `VARTYPE` VT_EMPTY &#124; VT_BYREF lub `VARIANT` `VARTYPE` VT_VARIANT.  
  
## <a name="resolution"></a>Rozwiązanie  

 Kod natywny lub niezarządzany przekazujący `VARIANT` musi mieć pewność, że `VARIANT` jest poprawnie sformułowany i zainicjowany.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 Zdarzenie MDA nie ma wpływu na zachowanie środowiska uruchomieniowego.  
  
## <a name="output"></a>Dane wyjściowe  

 Komunikat MDA wskazujący, że środowisko uruchomieniowe wykryło nieprawidłowe `VARIANT` przekazanie do zarządzanego kodu przez moduł niezarządzany.  
  
## <a name="configuration"></a>Konfigurowanie  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Organizowanie międzyoperacyjne](../interop/interop-marshaling.md)
