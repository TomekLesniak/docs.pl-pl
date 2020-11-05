---
title: Globalizacja i ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET], about globalization
- global applications, globalization
- international applications [.NET], globalization
- world-ready applications, globalization
- application development [.NET], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: e0ca78871d1ddf851148096c8c6cfd10076763ab
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400882"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="95a6f-102">Globalizacja i ICU platformy .NET</span><span class="sxs-lookup"><span data-stu-id="95a6f-102">.NET globalization and ICU</span></span>

<span data-ttu-id="95a6f-103">W przeszłości interfejsy API globalizacji platformy .NET używały różnych bibliotek bazowych na różnych platformach.</span><span class="sxs-lookup"><span data-stu-id="95a6f-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="95a6f-104">W systemie UNIX interfejsy API używające [składników międzynarodowych dla standardu Unicode (ICU)](http://site.icu-project.org/home)i w systemie Windows używają [obsługi języków narodowych (NLS)](/windows/win32/intl/national-language-support).</span><span class="sxs-lookup"><span data-stu-id="95a6f-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="95a6f-105">Spowodowało to pewne różnice w kilku globalizacji interfejsów API podczas uruchamiania aplikacji na różnych platformach.</span><span class="sxs-lookup"><span data-stu-id="95a6f-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="95a6f-106">Różnice w zachowaniu były widoczne w następujących obszarach:</span><span class="sxs-lookup"><span data-stu-id="95a6f-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="95a6f-107">Kultury i dane kulturowe</span><span class="sxs-lookup"><span data-stu-id="95a6f-107">Cultures and culture data</span></span>
- <span data-ttu-id="95a6f-108">Wielkość liter w postaci ciągów</span><span class="sxs-lookup"><span data-stu-id="95a6f-108">String casing</span></span>
- <span data-ttu-id="95a6f-109">Sortowanie i wyszukiwanie ciągów</span><span class="sxs-lookup"><span data-stu-id="95a6f-109">String sorting and searching</span></span>
- <span data-ttu-id="95a6f-110">Sortuj klucze</span><span class="sxs-lookup"><span data-stu-id="95a6f-110">Sort keys</span></span>
- <span data-ttu-id="95a6f-111">Normalizacja ciągu</span><span class="sxs-lookup"><span data-stu-id="95a6f-111">String normalization</span></span>
- <span data-ttu-id="95a6f-112">Obsługa międzynarodowych nazw domen (IDN)</span><span class="sxs-lookup"><span data-stu-id="95a6f-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="95a6f-113">Nazwa wyświetlana strefy czasowej w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="95a6f-113">Time zone display name on Linux</span></span>

<span data-ttu-id="95a6f-114">Począwszy od platformy .NET 5,0, deweloperzy mają większą kontrolę nad używaną biblioteką, umożliwiając aplikacjom uniknięcie różnic między platformami.</span><span class="sxs-lookup"><span data-stu-id="95a6f-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="95a6f-115">ICU w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="95a6f-115">ICU on Windows</span></span>

<span data-ttu-id="95a6f-116">System Windows 10 maja 2019 Update i nowsze wersje zawierają [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) w ramach systemu operacyjnego, a program .NET 5,0 i nowsze wersje domyślnie używają ICU.</span><span class="sxs-lookup"><span data-stu-id="95a6f-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="95a6f-117">W przypadku uruchamiania w systemie Windows program .NET 5,0 i nowsze wersje próbują załadować `icu.dll` i, jeśli jest dostępny, użyć go do wdrożenia globalizacji.</span><span class="sxs-lookup"><span data-stu-id="95a6f-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and, if it's available, use it for the globalization implementation.</span></span> <span data-ttu-id="95a6f-118">Jeśli biblioteka ICU nie może zostać znaleziona lub załadowana, na przykład w przypadku korzystania ze starszych wersji systemu Windows, program .NET 5,0 i jego nowsze wersje powracają do implementacji opartej na witrynie NLS.</span><span class="sxs-lookup"><span data-stu-id="95a6f-118">If the ICU library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="95a6f-119">Nawet w przypadku używania ICU, `CurrentCulture` , `CurrentUICulture` i `CurrentRegion` elementy członkowskie nadal używają interfejsów API systemu operacyjnego Windows do zapamiętania ustawień użytkownika.</span><span class="sxs-lookup"><span data-stu-id="95a6f-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="use-nls-instead-of-icu"></a><span data-ttu-id="95a6f-120">Korzystanie z programu NLS zamiast ICU</span><span class="sxs-lookup"><span data-stu-id="95a6f-120">Use NLS instead of ICU</span></span>

<span data-ttu-id="95a6f-121">Użycie ICU zamiast NLS może spowodować różnice w działaniu z pewnymi operacjami związanymi z globalizacją.</span><span class="sxs-lookup"><span data-stu-id="95a6f-121">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="95a6f-122">Aby wrócić do korzystania z usługi NLS, deweloper może zrezygnować z implementacji ICU.</span><span class="sxs-lookup"><span data-stu-id="95a6f-122">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="95a6f-123">Aplikacje mogą włączać tryb NLS w dowolny z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="95a6f-123">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="95a6f-124">W pliku projektu:</span><span class="sxs-lookup"><span data-stu-id="95a6f-124">In the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="95a6f-125">W pliku `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="95a6f-125">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.UseNls": true
        }
    }
  }
  ```

- <span data-ttu-id="95a6f-126">Ustawienie zmiennej środowiskowej `DOTNET_SYSTEM_GLOBALIZATION_USENLS` na wartość `true` lub `1` .</span><span class="sxs-lookup"><span data-stu-id="95a6f-126">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="95a6f-127">Wartość ustawiona w projekcie lub w `runtimeconfig.json` pliku ma pierwszeństwo przed zmienną środowiskową.</span><span class="sxs-lookup"><span data-stu-id="95a6f-127">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="95a6f-128">Aby uzyskać więcej informacji, zobacz [Ustawienia konfiguracji w czasie wykonywania](../../core/run-time-config/globalization.md#nls).</span><span class="sxs-lookup"><span data-stu-id="95a6f-128">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="95a6f-129">ICU lokalna aplikacji</span><span class="sxs-lookup"><span data-stu-id="95a6f-129">App-local ICU</span></span>

<span data-ttu-id="95a6f-130">Każda wersja programu ICU może nastąpić wraz z poprawkami błędów IT, a także z zaktualizowanymi danymi wspólnego repozytorium danych ustawień regionalnych (CLDR), które opisują języki na całym świecie.</span><span class="sxs-lookup"><span data-stu-id="95a6f-130">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="95a6f-131">Przechodzenie między wersjami ICU może obsłużyć zachowanie aplikacji w przypadku operacji związanych z globalizacją.</span><span class="sxs-lookup"><span data-stu-id="95a6f-131">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span> <span data-ttu-id="95a6f-132">Aby pomóc deweloperom aplikacji zapewnić spójność we wszystkich wdrożeniach, .NET 5,0 i nowszych wersjach, Włącz aplikacje w systemach Windows i UNIX do przenoszenia i używania własnych kopii ICU.</span><span class="sxs-lookup"><span data-stu-id="95a6f-132">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="95a6f-133">Aplikacje mogą zrezygnować z trybu implementacji ICU na poziomie aplikacji w trybie lokalnym na jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="95a6f-133">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="95a6f-134">W pliku projektu:</span><span class="sxs-lookup"><span data-stu-id="95a6f-134">In  the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
  </ItemGroup>
  ```

- <span data-ttu-id="95a6f-135">W pliku `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="95a6f-135">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
       }
    }
  }
  ```

- <span data-ttu-id="95a6f-136">Ustawienie zmiennej środowiskowej `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` na wartość `<suffix>:<version>` lub `<version>` .</span><span class="sxs-lookup"><span data-stu-id="95a6f-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

  <span data-ttu-id="95a6f-137">`<suffix>`: Opcjonalny sufiks krótszy niż 36 znaków, zgodnie z konwencjami pakietów ICU publicznego.</span><span class="sxs-lookup"><span data-stu-id="95a6f-137">`<suffix>`: Optional suffix of fewer than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="95a6f-138">Podczas kompilowania niestandardowych ICU można dostosować je do tworzenia nazw lib i wyeksportowanych nazw symboli, aby zawierały sufiks, na przykład, `libicuucmyapp` gdzie `myapp` jest sufiksem.</span><span class="sxs-lookup"><span data-stu-id="95a6f-138">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

  <span data-ttu-id="95a6f-139">`<version>`: Prawidłowa wersja ICU, na przykład 67,1.</span><span class="sxs-lookup"><span data-stu-id="95a6f-139">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="95a6f-140">Ta wersja jest używana do ładowania plików binarnych i uzyskiwania eksportowanych symboli.</span><span class="sxs-lookup"><span data-stu-id="95a6f-140">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="95a6f-141">Aby załadować ICU w przypadku ustawienia przełącznika lokalnego aplikacji, platforma .NET używa <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> metody, która sonduje wiele ścieżek.</span><span class="sxs-lookup"><span data-stu-id="95a6f-141">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="95a6f-142">Metoda najpierw próbuje znaleźć bibliotekę we `NATIVE_DLL_SEARCH_DIRECTORIES` właściwości, która jest tworzona przez hosta dotnet w oparciu o `deps.json` plik aplikacji.</span><span class="sxs-lookup"><span data-stu-id="95a6f-142">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="95a6f-143">Aby uzyskać więcej informacji, zobacz [domyślne sondowanie](../../core/dependency-loading/default-probing.md).</span><span class="sxs-lookup"><span data-stu-id="95a6f-143">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="95a6f-144">W przypadku aplikacji, które nie są wymagane przez użytkownika, nie jest wymagana żadna specjalna akcja, inna niż upewnienie się, że ICU znajduje się w katalogu aplikacji (w przypadku aplikacji samodzielnych, domyślnie jest to katalog roboczy `NATIVE_DLL_SEARCH_DIRECTORIES` ).</span><span class="sxs-lookup"><span data-stu-id="95a6f-144">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="95a6f-145">Jeśli korzystasz z ICU za pośrednictwem pakietu NuGet, działa to w aplikacjach zależnych od platformy.</span><span class="sxs-lookup"><span data-stu-id="95a6f-145">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="95a6f-146">Pakiet NuGet rozwiązuje natywne zasoby i dołącza je do `deps.json` pliku oraz do katalogu wyjściowego dla aplikacji w `runtimes` katalogu.</span><span class="sxs-lookup"><span data-stu-id="95a6f-146">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="95a6f-147">Platforma .NET ładuje ją z tego miejsca.</span><span class="sxs-lookup"><span data-stu-id="95a6f-147">.NET loads it from there.</span></span>

<span data-ttu-id="95a6f-148">W przypadku aplikacji zależnych od platformy (nie zawartych w nich), gdzie ICU jest zużywana z lokalnej kompilacji, należy wykonać dodatkowe czynności.</span><span class="sxs-lookup"><span data-stu-id="95a6f-148">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="95a6f-149">Zestaw .NET SDK nie ma jeszcze funkcji "luźnych" natywnych plików binarnych, które mają być włączone `deps.json` (zobacz [ten problem z zestawem SDK](https://github.com/dotnet/sdk/issues/11373)).</span><span class="sxs-lookup"><span data-stu-id="95a6f-149">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="95a6f-150">Zamiast tego można je włączyć przez dodanie dodatkowych informacji do pliku projektu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="95a6f-150">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="95a6f-151">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="95a6f-151">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="95a6f-152">Należy to zrobić dla wszystkich plików binarnych ICU dla obsługiwanych środowisk uruchomieniowych.</span><span class="sxs-lookup"><span data-stu-id="95a6f-152">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="95a6f-153">Ponadto `NuGetPackageId` metadane w `RuntimeTargetsCopyLocalItems` grupie elementów muszą być zgodne z pakietem NuGet, który rzeczywiście odwołuje się do projektu.</span><span class="sxs-lookup"><span data-stu-id="95a6f-153">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="95a6f-154">zachowanie macOS</span><span class="sxs-lookup"><span data-stu-id="95a6f-154">macOS behavior</span></span>

<span data-ttu-id="95a6f-155">`macOS` Program ma inne zachowanie w zakresie rozpoznawania zależnych bibliotek dynamicznych z poleceń ładowania określonych w `match-o` pliku niż moduł ładujący systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="95a6f-155">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="95a6f-156">W module ładującym systemu Linux .NET może próbować `libicudata` , `libicuuc` i `libicui18n` (w tej kolejności), aby SPEŁNIAŁ wykres zależności ICU.</span><span class="sxs-lookup"><span data-stu-id="95a6f-156">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="95a6f-157">Jednak w macOS nie działa.</span><span class="sxs-lookup"><span data-stu-id="95a6f-157">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="95a6f-158">Podczas kompilowania ICU na macOS, domyślnie Pobierz bibliotekę dynamiczną z tymi poleceniami ładowania w `libicuuc` .</span><span class="sxs-lookup"><span data-stu-id="95a6f-158">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="95a6f-159">Poniższy fragment kodu przedstawia przykład.</span><span class="sxs-lookup"><span data-stu-id="95a6f-159">The following snippet shows an example.</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="95a6f-160">Te polecenia po prostu odwołują się do nazw bibliotek zależnych dla innych składników ICU.</span><span class="sxs-lookup"><span data-stu-id="95a6f-160">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="95a6f-161">Moduł ładujący wykonuje wyszukiwanie zgodnie z `dlopen` konwencjami, które obejmują te biblioteki w katalogach systemowych lub ustawienia `LD_LIBRARY_PATH` ENV zmiennych lub ICU w katalogu na poziomie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="95a6f-161">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="95a6f-162">Jeśli nie możesz ustawić `LD_LIBRARY_PATH` lub upewnić się, że pliki binarne ICU znajdują się w katalogu na poziomie aplikacji, musisz wykonać kilka dodatkowych czynności.</span><span class="sxs-lookup"><span data-stu-id="95a6f-162">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="95a6f-163">Istnieją pewne dyrektywy dotyczące modułu ładującego, takie jak `@loader_path` , które informują program ładujący, aby wyszukał Tę zależność w tym samym katalogu co plik binarny z tym poleceniem ładowania.</span><span class="sxs-lookup"><span data-stu-id="95a6f-163">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="95a6f-164">Istnieją dwa sposoby osiągnięcia tego celu:</span><span class="sxs-lookup"><span data-stu-id="95a6f-164">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="95a6f-165">Uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="95a6f-165">Run the following commands:</span></span>

  ```bash
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
  install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
  ```

- <span data-ttu-id="95a6f-166">Poprawka ICU do tworzenia nazw instalacji z `@loader_path`</span><span class="sxs-lookup"><span data-stu-id="95a6f-166">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="95a6f-167">Przed uruchomieniem AUTOCONF ( `./runConfigureICU` ) Zmień [następujące wiersze](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) na:</span><span class="sxs-lookup"><span data-stu-id="95a6f-167">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

  ```
  LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
  ```

## <a name="icu-on-webassembly"></a><span data-ttu-id="95a6f-168">ICU na webassembly</span><span class="sxs-lookup"><span data-stu-id="95a6f-168">ICU on WebAssembly</span></span>

<span data-ttu-id="95a6f-169">Dostępna jest wersja ICU, która jest przeznaczona dla obciążeń zestawu webassembly.</span><span class="sxs-lookup"><span data-stu-id="95a6f-169">A version of ICU is available that's specifically for WebAssembly workloads.</span></span> <span data-ttu-id="95a6f-170">Ta wersja zapewnia zgodność globalizacji z profilami pulpitu.</span><span class="sxs-lookup"><span data-stu-id="95a6f-170">This version provides globalization compatibility with desktop profiles.</span></span> <span data-ttu-id="95a6f-171">Aby zmniejszyć rozmiar pliku danych ICU z 24 MB do 1,4 MB (lub ~ 0,3 MB w przypadku kompresji z Brotli), to obciążenie ma kilku ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="95a6f-171">To reduce the ICU data file size from 24 MB to 1.4 MB (or ~0.3 MB if compressed with Brotli), this workload has a handful of limitations.</span></span>

<span data-ttu-id="95a6f-172">Następujące interfejsy API nie są obsługiwane:</span><span class="sxs-lookup"><span data-stu-id="95a6f-172">The following APIs are not supported:</span></span>

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

<span data-ttu-id="95a6f-173">Następujące interfejsy API są obsługiwane z ograniczeniami:</span><span class="sxs-lookup"><span data-stu-id="95a6f-173">The following APIs are supported with limitations:</span></span>

- <span data-ttu-id="95a6f-174"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> i <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> nie obsługują rzadko używanych <xref:System.Text.NormalizationForm.FormKC> i <xref:System.Text.NormalizationForm.FormKD> formularzy.</span><span class="sxs-lookup"><span data-stu-id="95a6f-174"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> and <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> don't support the rarely used <xref:System.Text.NormalizationForm.FormKC> and <xref:System.Text.NormalizationForm.FormKD> forms.</span></span>
- <span data-ttu-id="95a6f-175"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> zwraca tę samą wartość, co <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="95a6f-175"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> returns the same value as <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="95a6f-176">Ponadto listę obsługiwanych ustawień regionalnych można znaleźć w [repozytorium dotnet/ICU](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span><span class="sxs-lookup"><span data-stu-id="95a6f-176">In addition, a list of supported locales can be found on the [dotnet/icu repo](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span></span>
