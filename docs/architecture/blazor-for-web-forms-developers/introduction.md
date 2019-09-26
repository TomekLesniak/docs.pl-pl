---
title: Wprowadzenie do Blazor dla deweloperów formularzy sieci Web ASP.NET
description: Wprowadzenie do Blazor i pisania aplikacji sieci Web na całym stosie przy użyciu platformy .NET
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 922e72514f0283b66de971d679fab0af436f1c75
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183848"
---
# <a name="an-introduction-to-blazor-for-aspnet-web-forms-developers"></a><span data-ttu-id="1d986-103">Wprowadzenie do Blazor dla deweloperów formularzy sieci Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1d986-103">An introduction to Blazor for ASP.NET Web Forms developers</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1d986-104">ASP.NET Web Forms Framework to zszywanie programu .NET Web Development od momentu .NET Framework pierwszego wysłania w 2002.</span><span class="sxs-lookup"><span data-stu-id="1d986-104">The ASP.NET Web Forms framework has been a staple of .NET web development since the .NET Framework first shipped in 2002.</span></span> <span data-ttu-id="1d986-105">Z powrotem, gdy sieć Web była w znacznym stopniu nieprogramistyczna, ASP.NET Web Forms tworzy aplikacje sieci Web w prosty i wydajny sposób, wdrażając wiele wzorców, które były używane do tworzenia aplikacji klasycznych.</span><span class="sxs-lookup"><span data-stu-id="1d986-105">Back when the Web was still largely in its infancy, ASP.NET Web Forms made building web apps simple and productive by adopting many of the patterns that were used for desktop development.</span></span> <span data-ttu-id="1d986-106">W formularzach sieci Web ASP.NET strony sieci Web mogą szybko składać się z kontrolek interfejsu użytkownika wielokrotnego użytku.</span><span class="sxs-lookup"><span data-stu-id="1d986-106">In ASP.NET Web Forms, web pages can be quickly composed from reusable UI controls.</span></span> <span data-ttu-id="1d986-107">Interakcje użytkowników są obsługiwane naturalnie jako zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="1d986-107">User interactions are handled naturally as events.</span></span> <span data-ttu-id="1d986-108">Istnieje bogaty ekosystem formantów interfejsu użytkownika formularzy sieci Web udostępnianych przez firmę Microsoft i dostawców kontroli.</span><span class="sxs-lookup"><span data-stu-id="1d986-108">There's a rich ecosystem of Web Forms UI controls provided by Microsoft and control vendors.</span></span> <span data-ttu-id="1d986-109">Kontrolki ułatwiają podejmowanie połączeń ze źródłami danych i wyświetlanie bogatych wizualizacji danych.</span><span class="sxs-lookup"><span data-stu-id="1d986-109">The controls ease the efforts of connecting to data sources and displaying rich data visualizations.</span></span> <span data-ttu-id="1d986-110">Dla wizualizacji, Projektant formularzy sieci Web udostępnia prosty interfejs przeciągania i upuszczania służący do zarządzania kontrolkami.</span><span class="sxs-lookup"><span data-stu-id="1d986-110">For the visually inclined, the Web Forms designer provides a simple drag-and-drop interface for managing controls.</span></span>

<span data-ttu-id="1d986-111">W ciągu lat firma Microsoft wprowadziła nowe platformy sieci Web opartych na ASP.NET w celu rozwiązania trendów związanych z programowaniem aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1d986-111">Over the years, Microsoft has introduced new ASP.NET-based web frameworks to address web development trends.</span></span> <span data-ttu-id="1d986-112">Niektóre takie struktury sieci Web obejmują ASP.NET MVC, ASP.NET strony sieci Web i ostatnio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d986-112">Some such web frameworks include ASP.NET MVC, ASP.NET Web Pages, and more recently ASP.NET Core.</span></span> <span data-ttu-id="1d986-113">W przypadku każdej nowej struktury niektóre z nich przewidziały bezpośrednie odrzucanie formularzy sieci Web ASP.NET i criticized je jako przestarzałe, nieaktualne platformy sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1d986-113">With each new framework, some have predicted the imminent decline of ASP.NET Web Forms and criticized it as an outdated, outmoded web framework.</span></span> <span data-ttu-id="1d986-114">Pomimo tych prognoz wiele deweloperów sieci Web platformy .NET kontynuuje wyszukiwanie ASP.NET Web Forms prostych, stabilnych i wydajnych metod wykonywania zadań.</span><span class="sxs-lookup"><span data-stu-id="1d986-114">Despite these predictions, many .NET web developers continue to find ASP.NET Web Forms a simple, stable, and productive way to get their work done.</span></span>

<span data-ttu-id="1d986-115">W momencie pisania niemal połowa milionów deweloperów sieci Web używa ASP.NET formularzy sieci Web co miesiąc.</span><span class="sxs-lookup"><span data-stu-id="1d986-115">At the time of writing, almost half a million web developers use ASP.NET Web Forms every month.</span></span> <span data-ttu-id="1d986-116">Struktura formularzy sieci Web ASP.NET jest stabilna w przypadku, gdy dokumenty, przykłady, książki i wpisy w blogu z dekady temu pozostaną przydatne i istotne.</span><span class="sxs-lookup"><span data-stu-id="1d986-116">The ASP.NET Web Forms framework is stable to the point that docs, samples, books, and blog posts from a decade ago remain useful and relevant.</span></span> <span data-ttu-id="1d986-117">W przypadku wielu deweloperów sieci Web platformy .NET "ASP.NET" jest nadal synonimem "ASP.NET Web Forms", tak jak podczas pierwszego opracowywania programu .NET.</span><span class="sxs-lookup"><span data-stu-id="1d986-117">For many .NET web developers, "ASP.NET" is still synonymous with "ASP.NET Web Forms" as it was when .NET was first conceived.</span></span> <span data-ttu-id="1d986-118">Argumenty dotyczące informatyków i wad formularzy sieci Web ASP.NET w porównaniu z innymi nowymi platformami sieci Web platformy .NET mogą próg.</span><span class="sxs-lookup"><span data-stu-id="1d986-118">Arguments on the pros and cons of ASP.NET Web Forms compared to the other new .NET web frameworks may rage on.</span></span> <span data-ttu-id="1d986-119">Formularze sieci Web ASP.NET są popularnym środowiskiem do tworzenia aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1d986-119">ASP.NET Web Forms remains a popular framework for creating web apps.</span></span>

<span data-ttu-id="1d986-120">Nawet innowacje w programowaniu oprogramowania nie spowalniają pracy.</span><span class="sxs-lookup"><span data-stu-id="1d986-120">Even so, innovations in software development aren't slowing.</span></span> <span data-ttu-id="1d986-121">Wszyscy deweloperzy oprogramowania muszą korzystać z nowych technologii i trendów.</span><span class="sxs-lookup"><span data-stu-id="1d986-121">All software developers need to stay abreast of new technologies and trends.</span></span> <span data-ttu-id="1d986-122">Rozważane są dwa trendy w szczególności:</span><span class="sxs-lookup"><span data-stu-id="1d986-122">Two trends in particular are worth considering:</span></span> 

1. <span data-ttu-id="1d986-123">Zmiana na typ Open Source i Międzyplatformowy</span><span class="sxs-lookup"><span data-stu-id="1d986-123">The shift to open-source and cross-platform</span></span>
2. <span data-ttu-id="1d986-124">Zmiana logiki aplikacji na klienta</span><span class="sxs-lookup"><span data-stu-id="1d986-124">The shift of app logic to the client</span></span>

## <a name="an-open-source-and-cross-platform-net"></a><span data-ttu-id="1d986-125">Platforma .NET Open Source i Międzyplatformowe</span><span class="sxs-lookup"><span data-stu-id="1d986-125">An open-source and cross-platform .NET</span></span>

<span data-ttu-id="1d986-126">Po pierwszym wysłaniu formularzy sieci Web platformy .NET i ASP.NET, ekosystem platformy wyglądał znacznie inaczej niż dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="1d986-126">When .NET and ASP.NET Web Forms first shipped, the platform ecosystem looked much different than it does today.</span></span> <span data-ttu-id="1d986-127">Rynki pulpitów i serwerów zostały zdominowane przez system Windows.</span><span class="sxs-lookup"><span data-stu-id="1d986-127">The desktop and server markets were dominated by Windows.</span></span> <span data-ttu-id="1d986-128">Alternatywne platformy, takie jak macOS i Linux, były nadal zoptymalizowaniem do zdobycia trakcji.</span><span class="sxs-lookup"><span data-stu-id="1d986-128">Alternative platforms like macOS and Linux were still struggling to gain traction.</span></span> <span data-ttu-id="1d986-129">Formularze sieci Web ASP.NET są dostarczane z .NET Framework jako składnik tylko dla systemu Windows, co oznacza, że aplikacje ASP.NET Web Forms mogą działać tylko na maszynach z systemem Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1d986-129">ASP.NET Web Forms ships with the .NET Framework as a Windows-only component, which means ASP.NET Web Forms apps can only run on Windows Server machines.</span></span> <span data-ttu-id="1d986-130">Wiele nowoczesnych środowisk korzysta teraz z różnych rodzajów platform dla serwerów i maszyn programistycznych, takich jak obsługa wielu platform przez wiele użytkowników jest wymaganiem bezwzględnym.</span><span class="sxs-lookup"><span data-stu-id="1d986-130">Many modern environments now use different kinds of platforms for servers and development machines such that cross-platform support for many users is an absolute requirement.</span></span>

<span data-ttu-id="1d986-131">Większość nowoczesnych platform sieci Web jest teraz również typu open source, który ma wiele korzyści.</span><span class="sxs-lookup"><span data-stu-id="1d986-131">Most modern web frameworks are now also open-source, which has a number of benefits.</span></span> <span data-ttu-id="1d986-132">Użytkownicy nie beheld się do jednego właściciela projektu, aby naprawić błędy i dodać funkcje.</span><span class="sxs-lookup"><span data-stu-id="1d986-132">Users aren't beheld to a single project owner to fix bugs and add features.</span></span> <span data-ttu-id="1d986-133">Projekty open source zapewniają lepszą przejrzystość w zakresie postępu tworzenia i nadchodzących zmian.</span><span class="sxs-lookup"><span data-stu-id="1d986-133">Open-source projects provide improved transparency on development progress and upcoming changes.</span></span> <span data-ttu-id="1d986-134">Projekty typu open source korzystają z wkładów z całej społeczności i wspierają ekosystem typu "open source".</span><span class="sxs-lookup"><span data-stu-id="1d986-134">Open-source projects enjoy contributions from an entire community, and they foster a supportive open-source ecosystem.</span></span> <span data-ttu-id="1d986-135">Pomimo ryzyka dotyczącego typu "open source", wielu odbiorców i współautorów znalazły odpowiednie środki zaradcze, które umożliwiają im korzystanie z zalet ekosystemu typu "open source" w bezpieczny i racjonalny sposób.</span><span class="sxs-lookup"><span data-stu-id="1d986-135">Despite the risks of open-source, many consumers and contributors have found suitable mitigations that enable them to enjoy the benefits of an open-source ecosystem in a safe and reasonable way.</span></span> <span data-ttu-id="1d986-136">Przykłady takich środków zaradczych dotyczą umów licencyjnych współautora, przyjaznych licencji, skanowania rodowodowego i obsługi.</span><span class="sxs-lookup"><span data-stu-id="1d986-136">Examples of such mitigations include contributor license agreements, friendly licenses, pedigree scans, and supporting foundations.</span></span>

<span data-ttu-id="1d986-137">Społeczność .NET wykorzystuje zarówno obsługę międzyplatformową, jak i open-source.</span><span class="sxs-lookup"><span data-stu-id="1d986-137">The .NET community has embraced both cross-platform support and open-source.</span></span> <span data-ttu-id="1d986-138">.NET Core to wieloplatformowa implementacja programu .NET, która działa na mnóstwo platform, w tym Windows, macOS i różnych dystrybucji systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="1d986-138">.NET Core is an open-source and cross-platform implementation of .NET that runs on a plethora of platforms, including Windows, macOS, and various Linux distributions.</span></span> <span data-ttu-id="1d986-139">Środowisko Xamarin zapewnia wersję platformy .NET typu open source.</span><span class="sxs-lookup"><span data-stu-id="1d986-139">Xamarin provides Mono, an open-source version of .NET.</span></span> <span data-ttu-id="1d986-140">Mono działa w systemach Android, iOS i różnych innych, takich jak zegarki i inteligentne telewizory.</span><span class="sxs-lookup"><span data-stu-id="1d986-140">Mono runs on Android, iOS, and a variety of other form factors, including watches and smart TVs.</span></span> <span data-ttu-id="1d986-141">Firma Microsoft ogłosiła, że [.NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/) rozwiąże się z platformą .NET Core i mono do "pojedynczego środowiska uruchomieniowego platformy .NET i platformy, których można użyć wszędzie i które mają ujednolicone zachowania środowiska uruchomieniowego i środowiska deweloperskie".</span><span class="sxs-lookup"><span data-stu-id="1d986-141">Microsoft has announced that [.NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/) will reconcile .NET Core and Mono into "a single .NET runtime and framework that can be used everywhere and that has uniform runtime behaviors and developer experiences."</span></span>

<span data-ttu-id="1d986-142">Czy program będzie ASP.NET korzystanie z formularzy sieci Web od przejścia do usługi Open Source i dla wielu platform?</span><span class="sxs-lookup"><span data-stu-id="1d986-142">Will ASP.NET Web Forms benefit from the move to open-source and cross-platform support?</span></span> <span data-ttu-id="1d986-143">Odpowiedź, niestety, nie jest ani co najmniej w tym samym zakresie, jak reszta platformy.</span><span class="sxs-lookup"><span data-stu-id="1d986-143">The answer, unfortunately, is no, or at least not to the same extent as the rest of the platform.</span></span> <span data-ttu-id="1d986-144">Zespół .NET [niedawno wyczyścił](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/) , że ASP.NET formularzy sieci Web nie będzie można przenieść do platformy .NET Core lub .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1d986-144">The .NET team [recently made it clear](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/) that ASP.NET Web Forms won't be ported to .NET Core or .NET 5.</span></span> <span data-ttu-id="1d986-145">Dlaczego?</span><span class="sxs-lookup"><span data-stu-id="1d986-145">Why is that?</span></span>

<span data-ttu-id="1d986-146">Wystąpiły wysiłki w wczesnych dniach programu .NET Core do portów ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="1d986-146">There were efforts in the early days of .NET Core to port ASP.NET Web Forms.</span></span> <span data-ttu-id="1d986-147">Liczba niepotrzebnych zmian, które są zbyt drastyczne, jest zbyt duża.</span><span class="sxs-lookup"><span data-stu-id="1d986-147">The number of breaking changes required were found to be too drastic.</span></span> <span data-ttu-id="1d986-148">Istnieje również możliwość odłożenia tego, że nawet w przypadku firmy Microsoft istnieje ograniczenie liczby platform sieci Web, które może obsługiwać jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="1d986-148">There's also an admission here that even for Microsoft, there's a limit to the number of web frameworks that it can support simultaneously.</span></span> <span data-ttu-id="1d986-149">Prawdopodobnie ktoś w społeczności będzie miał przyczynę utworzenia otwartej i wieloplatformowej wersji formularzy sieci Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1d986-149">Perhaps someone in the community will take up the cause of creating an open-source and cross-platform version of ASP.NET Web Forms.</span></span> <span data-ttu-id="1d986-150">[Kod źródłowy formularzy sieci Web ASP.NET](https://github.com/microsoft/referencesource) został udostępniony publicznie w formie referencyjnej.</span><span class="sxs-lookup"><span data-stu-id="1d986-150">The [source code for ASP.NET Web Forms](https://github.com/microsoft/referencesource) has been made available publicly in reference form.</span></span> <span data-ttu-id="1d986-151">Jednak w takim przypadku wygląda na to, że formularze sieci Web ASP.NET będą pozostawać tylko w systemie Windows i bez modelu udziału Open Source.</span><span class="sxs-lookup"><span data-stu-id="1d986-151">But for the time being, it seems ASP.NET Web Forms will remain Windows-only and without an open-source contribution model.</span></span> <span data-ttu-id="1d986-152">Jeśli obsługa wielu platform lub Open Source stanie się ważna dla Twoich scenariuszy, należy wyszukać coś nowego.</span><span class="sxs-lookup"><span data-stu-id="1d986-152">If cross-platform support or open-source become important for your scenarios, then you'll need to look for something new.</span></span>

<span data-ttu-id="1d986-153">Czy oznacza to, że ASP.NET formularze sieci Web są *martwe* i nie powinny być już używane?</span><span class="sxs-lookup"><span data-stu-id="1d986-153">Does this mean ASP.NET Web Forms is *dead* and should no longer be used?</span></span> <span data-ttu-id="1d986-154">Oczywiście nie!</span><span class="sxs-lookup"><span data-stu-id="1d986-154">Of course not!</span></span> <span data-ttu-id="1d986-155">Tak długo, jak .NET Framework są dostarczane jako część systemu Windows, ASP.NET Web Forms będzie obsługiwaną strukturą.</span><span class="sxs-lookup"><span data-stu-id="1d986-155">As long as the .NET Framework ships as part of Windows, ASP.NET Web Forms will be a supported framework.</span></span> <span data-ttu-id="1d986-156">W przypadku wielu deweloperów korzystających z formularzy sieci Web nie jest to problem z obsługą międzyplatformowego i typu open-source.</span><span class="sxs-lookup"><span data-stu-id="1d986-156">For many Web Forms developers, the lack of cross-platform and open-source support is a non-issue.</span></span> <span data-ttu-id="1d986-157">Jeśli nie masz wymaganego wsparcia dla wielu platform, typu open source lub innych nowych funkcji w programie .NET Core lub .NET 5, naklejanie do ASP.NET formularzy sieci Web w systemie Windows jest odpowiednie.</span><span class="sxs-lookup"><span data-stu-id="1d986-157">If you don't have a requirement for cross-platform support, open-source, or any of the other new features in .NET Core or .NET 5, then sticking with ASP.NET Web Forms on Windows is fine.</span></span> <span data-ttu-id="1d986-158">ASP.NET Web Forms będzie w dalszym ciągu wydajnym sposobem pisania aplikacji internetowych przez wiele lat.</span><span class="sxs-lookup"><span data-stu-id="1d986-158">ASP.NET Web Forms will continue to be a productive way to write web apps for many years to come.</span></span>

<span data-ttu-id="1d986-159">Jednak istnieje inny trend rozważania i jest to zmiana na klienta.</span><span class="sxs-lookup"><span data-stu-id="1d986-159">But there's another trend worth considering, and that's the shift to the client.</span></span>

## <a name="client-side-web-development"></a><span data-ttu-id="1d986-160">Programowanie aplikacji sieci Web po stronie klienta</span><span class="sxs-lookup"><span data-stu-id="1d986-160">Client-side web development</span></span>

<span data-ttu-id="1d986-161">Wszystkie. Platformy sieci Web oparte na protokole NET, w tym formularze sieci Web ASP.NET, mają w historyczny sposób wspólne: te, które są *renderowane na serwerze*.</span><span class="sxs-lookup"><span data-stu-id="1d986-161">All of the .NET-based web frameworks, including ASP.NET Web Forms, have historically had one thing in common: they're *server-rendered*.</span></span> <span data-ttu-id="1d986-162">W przypadku aplikacji sieci Web renderowanych na serwerze przeglądarka wysyła żądanie do serwera, który wykonuje kod (kod platformy .NET w aplikacjach ASP.NET) w celu utworzenia odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="1d986-162">In server-rendered web apps, the browser makes a request to the server, which executes some code (.NET code in ASP.NET apps) to produce a response.</span></span> <span data-ttu-id="1d986-163">Ta odpowiedź jest wysyłana z powrotem do przeglądarki w celu obsługi.</span><span class="sxs-lookup"><span data-stu-id="1d986-163">That response is sent back to the browser to handle.</span></span> <span data-ttu-id="1d986-164">W tym modelu przeglądarka jest używana jako aparat renderowania cienkiego.</span><span class="sxs-lookup"><span data-stu-id="1d986-164">In this model, the browser is used as a thin rendering engine.</span></span> <span data-ttu-id="1d986-165">Na serwerze występuje poprawność tworzenia interfejsu użytkownika, uruchamiania logiki biznesowej i zarządzania stanem.</span><span class="sxs-lookup"><span data-stu-id="1d986-165">The hard work of producing the UI, running the business logic, and managing state occurs on the server.</span></span>

<span data-ttu-id="1d986-166">Jednak przeglądarki stają się uniwersalną platformą.</span><span class="sxs-lookup"><span data-stu-id="1d986-166">However, browsers have become versatile platforms.</span></span> <span data-ttu-id="1d986-167">Implementują one coraz większą liczbę otwartych standardów sieci Web, które zapewniają dostęp do możliwości komputera użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1d986-167">They implement an ever-increasing number of open web standards that grant access to the capabilities of the user's machine.</span></span> <span data-ttu-id="1d986-168">Dlaczego nie należy korzystać z mocy obliczeniowej, magazynu, pamięci i innych zasobów urządzenia klienckiego?</span><span class="sxs-lookup"><span data-stu-id="1d986-168">Why not take advantage of the compute power, storage, memory, and other resources of the client device?</span></span> <span data-ttu-id="1d986-169">Interakcje interfejsu użytkownika w szczególności mogą korzystać z bogatszego i bardziej interaktywnego działania, gdy jest obsługiwany co najmniej częściowo lub całkowicie po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="1d986-169">UI interactions in particular can benefit from a richer and more interactive feel when handled at least partially or completely client-side.</span></span> <span data-ttu-id="1d986-170">Logika i dane, które powinny być obsługiwane na serwerze, nadal mogą być obsługiwane po stronie serwera.</span><span class="sxs-lookup"><span data-stu-id="1d986-170">Logic and data that should be handled on the server can still be handled server-side.</span></span> <span data-ttu-id="1d986-171">Mogą być używane wywołania interfejsu API sieci Web lub nawet za pośrednictwem protokołów w czasie rzeczywistym, takich jak WebSockets.</span><span class="sxs-lookup"><span data-stu-id="1d986-171">Web API calls or even over real-time protocols, like WebSockets, can be used.</span></span> <span data-ttu-id="1d986-172">Te korzyści są dostępne dla deweloperów sieci Web bezpłatnie, jeśli chcą pisać kod JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1d986-172">These benefits are available to web developers for free if they're willing to write JavaScript.</span></span> <span data-ttu-id="1d986-173">Struktury interfejsu użytkownika po stronie klienta, takie jak kątowy, reagowanie i Vue, upraszczają Programowanie aplikacji sieci Web po stronie klienta i osiągnęły popularność.</span><span class="sxs-lookup"><span data-stu-id="1d986-173">Client-side UI frameworks, such as Angular, React, and Vue, simplify client-side web development and have grown in popularity.</span></span> <span data-ttu-id="1d986-174">Deweloperzy ASP.NET Web Forms mogą również korzystać z klienta programu, a nawet korzystać z wbudowanych platform języka JavaScript, takich jak ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="1d986-174">ASP.NET Web Forms developers can also benefit from leveraging the client, and even have some out-of-the-box support with integrated JavaScript frameworks like ASP.NET AJAX.</span></span>

<span data-ttu-id="1d986-175">Mostkowanie obejmuje dwie różne platformy i ekosystemy (.NET i JavaScript).</span><span class="sxs-lookup"><span data-stu-id="1d986-175">But bridging two different platforms and ecosystems (.NET and JavaScript) comes with a cost.</span></span> <span data-ttu-id="1d986-176">Wiedza jest wymagana w dwóch równoległych światach z różnymi językami, strukturami i narzędziami.</span><span class="sxs-lookup"><span data-stu-id="1d986-176">Expertise is required in two parallel worlds with different languages, frameworks, and tools.</span></span> <span data-ttu-id="1d986-177">Kod i logika nie mogą być łatwo udostępniane między klientem i serwerem, co skutkuje duplikowaniem i pracą inżynieryjną.</span><span class="sxs-lookup"><span data-stu-id="1d986-177">Code and logic can't be easily shared between client and server, resulting in duplication and engineering overhead.</span></span> <span data-ttu-id="1d986-178">Może być również trudne do utrzymania w ekosystemie JavaScript, który ma historię rozwoju na szybkości breakneck.</span><span class="sxs-lookup"><span data-stu-id="1d986-178">It can also be difficult to keep up with the JavaScript ecosystem, which has a history of evolving at breakneck speed.</span></span> <span data-ttu-id="1d986-179">Narzędzia platformy frontonu i preferencji narzędzi do kompilacji szybko zmieniają się.</span><span class="sxs-lookup"><span data-stu-id="1d986-179">Front-end framework and build tool preferences change quickly.</span></span> <span data-ttu-id="1d986-180">Branża zaobserwowano postęp od grunt do Gulp z pakietem WebPack i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="1d986-180">The industry has observed the progression from Grunt to Gulp to Webpack, and so on.</span></span> <span data-ttu-id="1d986-181">Te same Restless zmiany wystąpiły z platformami frontonu, takimi jak jQuery, odcinanie, kątowe, reagowanie i Vue.</span><span class="sxs-lookup"><span data-stu-id="1d986-181">The same restless churn has occurred with front-end frameworks such as jQuery, Knockout, Angular, React, and Vue.</span></span> <span data-ttu-id="1d986-182">Jednak podano nieznaczny monopol przeglądarki JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1d986-182">But given JavaScript's browser monopoly, there was little choice in the matter.</span></span> <span data-ttu-id="1d986-183">Oznacza to, że do momentu, aż społeczność internetowa się nie *pomiraclea* .</span><span class="sxs-lookup"><span data-stu-id="1d986-183">That is, until the web community got together and caused a *miracle* to happen!</span></span>

## <a name="webassembly-fulfills-a-need"></a><span data-ttu-id="1d986-184">Zestaw webassembly spełnia potrzeby</span><span class="sxs-lookup"><span data-stu-id="1d986-184">WebAssembly fulfills a need</span></span>

<span data-ttu-id="1d986-185">W 2015, głównym dostawcom przeglądarki przyłączono siły w grupie społeczność W3C, aby utworzyć nowy otwarty standard sieci Web o nazwie webassembly.</span><span class="sxs-lookup"><span data-stu-id="1d986-185">In 2015, the major browser vendors joined forces in a W3C Community Group to create a new open web standard called WebAssembly.</span></span> <span data-ttu-id="1d986-186">Webassembly to bajtowy kod dla sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1d986-186">WebAssembly is a byte code for the Web.</span></span> <span data-ttu-id="1d986-187">Jeśli można skompilować swój kod do zestawu webassembly, można go uruchomić w dowolnej przeglądarce na dowolnej platformie w niemal natywnej szybkości.</span><span class="sxs-lookup"><span data-stu-id="1d986-187">If you can compile your code to WebAssembly, it can then run on any browser on any platform at near native speed.</span></span> <span data-ttu-id="1d986-188">Początkowe wysiłki skupiające się naC++języku C/.</span><span class="sxs-lookup"><span data-stu-id="1d986-188">Initial efforts focused on C/C++.</span></span> <span data-ttu-id="1d986-189">Wynikiem jest znaczną prezentację uruchamiania natywnych aparatów graficznych 3W bezpośrednio w przeglądarce bez wtyczek.</span><span class="sxs-lookup"><span data-stu-id="1d986-189">The result was a dramatic demonstration of running native 3D graphics engines directly in the browser without plugins.</span></span> <span data-ttu-id="1d986-190">Zestaw webassembly został znormalizowany i zaimplementowany przez wszystkie główne przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="1d986-190">WebAssembly has since been standardized and implemented by all major browsers.</span></span>

<span data-ttu-id="1d986-191">Działanie na uruchomionym platformie .NET w zestawie webassembly zostało ogłoszone w późnej 2017 i oczekuje się, że wyśle się w 2020, włącznie z wsparciem z platformy .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1d986-191">Work on running .NET on WebAssembly was announced in late 2017 and is expected to ship in 2020, including support from .NET 5.</span></span> <span data-ttu-id="1d986-192">Możliwość uruchamiania kodu platformy .NET bezpośrednio w przeglądarce umożliwia tworzenie aplikacji sieci Web na całym stosie przy użyciu platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="1d986-192">The ability to run .NET code directly in the browser enables full-stack web development with .NET.</span></span>

## <a name="blazor-full-stack-web-development-with-net"></a><span data-ttu-id="1d986-193">Blazor: Programowanie aplikacji sieci Web w pełnym stosie przy użyciu platformy .NET</span><span class="sxs-lookup"><span data-stu-id="1d986-193">Blazor: full-stack web development with .NET</span></span>

<span data-ttu-id="1d986-194">Ponadto możliwość uruchamiania kodu platformy .NET w przeglądarce nie zapewnia kompleksowego środowiska tworzenia aplikacji sieci Web po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="1d986-194">On its own, the ability to run .NET code in a browser doesn't provide an end-to-end experience for creating client-side web apps.</span></span> <span data-ttu-id="1d986-195">Jest to miejsce, w którym znajduje się Blazor.</span><span class="sxs-lookup"><span data-stu-id="1d986-195">That's where Blazor comes in.</span></span> <span data-ttu-id="1d986-196">Blazor to struktura interfejsu użytkownika sieci Web po stronie klienta oparta C# na zamiast języka JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1d986-196">Blazor is a client-side web UI framework based on C# instead of JavaScript.</span></span> <span data-ttu-id="1d986-197">Blazor można uruchomić bezpośrednio w przeglądarce za pośrednictwem webassembly.</span><span class="sxs-lookup"><span data-stu-id="1d986-197">Blazor can run directly in the browser via WebAssembly.</span></span> <span data-ttu-id="1d986-198">Nie są wymagane żadne wtyczki przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="1d986-198">No browser plugins are required.</span></span> <span data-ttu-id="1d986-199">Alternatywnie aplikacje Blazor mogą uruchamiać serwer na platformie .NET Core i obsługiwać wszystkie interakcje użytkowników w czasie rzeczywistym z przeglądarką.</span><span class="sxs-lookup"><span data-stu-id="1d986-199">Alternatively, Blazor apps can run server-side on .NET Core and handle all user interactions over a real-time connection with the browser.</span></span>

<span data-ttu-id="1d986-200">Blazor ma wspaniałe narzędzia obsługiwane w programie Visual Studio i Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1d986-200">Blazor has great tooling support in Visual Studio and Visual Studio Code.</span></span> <span data-ttu-id="1d986-201">Struktura zawiera również pełny model składników interfejsu użytkownika i oferuje wbudowane funkcje programu:</span><span class="sxs-lookup"><span data-stu-id="1d986-201">The framework also includes a full UI component model and has built-in facilities for:</span></span>

* <span data-ttu-id="1d986-202">Formularze i walidacja</span><span class="sxs-lookup"><span data-stu-id="1d986-202">Forms and validation</span></span>
* <span data-ttu-id="1d986-203">Wstrzykiwanie zależności</span><span class="sxs-lookup"><span data-stu-id="1d986-203">Dependency injection</span></span>
* <span data-ttu-id="1d986-204">Routing po stronie klienta</span><span class="sxs-lookup"><span data-stu-id="1d986-204">Client-side routing</span></span>
* <span data-ttu-id="1d986-205">Układy</span><span class="sxs-lookup"><span data-stu-id="1d986-205">Layouts</span></span>
* <span data-ttu-id="1d986-206">Debugowanie w przeglądarce</span><span class="sxs-lookup"><span data-stu-id="1d986-206">In-browser debugging</span></span>
* <span data-ttu-id="1d986-207">Międzyoperacyjność w języku JavaScript</span><span class="sxs-lookup"><span data-stu-id="1d986-207">JavaScript interop</span></span>

<span data-ttu-id="1d986-208">Blazor ma wiele wspólnych metod ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="1d986-208">Blazor has a lot in common with ASP.NET Web Forms.</span></span> <span data-ttu-id="1d986-209">Obie te platformy oferują modele programowania opartego na składnikach, sterowanych zdarzeniami.</span><span class="sxs-lookup"><span data-stu-id="1d986-209">Both frameworks offer component-based, event-driven, stateful UI programming models.</span></span> <span data-ttu-id="1d986-210">Główną różnicą architektury jest to, że ASP.NET Web Forms działa tylko na serwerze.</span><span class="sxs-lookup"><span data-stu-id="1d986-210">The main architectural difference is that ASP.NET Web Forms runs only on the server.</span></span> <span data-ttu-id="1d986-211">Blazor można uruchomić na kliencie w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="1d986-211">Blazor can run on the client in the browser.</span></span> <span data-ttu-id="1d986-212">Ale jeśli korzystasz z tła ASP.NET formularzy sieci Web, istnieje wiele Blazor, które będą znane.</span><span class="sxs-lookup"><span data-stu-id="1d986-212">But if you're coming from an ASP.NET Web Forms background, there's a lot in Blazor that will feel familiar.</span></span> <span data-ttu-id="1d986-213">Blazor to naturalne rozwiązanie dla deweloperów formularzy sieci Web ASP.NET, które chcą korzystać z funkcji tworzenia aplikacji po stronie klienta i środowiska typu open-source na platformie .NET.</span><span class="sxs-lookup"><span data-stu-id="1d986-213">Blazor is a natural solution for ASP.NET Web Forms developers looking for a way to take advantage of client-side development and the open-source, cross-platform future of .NET.</span></span>

<span data-ttu-id="1d986-214">Ta książka zawiera wprowadzenie do Blazor, które są przeznaczone dla deweloperów ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="1d986-214">This book provides an introduction to Blazor that is catered specifically to ASP.NET Web Forms developers.</span></span> <span data-ttu-id="1d986-215">Poszczególne koncepcje Blazor są prezentowane w kontekście analogicznych funkcji i praktyk formularzy sieci Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1d986-215">Each Blazor concept is presented in the context of analogous ASP.NET Web Forms features and practices.</span></span> <span data-ttu-id="1d986-216">Na koniec tej książki znajdziesz następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="1d986-216">By the end of this book, you'll have an understanding of:</span></span>

* <span data-ttu-id="1d986-217">Jak kompilować aplikacje Blazor.</span><span class="sxs-lookup"><span data-stu-id="1d986-217">How to build Blazor apps.</span></span>
* <span data-ttu-id="1d986-218">Jak działa Blazor.</span><span class="sxs-lookup"><span data-stu-id="1d986-218">How Blazor works.</span></span>
* <span data-ttu-id="1d986-219">Jak Blazor odnosi się do programu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d986-219">How Blazor relates to .NET Core.</span></span>
* <span data-ttu-id="1d986-220">Odpowiednie strategie migrowania istniejących aplikacji ASP.NET Web Forms do Blazor, tam gdzie to możliwe.</span><span class="sxs-lookup"><span data-stu-id="1d986-220">Reasonable strategies for migrating existing ASP.NET Web Forms apps to Blazor where appropriate.</span></span>

## <a name="get-started-with-blazor"></a><span data-ttu-id="1d986-221">Wprowadzenie do Blazor</span><span class="sxs-lookup"><span data-stu-id="1d986-221">Get started with Blazor</span></span>

<span data-ttu-id="1d986-222">Rozpoczynanie pracy z usługą Blazor jest łatwe.</span><span class="sxs-lookup"><span data-stu-id="1d986-222">Getting started with Blazor is easy.</span></span> <span data-ttu-id="1d986-223">Przejdź do <https://blazor.net> obszaru i postępuj zgodnie z linkami, aby zainstalować odpowiednie zestaw .NET Core SDK i szablony projektu Blazor.</span><span class="sxs-lookup"><span data-stu-id="1d986-223">Go to <https://blazor.net> and follow the links to install the appropriate .NET Core SDK and Blazor project templates.</span></span> <span data-ttu-id="1d986-224">Znajdziesz również instrukcje dotyczące konfigurowania narzędzi Blazor w programie Visual Studio lub Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1d986-224">You'll also find instructions for setting up the Blazor tooling in Visual Studio or Visual Studio Code.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1d986-225">[Poprzedni](index.md)
>[Następny](architecture-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="1d986-225">[Previous](index.md)
[Next](architecture-comparison.md)</span></span>