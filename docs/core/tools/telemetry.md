---
title: Telemetria zestawu .NET SDK
description: Odkryj funkcje telemetrii zestawu .NET SDK, które zbierają informacje dotyczące użycia do analizy, zbierane dane oraz sposób ich wyłączania.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 4f137822c61e1a04eccd28ebd0cd56c04f4a85e2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633873"
---
# <a name="net-sdk-telemetry"></a><span data-ttu-id="104ef-103">Telemetria zestawu .NET SDK</span><span class="sxs-lookup"><span data-stu-id="104ef-103">.NET SDK telemetry</span></span>

<span data-ttu-id="104ef-104">[Zestaw SDK platformy .NET](index.md) zawiera funkcję telemetrii, która zbiera dane użycia i informacje o wyjątkach w przypadku awarii interfejsu wiersza polecenia platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="104ef-104">The [.NET SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET CLI crashes.</span></span> <span data-ttu-id="104ef-105">Interfejs wiersza polecenia platformy .NET jest dostarczany z zestawem SDK platformy .NET i jest zestawem zleceń, które umożliwiają kompilowanie, testowanie i publikowanie aplikacji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="104ef-105">The .NET CLI comes with the .NET SDK and is the set of verbs that enable you to build, test, and publish your .NET apps.</span></span> <span data-ttu-id="104ef-106">Ważne jest, aby zespół .NET wiedział, w jaki sposób narzędzia są używane, aby można je było ulepszyć.</span><span class="sxs-lookup"><span data-stu-id="104ef-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="104ef-107">Informacje o błędach ułatwiają zespołowi Rozwiązywanie problemów i rozwiązywanie usterek.</span><span class="sxs-lookup"><span data-stu-id="104ef-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="104ef-108">Zebrane dane są publikowane w agregacji w ramach [licencji Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="104ef-108">The collected data is published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="104ef-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="104ef-109">Scope</span></span>

<span data-ttu-id="104ef-110">`dotnet` Program ma dwie funkcje: do uruchamiania aplikacji i wykonywania poleceń interfejsu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="104ef-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="104ef-111">Dane telemetryczne *nie są zbierane* podczas korzystania `dotnet` z programu w celu uruchomienia aplikacji w następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="104ef-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="104ef-112">Dane telemetryczne *są zbierane* podczas korzystania z [poleceń interfejsu wiersza polecenia platformy .NET](index.md), takich jak:</span><span class="sxs-lookup"><span data-stu-id="104ef-112">Telemetry *is collected* when using any of the [.NET CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="104ef-113">Jak zrezygnować</span><span class="sxs-lookup"><span data-stu-id="104ef-113">How to opt out</span></span>

<span data-ttu-id="104ef-114">Funkcja telemetrii zestawu .NET SDK jest domyślnie włączona.</span><span class="sxs-lookup"><span data-stu-id="104ef-114">The .NET SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="104ef-115">Aby zrezygnować z funkcji telemetrii, należy ustawić `DOTNET_CLI_TELEMETRY_OPTOUT` zmienną środowiskową na `1` lub `true` .</span><span class="sxs-lookup"><span data-stu-id="104ef-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="104ef-116">Po pomyślnej instalacji w instalatorze zestawu .NET SDK zostanie również wysłany pojedynczy wpis telemetrii.</span><span class="sxs-lookup"><span data-stu-id="104ef-116">A single telemetry entry is also sent by the .NET SDK installer when a successful installation happens.</span></span> <span data-ttu-id="104ef-117">Aby zrezygnować z programu, należy ustawić `DOTNET_CLI_TELEMETRY_OPTOUT` zmienną środowiskową przed zainstalowaniem zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="104ef-118">Mogąc</span><span class="sxs-lookup"><span data-stu-id="104ef-118">Disclosure</span></span>

<span data-ttu-id="104ef-119">Zestaw SDK platformy .NET wyświetla tekst podobny do poniższego podczas pierwszego uruchomienia jednego z [poleceń interfejsu wiersza polecenia platformy .NET](index.md) (na przykład `dotnet build` ).</span><span class="sxs-lookup"><span data-stu-id="104ef-119">The .NET SDK displays text similar to the following when you first run one of the [.NET CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="104ef-120">Tekst może się nieco różnić w zależności od używanej wersji zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="104ef-121">To "pierwsze uruchomienie" polega na tym, jak firma Microsoft powiadamia użytkownika o zbieraniu danych.</span><span class="sxs-lookup"><span data-stu-id="104ef-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="104ef-122">Aby wyłączyć ten komunikat i komunikat powitalny platformy .NET, ustaw dla `DOTNET_NOLOGO` zmiennej środowiskowej wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="104ef-122">To disable this message and the .NET welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="104ef-123">Należy zauważyć, że ta zmienna nie ma wpływu na rezygnację z telemetrii.</span><span class="sxs-lookup"><span data-stu-id="104ef-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="104ef-124">Punkty danych</span><span class="sxs-lookup"><span data-stu-id="104ef-124">Data points</span></span>

<span data-ttu-id="104ef-125">Funkcja telemetrii nie zbiera danych osobowych, takich jak nazwy użytkowników lub adresy e-mail.</span><span class="sxs-lookup"><span data-stu-id="104ef-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="104ef-126">Nie skanuje kodu i nie wyodrębnia danych na poziomie projektu, takich jak Name, Repository lub Author.</span><span class="sxs-lookup"><span data-stu-id="104ef-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="104ef-127">Dane są bezpiecznie przesyłane do serwerów firmy Microsoft przy użyciu technologii [Azure monitor](https://azure.microsoft.com/services/monitor/) , w ramach ograniczonego dostępu, i publikowane w ramach ścisłych kontroli zabezpieczeń z bezpiecznych systemów [usługi Azure Storage](https://azure.microsoft.com/services/storage/) .</span><span class="sxs-lookup"><span data-stu-id="104ef-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="104ef-128">Ochrona prywatności jest dla nas ważna.</span><span class="sxs-lookup"><span data-stu-id="104ef-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="104ef-129">Jeśli podejrzewasz, że Telemetria zbiera dane poufne lub dane są w sposób niezabezpieczony lub niewłaściwie obsłużone, należy rozwiązać problem w repozytorium [dotnet/SDK](https://github.com/dotnet/sdk/issues) lub wysłać wiadomość e-mail do [dotnet@microsoft.com](mailto:dotnet@microsoft.com) badania.</span><span class="sxs-lookup"><span data-stu-id="104ef-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/sdk](https://github.com/dotnet/sdk/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="104ef-130">Funkcja telemetrii zbiera następujące dane:</span><span class="sxs-lookup"><span data-stu-id="104ef-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="104ef-131">Wersje zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="104ef-131">SDK versions</span></span> | <span data-ttu-id="104ef-132">Dane</span><span class="sxs-lookup"><span data-stu-id="104ef-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="104ef-133">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-133">All</span></span>          | <span data-ttu-id="104ef-134">Sygnatura czasowa wywołania.</span><span class="sxs-lookup"><span data-stu-id="104ef-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="104ef-135">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-135">All</span></span>          | <span data-ttu-id="104ef-136">Wywołano polecenie (na przykład "Kompilacja"), wartość skrótu rozpoczynająca się w 2,1.</span><span class="sxs-lookup"><span data-stu-id="104ef-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="104ef-137">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-137">All</span></span>          | <span data-ttu-id="104ef-138">Trzy adresy IP używane do określenia lokalizacji geograficznej.</span><span class="sxs-lookup"><span data-stu-id="104ef-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="104ef-139">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-139">All</span></span>          | <span data-ttu-id="104ef-140">System operacyjny i wersja.</span><span class="sxs-lookup"><span data-stu-id="104ef-140">Operating system and version.</span></span> |
| <span data-ttu-id="104ef-141">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-141">All</span></span>          | <span data-ttu-id="104ef-142">Identyfikator środowiska uruchomieniowego (RID), na którym jest uruchomiony zestaw SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="104ef-143">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-143">All</span></span>          | <span data-ttu-id="104ef-144">Wersja zestawu SDK platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="104ef-144">.NET SDK version.</span></span> |
| <span data-ttu-id="104ef-145">Wszystko</span><span class="sxs-lookup"><span data-stu-id="104ef-145">All</span></span>          | <span data-ttu-id="104ef-146">Profil telemetrii: opcjonalna wartość używana tylko z jawnym zapytaniem użytkownika i używana wewnętrznie w firmie Microsoft.</span><span class="sxs-lookup"><span data-stu-id="104ef-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="104ef-147">>= 2,0</span><span class="sxs-lookup"><span data-stu-id="104ef-147">>=2.0</span></span>        | <span data-ttu-id="104ef-148">Argumenty polecenia i opcje: zbierane są kilka argumentów i opcji (nie dowolnych ciągów).</span><span class="sxs-lookup"><span data-stu-id="104ef-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="104ef-149">Zobacz [zebrane opcje](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="104ef-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="104ef-150">Skrót po 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="104ef-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="104ef-151">>= 2,0</span><span class="sxs-lookup"><span data-stu-id="104ef-151">>=2.0</span></span>         | <span data-ttu-id="104ef-152">Czy zestaw SDK działa w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="104ef-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="104ef-153">>= 2,0</span><span class="sxs-lookup"><span data-stu-id="104ef-153">>=2.0</span></span>         | <span data-ttu-id="104ef-154">Platformy docelowe (ze `TargetFramework` zdarzenia), które zostały zmieszane, począwszy od 2,1.</span><span class="sxs-lookup"><span data-stu-id="104ef-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="104ef-155">>= 2,0</span><span class="sxs-lookup"><span data-stu-id="104ef-155">>=2.0</span></span>         | <span data-ttu-id="104ef-156">Adres MAC (SHA256) z mieszaniem (w Access Control skrócie).</span><span class="sxs-lookup"><span data-stu-id="104ef-156">Hashed Media Access Control (MAC) address (SHA256).</span></span> |
| <span data-ttu-id="104ef-157">>= 2,0</span><span class="sxs-lookup"><span data-stu-id="104ef-157">>=2.0</span></span>         | <span data-ttu-id="104ef-158">Skrót bieżącego katalogu roboczego.</span><span class="sxs-lookup"><span data-stu-id="104ef-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="104ef-159">>= 2,0</span><span class="sxs-lookup"><span data-stu-id="104ef-159">>=2.0</span></span>         | <span data-ttu-id="104ef-160">Zainstaluj Raport z sukcesem z nazwą pliku exe Instalatora.</span><span class="sxs-lookup"><span data-stu-id="104ef-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="104ef-161">>= 2.1.300</span><span class="sxs-lookup"><span data-stu-id="104ef-161">>=2.1.300</span></span>     | <span data-ttu-id="104ef-162">Wersja jądra.</span><span class="sxs-lookup"><span data-stu-id="104ef-162">Kernel version.</span></span> |
| <span data-ttu-id="104ef-163">>= 2.1.300</span><span class="sxs-lookup"><span data-stu-id="104ef-163">>=2.1.300</span></span>     | <span data-ttu-id="104ef-164">Libc wydanie/wersja.</span><span class="sxs-lookup"><span data-stu-id="104ef-164">Libc release/version.</span></span> |
| <span data-ttu-id="104ef-165">>= 3.0.100</span><span class="sxs-lookup"><span data-stu-id="104ef-165">>=3.0.100</span></span>     | <span data-ttu-id="104ef-166">Czy dane wyjściowe zostały przekierowane (wartość true lub false).</span><span class="sxs-lookup"><span data-stu-id="104ef-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="104ef-167">>= 3.0.100</span><span class="sxs-lookup"><span data-stu-id="104ef-167">>=3.0.100</span></span>     | <span data-ttu-id="104ef-168">W przypadku awarii interfejsu wiersza polecenia/zestawu SDK typ wyjątku i jego ślad stosu (kod interfejsu wiersza polecenia/zestawu SDK jest dołączony do wysyłanego śladu stosu).</span><span class="sxs-lookup"><span data-stu-id="104ef-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="104ef-169">Aby uzyskać więcej informacji, zobacz [zbieranie danych telemetrycznych dotyczących wyjątków interfejsu wiersza polecenia platformy .NET/zestawu SDK](#net-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="104ef-169">For more information, see [.NET CLI/SDK crash exception telemetry collected](#net-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="104ef-170">Zebrane opcje</span><span class="sxs-lookup"><span data-stu-id="104ef-170">Collected options</span></span>

<span data-ttu-id="104ef-171">Niektóre polecenia wysyłają dodatkowe dane.</span><span class="sxs-lookup"><span data-stu-id="104ef-171">Certain commands send additional data.</span></span> <span data-ttu-id="104ef-172">Podzbiór poleceń wysyła pierwszy argument:</span><span class="sxs-lookup"><span data-stu-id="104ef-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="104ef-173">Polecenie</span><span class="sxs-lookup"><span data-stu-id="104ef-173">Command</span></span>               | <span data-ttu-id="104ef-174">Wysłane dane pierwszego argumentu</span><span class="sxs-lookup"><span data-stu-id="104ef-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="104ef-175">Trwa kwerenda pomocy dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="104ef-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="104ef-176">Nazwa szablonu (wartość skrótu).</span><span class="sxs-lookup"><span data-stu-id="104ef-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="104ef-177">Słowo `package` lub `reference` .</span><span class="sxs-lookup"><span data-stu-id="104ef-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="104ef-178">Słowo `package` lub `reference` .</span><span class="sxs-lookup"><span data-stu-id="104ef-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="104ef-179">Słowo `package` lub `reference` .</span><span class="sxs-lookup"><span data-stu-id="104ef-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="104ef-180">Słowo `add` , `list` , lub `remove` .</span><span class="sxs-lookup"><span data-stu-id="104ef-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="104ef-181">Słowo `delete` , `locals` , lub `push` .</span><span class="sxs-lookup"><span data-stu-id="104ef-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="104ef-182">Podzbiór poleceń wysyła wybrane opcje, jeśli są używane, wraz z ich wartościami:</span><span class="sxs-lookup"><span data-stu-id="104ef-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="104ef-183">Opcja</span><span class="sxs-lookup"><span data-stu-id="104ef-183">Option</span></span>                  | <span data-ttu-id="104ef-184">Polecenia</span><span class="sxs-lookup"><span data-stu-id="104ef-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="104ef-185">Wszystkie polecenia</span><span class="sxs-lookup"><span data-stu-id="104ef-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="104ef-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="104ef-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="104ef-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="104ef-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="104ef-188">`dotnet build`,  `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="104ef-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="104ef-189">Z wyjątkiem `--verbosity` i `--sdk-package-version` , wszystkie inne wartości są zmieszane, począwszy od platformy .NET Core 2.1.100 SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="104ef-190">Zebrane dane telemetryczne wyjątków platformy .NET/zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="104ef-190">.NET CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="104ef-191">Jeśli wystąpi awaria interfejsu wiersza polecenia platformy .NET/zestawu SDK, program zbiera informacje o nazwie i śladie stosu kodu CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-191">If the .NET CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="104ef-192">Te informacje są zbierane w celu oceny problemów i poprawy jakości zestawu .NET SDK i interfejsu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="104ef-192">This information is collected to assess problems and improve the quality of the .NET SDK and CLI.</span></span> <span data-ttu-id="104ef-193">Ten artykuł zawiera informacje o zbieranych danych.</span><span class="sxs-lookup"><span data-stu-id="104ef-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="104ef-194">Zawiera również wskazówki dotyczące sposobu, w jaki użytkownicy tworzący własne wersje zestawu .NET SDK mogą uniknąć przypadkowego ujawnienia informacji osobistych lub poufnych.</span><span class="sxs-lookup"><span data-stu-id="104ef-194">It also provides tips on how users building their own version of the .NET SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="104ef-195">Typy zebranych danych</span><span class="sxs-lookup"><span data-stu-id="104ef-195">Types of collected data</span></span>

<span data-ttu-id="104ef-196">Interfejs wiersza polecenia platformy .NET zbiera informacje tylko dla wyjątków CLI/SDK, a nie wyjątków w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="104ef-196">.NET CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="104ef-197">Zebrane dane zawierają nazwę wyjątku i ślad stosu.</span><span class="sxs-lookup"><span data-stu-id="104ef-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="104ef-198">Ten ślad stosu jest kodem CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="104ef-199">Poniższy przykład przedstawia rodzaj zbieranych danych:</span><span class="sxs-lookup"><span data-stu-id="104ef-199">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="104ef-200">Unikaj przypadkowego ujawnienia informacji</span><span class="sxs-lookup"><span data-stu-id="104ef-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="104ef-201">Współautorzy platformy .NET i inne osoby korzystające z wersji zestawu .NET SDK, które samodzielnie tworzą, powinny rozważyć ścieżkę do kodu źródłowego zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="104ef-201">.NET contributors and anyone else running a version of the .NET SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="104ef-202">Jeśli wystąpi awaria podczas korzystania z zestawu .NET SDK, który jest niestandardową kompilacją debugowania lub została skonfigurowana za pomocą niestandardowych plików symboli kompilacji, ścieżka pliku źródłowego zestawu SDK z maszyny kompilacji jest zbierana jako część śladu stosu i nie jest używana jako wartość skrótu.</span><span class="sxs-lookup"><span data-stu-id="104ef-202">If a crash occurs while using a .NET SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="104ef-203">Z tego powodu niestandardowe kompilacje zestawu .NET SDK nie powinny znajdować się w katalogach, których nazwy ścieżek ujawniają osobiste lub poufne informacje.</span><span class="sxs-lookup"><span data-stu-id="104ef-203">Because of this, custom builds of the .NET SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="104ef-204">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="104ef-204">See also</span></span>

- [<span data-ttu-id="104ef-205">Dane telemetryczne interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="104ef-205">.NET CLI Telemetry Data</span></span>](https://dotnet.microsoft.com/platform/telemetry)
- [<span data-ttu-id="104ef-206">Źródło odwołania telemetrii (repozytorium dotnet/SDK)</span><span class="sxs-lookup"><span data-stu-id="104ef-206">Telemetry reference source (dotnet/sdk repository)</span></span>](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
