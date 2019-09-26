---
title: Wprowadzenie — gRPC dla deweloperów WCF
description: Wprowadzenie
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 2782f28e8a99fa7c0bde69f757d14e96e91f5cd4
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184422"
---
# <a name="introduction"></a><span data-ttu-id="74910-103">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="74910-103">Introduction</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="74910-104">Pomoc dla maszyn komunikujących się ze sobą jest jednym z podstawowych postanowień w wieku cyfrowym.</span><span class="sxs-lookup"><span data-stu-id="74910-104">Helping machines communicate with each other has been one of the primary preoccupations of the digital age.</span></span> <span data-ttu-id="74910-105">W szczególności istnieje ciągły nakład na określenie optymalnego mechanizmu komunikacji zdalnej, który będzie odpowiadał wymaganiom związanym z współdziałaniem bieżącej infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="74910-105">In particular, there is an ongoing effort to determine the optimal remote communication mechanism that will suit the interoperability demands of the current infrastructure.</span></span> <span data-ttu-id="74910-106">Jak można wyobrazić, ten mechanizm zmienia się w zależności od potrzeb lub infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="74910-106">As you can imagine, that mechanism changes as either the demands or the infrastructure evolves.</span></span>

<span data-ttu-id="74910-107">Wydanie programu .NET Core 3,0 oznacza zmianę sposobu, w jaki firma Microsoft dostarcza rozwiązania komunikacji zdalnej dla deweloperów, którzy chcą dostarczać usługi na różnych platformach.</span><span class="sxs-lookup"><span data-stu-id="74910-107">The release of .NET Core 3.0 marks a shift in the way that Microsoft delivers remote communication solutions to developers who want to deliver services across a range of platforms.</span></span> <span data-ttu-id="74910-108">Platforma .NET Core nie oferuje Windows Communication Foundation (WCF) z usługi Box, ale w wersji ASP.NET Core 3,0 zapewnia wbudowaną funkcję gRPC.</span><span class="sxs-lookup"><span data-stu-id="74910-108">.NET Core doesn't offer Windows Communication Foundation (WCF) out of the box but, with the release of version ASP.NET Core 3.0, it does provide built-in gRPC functionality.</span></span>

<span data-ttu-id="74910-109">gRPC to popularna platforma w szerszej społeczności oprogramowania, używana przez deweloperów w wielu językach programowania dla nowoczesnych scenariuszy RPC.</span><span class="sxs-lookup"><span data-stu-id="74910-109">gRPC is a popular framework in the wider software community, used by developers across many programming languages for modern RPC scenarios.</span></span> <span data-ttu-id="74910-110">Społeczność i ekosystem są żywe i aktywne, z obsługą protokołu gRPC dodawanego do składników infrastruktury, takich jak Kubernetes, siatki usług, moduły równoważenia obciążenia i nie tylko.</span><span class="sxs-lookup"><span data-stu-id="74910-110">The community and the ecosystem are vibrant and active, with support for the gRPC protocol being added to infrastructure components like Kubernetes, service meshes, load balancers and more.</span></span> <span data-ttu-id="74910-111">Te czynniki, a także jego wydajność, wydajność i zgodność między platformami, umożliwiają gRPC naturalny wybór dla nowych aplikacji i aplikacji WCF przenoszonych na platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="74910-111">These factors, as well as its performance, efficiency and cross-platform compatibility, make gRPC a natural choice for new apps and WCF apps moving to .NET Core.</span></span>

## <a name="history"></a><span data-ttu-id="74910-112">Historia</span><span class="sxs-lookup"><span data-stu-id="74910-112">History</span></span>

<span data-ttu-id="74910-113">Podstawowa zasada w sieci komputerowej nie większa niż grupa komputerów wymieniających dane ze sobą w celu osiągnięcia zestawu powiązanych zadań, które nie uległy zmianie od momentu jego powstania.</span><span class="sxs-lookup"><span data-stu-id="74910-113">The fundamental principle of a computer network as nothing more than a group of computers exchanging data with each other to achieve a set of interrelated tasks hasn't changed since its inception.</span></span> <span data-ttu-id="74910-114">Jednak stopień złożoności, skali i oczekiwania jest wykładniczy.</span><span class="sxs-lookup"><span data-stu-id="74910-114">However, the complexity, scale, and expectations have grown exponentially.</span></span>  

<span data-ttu-id="74910-115">W 1990s wyróżnienie dotyczyło głównie ulepszania sieci wewnętrznych przy użyciu tego samego języka i platform.</span><span class="sxs-lookup"><span data-stu-id="74910-115">During the 1990s, the emphasis had been mainly focused on improving internal networks using the same language and platforms.</span></span> <span data-ttu-id="74910-116">Protokół TCP/IP stał się standardem Gold dla tego typu komunikacji.</span><span class="sxs-lookup"><span data-stu-id="74910-116">TCP/IP became the gold standard for this type of communication.</span></span>

<span data-ttu-id="74910-117">Jednak fokus jest wkrótce przenoszony do optymalnej optymalizacji komunikacji na wielu platformach promującej podejście niezależny od języka.</span><span class="sxs-lookup"><span data-stu-id="74910-117">However, the focus soon shifted to how best to optimize communication across multiple platforms promoting a language agnostic approach.</span></span> <span data-ttu-id="74910-118">Architektura zorientowana na usługę (SOA) udostępnia strukturę swobodnego sprzęgania szerokiej kolekcji usług, które mogą być udostępniane aplikacji.</span><span class="sxs-lookup"><span data-stu-id="74910-118">Service-oriented architecture (SOA) provided a structure for loosely coupling a broad collection of services that could be provided to an application.</span></span>

<span data-ttu-id="74910-119">Opracowywanie *usług sieci Web* ma miejsce, gdy wszystkie główne platformy mogą uzyskać dostęp do Internetu, ale nadal nie mogą ze sobą współistnieć.</span><span class="sxs-lookup"><span data-stu-id="74910-119">The development of *Web Services* occurred once all major platforms could access the Internet, but they still couldn’t interact with each other.</span></span> <span data-ttu-id="74910-120">Usługi sieci Web mają otwarte standardy i protokoły, w tym:</span><span class="sxs-lookup"><span data-stu-id="74910-120">Web services have open standards and protocols including:</span></span>

- <span data-ttu-id="74910-121">XML do tagów i danych kodu;</span><span class="sxs-lookup"><span data-stu-id="74910-121">XML to tag and code data;</span></span>
- <span data-ttu-id="74910-122">Simple Object Access Protocol (SOAP) do transferowania danych;</span><span class="sxs-lookup"><span data-stu-id="74910-122">Simple Object Access Protocol (SOAP) to transfer data;</span></span>
- <span data-ttu-id="74910-123">Web Services Definition Language (WSDL) — opisuje i nawiązuje połączenie usługi sieci Web z aplikacją kliencką. *i*</span><span class="sxs-lookup"><span data-stu-id="74910-123">Web Services Definition Language (WSDL) – describes and connects the web service to the client application; *and*</span></span>
- <span data-ttu-id="74910-124">Integracja z odnajdywaniem uniwersalnym (UDDI) — umożliwia odnajdywanie usług sieci Web przy użyciu innych usług.</span><span class="sxs-lookup"><span data-stu-id="74910-124">Universal Description Discovery Integration (UDDI)- enables Web Services to be discoverable by other Services</span></span>

<span data-ttu-id="74910-125">Protokół SOAP definiuje reguły, za pomocą których elementy rozproszone aplikacji mogą komunikować się ze sobą, nawet jeśli znajdują się na różnych platformach.</span><span class="sxs-lookup"><span data-stu-id="74910-125">SOAP defines the rules by which distributed elements of an application can communicate with each other even if they are on different platforms.</span></span> <span data-ttu-id="74910-126">Protokół SOAP jest oparty na kodzie XML, więc jest czytelny dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="74910-126">SOAP is based on XML, so it's human-readable.</span></span> <span data-ttu-id="74910-127">W celu łatwego zrozumienia protokołu SOAP jest to rozmiar. Komunikaty protokołu SOAP są większe niż komunikaty w porównywalnych protokołach.</span><span class="sxs-lookup"><span data-stu-id="74910-127">The sacrifice for making SOAP easily understood is size; SOAP messages are larger than messages in comparable protocols.</span></span> <span data-ttu-id="74910-128">Protokół SOAP został zaprojektowany, aby podzielić aplikacje monolityczne na formularz wieloskładnikowy bez utraty zabezpieczeń lub kontroli.</span><span class="sxs-lookup"><span data-stu-id="74910-128">SOAP was designed to break down monolithic applications into multi-component form without losing security or control.</span></span> <span data-ttu-id="74910-129">W związku z tym program WCF został zaprojektowany do pracy z tym rodzajem systemu, w przeciwieństwie do gRPC, który rozpoczął się jako system rozproszony.</span><span class="sxs-lookup"><span data-stu-id="74910-129">Therefore, WCF was designed to work with that kind of system, unlike gRPC, which began as a distributed system.</span></span> <span data-ttu-id="74910-130">Usługa WCF dotyczyła niektórych z tych ograniczeń przez opracowywanie i dokumentowanie własnych protokołów rozszerzeń dla stosu protokołu SOAP, ale kosztem niewsparcia z innych platform.</span><span class="sxs-lookup"><span data-stu-id="74910-130">WCF addressed some of these limitations by developing and documenting proprietary extension protocols for the SOAP stack, but at the cost of lack of support from other platforms.</span></span>

<span data-ttu-id="74910-131">Windows Communication Foundation to struktura do kompilowania usług.</span><span class="sxs-lookup"><span data-stu-id="74910-131">Windows Communication Foundation is a framework for building services.</span></span> <span data-ttu-id="74910-132">Została zaprojektowana na wczesnych wersjach 2000, aby ułatwić deweloperom korzystanie z wczesnego SOA do zarządzania złożonością pracy z protokołem SOAP.</span><span class="sxs-lookup"><span data-stu-id="74910-132">It was designed in the early 2000s to help developers using early SOA to manage the complexities of working with SOAP.</span></span> <span data-ttu-id="74910-133">Mimo że eliminuje wymóg tworzenia własnych protokołów SOAP przez dewelopera, usługa WCF nadal używa protokołu SOAP do zapewnienia współdziałania z innymi systemami.</span><span class="sxs-lookup"><span data-stu-id="74910-133">Although it removes the requirement for the developer to write their own SOAP protocols, WCF still uses SOAP to enable interoperability with other systems.</span></span> <span data-ttu-id="74910-134">Program WCF został również zaprojektowany w celu dostarczania rozwiązań między wieloma protokołami (HTTP/1.1, NetTCP itd.).</span><span class="sxs-lookup"><span data-stu-id="74910-134">WCF was also designed to deliver solutions across multiple protocols (HTTP/1.1, NetTCP, and so on).</span></span>

## <a name="microservices"></a><span data-ttu-id="74910-135">Mikrousługi</span><span class="sxs-lookup"><span data-stu-id="74910-135">Microservices</span></span>

<span data-ttu-id="74910-136">W przypadku architektur mikrousług duże aplikacje są kompilowane jako kolekcja mniejszych usług modułowych.</span><span class="sxs-lookup"><span data-stu-id="74910-136">In microservice architectures, large applications are built as a collection of smaller modular services.</span></span> <span data-ttu-id="74910-137">Każdy składnik wykonuje określone zadanie lub proces, a składniki są przeznaczone do pracy, ale mogą być odizolowane w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="74910-137">Each component does a specific task or process, and components are designed to work interoperably but can be isolated as necessary.</span></span>

<span data-ttu-id="74910-138">Zalety mikrousług obejmują:</span><span class="sxs-lookup"><span data-stu-id="74910-138">Advantages to microservices include:</span></span>

- <span data-ttu-id="74910-139">Zmiany i uaktualnienia mogą być obsługiwane niezależnie.</span><span class="sxs-lookup"><span data-stu-id="74910-139">Changes and upgrades can be handled independently.</span></span>
- <span data-ttu-id="74910-140">Obsługa błędów stanie się bardziej wydajna, ponieważ problemy mogą być śledzone dla konkretnych usług, które są następnie odizolowane, odtworzone, przetestowane i ponownie wdrożone niezależnie od innych usług.</span><span class="sxs-lookup"><span data-stu-id="74910-140">Error handling becomes more efficient as problems can be traced to specific services that are then isolated, rebuilt, tested, and redeployed independent of the other services.</span></span>
- <span data-ttu-id="74910-141">Skalowalność może być ograniczona do określonych wystąpień lub usług, a nie całej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="74910-141">Scalability can be confined to the specific instances or services rather than the whole application.</span></span>
- <span data-ttu-id="74910-142">Programowanie może odbywać się w wielu zespołach, z mniejszą ilością problemów, gdy wiele zespołów pracuje w pojedynczej bazie kodu.</span><span class="sxs-lookup"><span data-stu-id="74910-142">Development can happen across multiple teams, with less friction than occurs when many teams work on a single codebase.</span></span>

<span data-ttu-id="74910-143">Przejście do coraz większej wirtualizacji, przetwarzania danych w chmurze, kontenerów i Internet rzeczyów przyczyniło się do ciągłego wzrostu mikrousług.</span><span class="sxs-lookup"><span data-stu-id="74910-143">The move towards increasing virtualization, cloud computing, containers and the Internet of Things have contributed to the ongoing rise of microservices.</span></span> <span data-ttu-id="74910-144">Jednak mikrousługi nie mają żadnych wyzwań.</span><span class="sxs-lookup"><span data-stu-id="74910-144">However, microservices aren't without their challenges.</span></span> <span data-ttu-id="74910-145">W przypadku infrastruktury pofragmentowanej/zdecentralizowanej coraz częściej zachodzi potrzeba uproszczenia i przyspieszenia komunikacji między usługami.</span><span class="sxs-lookup"><span data-stu-id="74910-145">The fragmented/decentralized infrastructure placed more emphasis on the need for simplicity and speed when communicating between services.</span></span> <span data-ttu-id="74910-146">To z kolei nastąpiło zwrócenie uwagi do czasami pracochłonne i nieskażony charakter protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="74910-146">This in turn drew attention to the sometimes laborious and contorted nature of SOAP.</span></span>

<span data-ttu-id="74910-147">Była w tym środowisku, że gRPC został uruchomiony, 10 lat po pierwszym wydaniu WCF przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74910-147">It was into this environment that gRPC was launched, 10 years after Microsoft first released WCF.</span></span> <span data-ttu-id="74910-148">W przypadku rozwijającego się bezpośrednio z usługi RPC infrastruktury wewnętrznej firmy Google (stubby), gRPC nigdy nie opierał się na tych samych standardach i protokołach, które powiadomiły parametry wielu wcześniejszych wywołań RPC.</span><span class="sxs-lookup"><span data-stu-id="74910-148">Evolved directly from Google’s internal infrastructure RPC (Stubby), gRPC was never based on the same standards and protocols that had informed the parameters of many earlier RPCs.</span></span> <span data-ttu-id="74910-149">Ponadto gRPC była kiedykolwiek oparta na protokole HTTP/2 i dlatego może nastąpić w przypadku nowych funkcji oferowanych przez zaawansowany protokół transportowy.</span><span class="sxs-lookup"><span data-stu-id="74910-149">Additionally, gRPC was only ever based on HTTP/2 and that's why it could draw on the new capabilities that advanced transport protocol provided.</span></span> <span data-ttu-id="74910-150">W szczególności dwukierunkowe przesyłanie strumieniowe, obsługa komunikatów binarnych i multipleksowanie.</span><span class="sxs-lookup"><span data-stu-id="74910-150">In particular, bidirectional streaming, binary messaging, and multiplexing.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="74910-151">Informacje o tym przewodniku</span><span class="sxs-lookup"><span data-stu-id="74910-151">About this guide</span></span>

<span data-ttu-id="74910-152">Ten przewodnik obejmuje najważniejsze funkcje gRPC.</span><span class="sxs-lookup"><span data-stu-id="74910-152">This guide covers the key features of gRPC.</span></span> <span data-ttu-id="74910-153">Wczesne rozdziały mają ogólny wygląd głównych funkcji programu WCF i porównaj je z gRPC.</span><span class="sxs-lookup"><span data-stu-id="74910-153">The early chapters take a high-level look at the main features of WCF and compare them to gRPC.</span></span> <span data-ttu-id="74910-154">Określa, gdzie są bezpośrednie korelacje między WCF i gRPC, a także miejsce, w którym gRPC oferuje zalety.</span><span class="sxs-lookup"><span data-stu-id="74910-154">It identifies where the are direct correlations between WCF and gRPC and also where gRPC offers an advantage.</span></span> <span data-ttu-id="74910-155">W przypadku braku korelacji między usługą WCF i gRPC lub gRPC nie jest możliwe zaoferowanie równoważnego rozwiązania WCF, w tym przewodniku opisano obejścia lub miejsca, w których można znaleźć więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="74910-155">Where there's no correlation between WCF and gRPC or where gRPC isn't able to offer an equivalent solution to WCF, this guide will suggest workarounds or places to go for further information.</span></span>

<span data-ttu-id="74910-156">Korzystając z zestawu przykładowych aplikacji WCF, rozdział 5 to głębokie szczegółowee wyszukiwanie w celu przeprowadzenia konwersji głównych typów usług WCF (prosta odpowiedź na żądanie, jednokierunkowe i przesyłania strumieniowego) do ich odpowiedników w gRPC.</span><span class="sxs-lookup"><span data-stu-id="74910-156">Using a set of sample WCF applications, Chapter 5 is a deep dive look at a converting the main types of WCF service (simple request-reply, one-way, and streaming) to their equivalents in gRPC.</span></span>

<span data-ttu-id="74910-157">W ostatniej sekcji książki zawarto informacje na temat najlepszego gRPC w pracy, w tym przy użyciu dodatkowych narzędzi, takich jak kontenery Docker lub Kubernetes, aby wykorzystać wydajność usługi gRPC oraz szczegółowy opis monitorowania z rejestrowaniem, metrykami i dystrybuowaniem pochodzenia.</span><span class="sxs-lookup"><span data-stu-id="74910-157">The final section of the book looks at how to get the best from gRPC in practice, including using additional tools like Docker containers or Kubernetes to leverage to the efficiency of gRPC, and a detailed look at the monitoring with logging, metrics, and distributed tracing.</span></span>

## <a name="whom-this-guide-is-for"></a><span data-ttu-id="74910-158">Którego dotyczy ten przewodnik</span><span class="sxs-lookup"><span data-stu-id="74910-158">Whom this guide is for</span></span>

<span data-ttu-id="74910-159">Ten przewodnik został utworzony dla deweloperów pracujących w .NET Framework lub .NET Core, którzy wcześniej korzystali z usług WCF i chcący migrować swoje aplikacje do nowoczesnego środowiska RPC dla programu .NET Core 3,0 i jego nowszych wersji.</span><span class="sxs-lookup"><span data-stu-id="74910-159">This guide was written for developers working in .NET Framework or .NET Core who have previously used WCF and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="74910-160">Przewodnik może być również bardziej używany w przypadku deweloperów uaktualniających lub rozważających uaktualnienie do programu .NET Core 3,0, którzy chcą korzystać z wbudowanych narzędzi gRPC.</span><span class="sxs-lookup"><span data-stu-id="74910-160">The guide may also be of use more generally for developers upgrading or considering upgrading to .NET Core 3.0 who want to use the built-in gRPC tools.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="74910-161">[Poprzedni](index.md)
>[Następny](grpc-overview.md)</span><span class="sxs-lookup"><span data-stu-id="74910-161">[Previous](index.md)
[Next](grpc-overview.md)</span></span>