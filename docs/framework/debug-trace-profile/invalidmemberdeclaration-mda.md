---
title: invalidMemberDeclaration MDA
description: Zapoznaj się z asystentem debugowania zarządzanego przez invalidMemberDeclaration, który jest wywoływany w przypadku zwrócenia błędu HRESULT do modelu COM bez wywoływania metody zarządzanej.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: c8d6c69fc6eb4f5f690b02809fdc492da675c3b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272556"
---
# <a name="invalidmemberdeclaration-mda"></a>invalidMemberDeclaration MDA

`invalidMemberDeclaration`Asystent debugowania zarządzanego (MDA) został aktywowany, aby zgłosić błąd, który występuje podczas określania sposobu organizowania parametrów elementu członkowskiego, który ma być wywoływany z modelu com.  
  
## <a name="symptoms"></a>Objawy  

 Błąd HRESULT jest zwracany do modelu COM bez wywołania metody zarządzanej.  
  
## <a name="cause"></a>Przyczyna  

 Najprawdopodobniej ze względu na niezgodny <xref:System.Runtime.InteropServices.MarshalAsAttribute> atrybut na jednym z parametrów.  
  
## <a name="resolution"></a>Rozwiązanie  

 Określ prawidłowe <xref:System.Runtime.InteropServices.MarshalAsAttribute> atrybuty dla parametrów.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 To zdarzenie MDA nie ma wpływu na środowisko CLR.  
  
## <a name="output"></a>Dane wyjściowe  

 Komunikat informacyjny zawierający nazwę elementu członkowskiego, nazwę typu i komunikat o błędzie.  
  
## <a name="configuration"></a>Konfigurowanie  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Organizowanie międzyoperacyjne](../interop/interop-marshaling.md)
