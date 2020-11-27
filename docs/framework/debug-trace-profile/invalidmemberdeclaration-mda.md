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
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="ab8d1-103">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="ab8d1-103">invalidMemberDeclaration MDA</span></span>

<span data-ttu-id="ab8d1-104">`invalidMemberDeclaration`Asystent debugowania zarządzanego (MDA) został aktywowany, aby zgłosić błąd, który występuje podczas określania sposobu organizowania parametrów elementu członkowskiego, który ma być wywoływany z modelu com.</span><span class="sxs-lookup"><span data-stu-id="ab8d1-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ab8d1-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="ab8d1-105">Symptoms</span></span>  

 <span data-ttu-id="ab8d1-106">Błąd HRESULT jest zwracany do modelu COM bez wywołania metody zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="ab8d1-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ab8d1-107">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="ab8d1-107">Cause</span></span>  

 <span data-ttu-id="ab8d1-108">Najprawdopodobniej ze względu na niezgodny <xref:System.Runtime.InteropServices.MarshalAsAttribute> atrybut na jednym z parametrów.</span><span class="sxs-lookup"><span data-stu-id="ab8d1-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ab8d1-109">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="ab8d1-109">Resolution</span></span>  

 <span data-ttu-id="ab8d1-110">Określ prawidłowe <xref:System.Runtime.InteropServices.MarshalAsAttribute> atrybuty dla parametrów.</span><span class="sxs-lookup"><span data-stu-id="ab8d1-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ab8d1-111">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ab8d1-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="ab8d1-112">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="ab8d1-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ab8d1-113">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="ab8d1-113">Output</span></span>  

 <span data-ttu-id="ab8d1-114">Komunikat informacyjny zawierający nazwę elementu członkowskiego, nazwę typu i komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ab8d1-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ab8d1-115">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="ab8d1-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab8d1-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ab8d1-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ab8d1-117">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="ab8d1-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ab8d1-118">Organizowanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="ab8d1-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
