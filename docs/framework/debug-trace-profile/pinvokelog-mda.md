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
# <a name="pinvokelog-mda"></a><span data-ttu-id="ccd35-103">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="ccd35-103">pInvokeLog MDA</span></span>

<span data-ttu-id="ccd35-104">`pInvokeLog`Asystent debugowania zarządzanego (MDA) jest uaktywniany dla każdego unikatowego podpisu wywołania platformy używanego podczas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ccd35-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ccd35-105">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ccd35-105">Effect on the Runtime</span></span>  

 <span data-ttu-id="ccd35-106">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="ccd35-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ccd35-107">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="ccd35-107">Output</span></span>  

 <span data-ttu-id="ccd35-108">Komunikat wskazujący podpis wywołania platformy używany podczas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ccd35-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ccd35-109">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="ccd35-109">Configuration</span></span>  

 <span data-ttu-id="ccd35-110">Każdy element dopasowania filtruje pliki. dll, do których są tworzone wywołania wywołania platformy.</span><span class="sxs-lookup"><span data-stu-id="ccd35-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ccd35-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ccd35-111">See also</span></span>

- [<span data-ttu-id="ccd35-112">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="ccd35-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ccd35-113">Wykorzystywanie niezarządzanych funkcji DLL</span><span class="sxs-lookup"><span data-stu-id="ccd35-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
