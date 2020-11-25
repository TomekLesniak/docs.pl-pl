---
title: Otoki COM
description: Klienci modelu COM i obiekty .NET współdziałają z użyciem otoki, która umożliwia wywoływanie modelu COM i otokę umożliwiającą wywoływanie Środowisko CLR tworzy otoki automatycznie.
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
ms.openlocfilehash: 17a303cde5fa51cd940b0375d2c6657fcd354dc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706335"
---
# <a name="com-wrappers"></a><span data-ttu-id="1b109-104">Otoki COM</span><span class="sxs-lookup"><span data-stu-id="1b109-104">COM Wrappers</span></span>

<span data-ttu-id="1b109-105">COM różni się od modelu obiektów środowiska uruchomieniowego .NET na kilka ważnych sposobów:</span><span class="sxs-lookup"><span data-stu-id="1b109-105">COM differs from the .NET runtime object model in several important ways:</span></span>  
  
- <span data-ttu-id="1b109-106">Klienci obiektów COM muszą zarządzać okresem istnienia tych obiektów; środowisko uruchomieniowe języka wspólnego zarządza okresem istnienia obiektów w jego środowisku.</span><span class="sxs-lookup"><span data-stu-id="1b109-106">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
- <span data-ttu-id="1b109-107">Klienci obiektów COM wykrywają, czy usługa jest dostępna przez żądanie interfejsu, który zapewnia tę usługę, i przywracający wskaźnik interfejsu, czy nie.</span><span class="sxs-lookup"><span data-stu-id="1b109-107">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="1b109-108">Klienci obiektów .NET mogą uzyskać opis funkcji obiektu przy użyciu odbicia.</span><span class="sxs-lookup"><span data-stu-id="1b109-108">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
- <span data-ttu-id="1b109-109">Obiekty sieciowe znajdują się w pamięci zarządzanej przez środowisko wykonawcze środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="1b109-109">NET objects reside in memory managed by the .NET runtime execution environment.</span></span> <span data-ttu-id="1b109-110">Środowisko wykonawcze może przenosić obiekty w pamięci ze względu na wydajność i aktualizować wszystkie odwołania do obiektów, które są przez niego przenoszone.</span><span class="sxs-lookup"><span data-stu-id="1b109-110">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="1b109-111">Niezarządzani Klienci, którzy uzyskali wskaźnik do obiektu, zależą od obiektu, aby pozostawał w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1b109-111">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="1b109-112">Ci klienci nie mają mechanizmu do zajmowania się obiektem, którego lokalizacja nie jest stała.</span><span class="sxs-lookup"><span data-stu-id="1b109-112">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="1b109-113">Aby przezwyciężyć te różnice, środowisko uruchomieniowe zapewnia klasy otoki, aby zarówno klienci zarządzani, jak i niezarządzani, uważali, że wywołujeją obiekty w ramach danego środowiska.</span><span class="sxs-lookup"><span data-stu-id="1b109-113">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="1b109-114">Za każdym razem, gdy zarządzany klient wywołuje metodę dla obiektu COM, środowisko uruchomieniowe tworzy niewywołującą otokę (otoka [środowiska uruchomieniowego](runtime-callable-wrapper.md) ).</span><span class="sxs-lookup"><span data-stu-id="1b109-114">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="1b109-115">RCW abstrakcyjne różnice między zarządzanymi i niezarządzanymi mechanizmami odniesienia, między innymi.</span><span class="sxs-lookup"><span data-stu-id="1b109-115">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="1b109-116">Środowisko uruchomieniowe powoduje także utworzenie [otoki](com-callable-wrapper.md) wywołującej com (CCW) w celu odwrócenia procesu, co umożliwia KLIENTowi com bezproblemową wywoływanie metody dla obiektu .NET.</span><span class="sxs-lookup"><span data-stu-id="1b109-116">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="1b109-117">Jak widać na poniższej ilustracji, perspektywa kodu wywołującego określa klasę otoki, którą tworzy środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="1b109-117">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 ![Omówienie otoki COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 <span data-ttu-id="1b109-119">W większości przypadków standardowa OTOKa lub CCW wygenerowane przez środowisko uruchomieniowe zapewniają odpowiednie kierowanie dla wywołań, które przecinają granicę między modelem COM a środowiskiem uruchomieniowym platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="1b109-119">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET runtime.</span></span> <span data-ttu-id="1b109-120">Przy użyciu atrybutów niestandardowych można opcjonalnie dostosować sposób, w jaki środowisko uruchomieniowe reprezentuje kod zarządzany i niezarządzany.</span><span class="sxs-lookup"><span data-stu-id="1b109-120">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b109-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1b109-121">See also</span></span>

- <span data-ttu-id="1b109-122">[Zaawansowane współdziałanie COM w .NET Framework](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1b109-122">[Advanced COM Interoperability in .NET Framework](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="1b109-123">Wywoływana otoka środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="1b109-123">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
- [<span data-ttu-id="1b109-124">Wywoływana otoka COM</span><span class="sxs-lookup"><span data-stu-id="1b109-124">COM Callable Wrapper</span></span>](com-callable-wrapper.md)
- <span data-ttu-id="1b109-125">[Dostosowywanie otok standardowych w .NET Framework](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1b109-125">[Customizing Standard Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span></span>
- <span data-ttu-id="1b109-126">[Instrukcje: Dostosowywanie wywoływanych otok środowiska uruchomieniowego w .NET Framework](/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1b109-126">[How to: Customize Runtime Callable Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span></span>
