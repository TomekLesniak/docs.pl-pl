---
title: przekazywanie międzyprocesowe (marshaling) MDA
description: Przejrzyj zarządzany Asystent debugowania (MDA), który jest wywoływany, jeśli środowisko CLR skonfiguruje informacje kierujące dla parametru metody lub pola struktury.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: afe54a2104e05f8fad57c7cbba4988b013aff761
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271177"
---
# <a name="marshaling-mda"></a>przekazywanie międzyprocesowe (marshaling) MDA

`marshaling`Asystent debugowania zarządzanego (MDA) jest uaktywniany, gdy środowisko CLR konfiguruje informacje kierujące dla parametru metody lub pola struktury. To zdarzenie MDA nie działa w przypadku zestawów skompilowanych w trybie JIT.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 To zdarzenie MDA nie ma wpływu na środowisko CLR.  
  
## <a name="output"></a>Dane wyjściowe  

 MDA Wyświetla typ parametru lub pola w kontekstach zarządzanych i niezarządzanych, a także strukturę lub metodę zawierającą typ.  Poniżej znajduje się przykład danych wyjściowych dla pola:  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a>Konfigurowanie  

 Konfiguracja MDA umożliwia filtrowanie raportowanych informacji o kierowaniu na podstawie nazw pól lub metod.  W poniższym przykładzie pokazano użycie `methodFilter` , `fieldFilter` , i `match` elementów do określenia filtrów.  Ustawienie `name` atrybutu na gwiazdkę ( \* ) będzie pasować do wszystkiego.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Organizowanie międzyoperacyjne](../interop/interop-marshaling.md)
