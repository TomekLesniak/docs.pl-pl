---
title: pInvokeLog MDA
description: Informacje o programie pInvokeLog Managed Debug Assistant (MDA), który jest uaktywniany dla każdego unikatowego podpisu wywołania platformy używanego podczas wykonywania w programie .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: b8cb4805663a2b28a133f98503730199af695c4f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271463"
---
# <a name="pinvokelog-mda"></a>pInvokeLog MDA

`pInvokeLog`Asystent debugowania zarządzanego (MDA) jest uaktywniany dla każdego unikatowego podpisu wywołania platformy używanego podczas wykonywania.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  

 To zdarzenie MDA nie ma wpływu na środowisko CLR.  
  
## <a name="output"></a>Dane wyjściowe  

 Komunikat wskazujący podpis wywołania platformy używany podczas wykonywania.  
  
## <a name="configuration"></a>Konfigurowanie  

 Każdy element dopasowania filtruje pliki. dll, do których są tworzone wywołania wywołania platformy.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](diagnosing-errors-with-managed-debugging-assistants.md)
- [Wykorzystywanie niezarządzanych funkcji DLL](../interop/consuming-unmanaged-dll-functions.md)
