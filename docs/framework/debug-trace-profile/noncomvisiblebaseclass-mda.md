---
title: nonComVisibleBaseClass MDA
description: Zobacz Asystent debugowania zarządzanego nonComVisibleBaseClass (MDA), który jest wywoływany w wywołaniach QueryInterface z kodu natywnego z niepowodzeniem z COR_E_INVALIDOPERATION.
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: c13d05d04c75d6b4f1be4a5f338fd7246fed8db4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254574"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="5386e-103">nonComVisibleBaseClass MDA</span><span class="sxs-lookup"><span data-stu-id="5386e-103">nonComVisibleBaseClass MDA</span></span>

<span data-ttu-id="5386e-104">`nonComVisibleBaseClass`Asystent debugowania zarządzanego (MDA) jest uaktywniany, gdy `QueryInterface` wywołanie jest wykonywane przez kod natywny lub niezarządzany w przypadku niezarządzanej otoki COM (CCW) klasy zarządzanej com, która dziedziczy z klasy podstawowej, która nie jest widoczna dla modelu com.</span><span class="sxs-lookup"><span data-stu-id="5386e-104">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="5386e-105">`QueryInterface`Wywołanie powoduje aktywację elementu MDA tylko w przypadkach, gdy wywołania żądają interfejsu klasy lub domyślnej `IDispatch` klasy zarządzanej przez com.</span><span class="sxs-lookup"><span data-stu-id="5386e-105">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="5386e-106">Zdarzenie MDA nie jest uaktywniane, gdy `QueryInterface` jest przeznaczony dla jawnego interfejsu, który ma <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atrybut zastosowany i jest jawnie zaimplementowany przez klasę widoczną dla modelu com.</span><span class="sxs-lookup"><span data-stu-id="5386e-106">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5386e-107">Objawy</span><span class="sxs-lookup"><span data-stu-id="5386e-107">Symptoms</span></span>  

 <span data-ttu-id="5386e-108">`QueryInterface`Wykonano wywołanie z kodu natywnego, który kończy się niepowodzeniem z COR_E_INVALIDOPERATION HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5386e-108">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="5386e-109">WYNIK HRESULT może być spowodowany tym, że środowisko uruchomieniowe nie zezwoli na `QueryInterface` wywołania, które mogłyby spowodować aktywację tego elementu MDA.</span><span class="sxs-lookup"><span data-stu-id="5386e-109">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5386e-110">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="5386e-110">Cause</span></span>  

 <span data-ttu-id="5386e-111">Środowisko uruchomieniowe nie może zezwolić na `QueryInterface` wywołania interfejsu klasy lub domyślnego `IDispatch` interfejsu klasy widocznej dla modelu COM, która dziedziczy z klasy, która nie jest widoczna dla modelu COM ze względu na potencjalne problemy z wersjami.</span><span class="sxs-lookup"><span data-stu-id="5386e-111">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="5386e-112">Na przykład, jeśli jakikolwiek publiczny element członkowski został dodany do klasy podstawowej, która nie jest widoczna dla modelu COM, istniejący klienci COM korzystający z klasy pochodnej mogą potencjalnie przerwać, ponieważ tablice metod pochodnych klasy pochodnej, która zawiera składowe klasy bazowej, zostałyby zmienione przez taką zmianę.</span><span class="sxs-lookup"><span data-stu-id="5386e-112">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="5386e-113">Jawne interfejsy uwidocznione dla modelu COM nie mają tego problemu, ponieważ nie obejmują podstawowych elementów członkowskich interfejsów w tablicy bazowej.</span><span class="sxs-lookup"><span data-stu-id="5386e-113">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5386e-114">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="5386e-114">Resolution</span></span>  

 <span data-ttu-id="5386e-115">Nie ujawniaj interfejsu klasy.</span><span class="sxs-lookup"><span data-stu-id="5386e-115">Do not expose the class interface.</span></span> <span data-ttu-id="5386e-116">Zdefiniuj jawny interfejs i Zastosuj <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> do niego atrybut.</span><span class="sxs-lookup"><span data-stu-id="5386e-116">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5386e-117">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="5386e-117">Effect on the Runtime</span></span>  

 <span data-ttu-id="5386e-118">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="5386e-118">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5386e-119">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="5386e-119">Output</span></span>  

 <span data-ttu-id="5386e-120">Poniżej znajduje się przykładowy komunikat dla `QueryInterface` wywołania klasy widocznej dla modelu COM `Derived` , która dziedziczy z klasy niewidocznej dla modelu COM `Base` .</span><span class="sxs-lookup"><span data-stu-id="5386e-120">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```output
A QueryInterface call was made requesting the class interface of COM
visible managed class 'Derived'. However since this class derives from
non COM visible class 'Base', the QueryInterface call will fail. This
is done to prevent the non COM visible base class from being
constrained by the COM versioning rules.
```  
  
## <a name="configuration"></a><span data-ttu-id="5386e-121">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="5386e-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5386e-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5386e-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5386e-123">Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="5386e-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5386e-124">Organizowanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="5386e-124">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
