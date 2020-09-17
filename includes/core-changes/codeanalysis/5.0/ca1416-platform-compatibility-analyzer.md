---
ms.openlocfilehash: cd7860a5dfff1eb595625665382689733cffc94a
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90721239"
---
### <a name="ca1416-platform-compatibility"></a><span data-ttu-id="eb621-101">CA1416: zgodność platformy</span><span class="sxs-lookup"><span data-stu-id="eb621-101">CA1416: Platform compatibility</span></span>

<span data-ttu-id="eb621-102">Reguła analizatora kodu platformy .NET [CA1416](/visualstudio/code-quality/ca1416) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="eb621-102">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="eb621-103">Generuje ostrzeżenie kompilacji dla wywołań interfejsów API specyficznych dla platformy z lokacji wywołań, które nie weryfikują systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="eb621-103">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eb621-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="eb621-104">Change description</span></span>

<span data-ttu-id="eb621-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="eb621-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="eb621-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA1416](/visualstudio/code-quality/ca1416).</span><span class="sxs-lookup"><span data-stu-id="eb621-106">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="eb621-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="eb621-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="eb621-108">Reguła CA1416 informuje użytkownika, gdy korzystasz z interfejsów API specyficznych dla platformy z miejsc, w których kontekst platformy nie został zweryfikowany.</span><span class="sxs-lookup"><span data-stu-id="eb621-108">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="eb621-109">[CA1416](/visualstudio/code-quality/ca1416)reguły, Analizator zgodności platformy, umożliwia dostęp do innych funkcji, które są nowe w programie .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="eb621-109">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="eb621-110">W programie .NET 5,0 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> wprowadzono <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> funkcję i, która pozwala określić platformy, na których interfejs API *jest* lub *nie* jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="eb621-110">.NET 5.0 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="eb621-111">W przypadku braku tych atrybutów przyjmuje się, że interfejs API jest obsługiwany na wszystkich platformach.</span><span class="sxs-lookup"><span data-stu-id="eb621-111">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="eb621-112">Te atrybuty zostały zastosowane do interfejsów API specyficznych dla platformy w podstawowych bibliotekach platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="eb621-112">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="eb621-113">W projektach przeznaczonych dla platform, dla których używane interfejsy API są niedostępne, reguła [CA1416](/visualstudio/code-quality/ca1416) flaguje każde wywołanie interfejsu API specyficzne dla platformy, w którym nie zweryfikowano kontekstu platformy.</span><span class="sxs-lookup"><span data-stu-id="eb621-113">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="eb621-114">Większość interfejsów API, które są teraz uzupełnione <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> atrybutami i generują <xref:System.PlatformNotSupportedException> wyjątki, gdy są wywoływane w nieobsługiwanym systemie operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="eb621-114">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="eb621-115">Teraz, gdy te interfejsy API są oznaczone jako specyficzne dla platformy, reguła [CA1416a](/visualstudio/code-quality/ca1416) pomaga zapobiegać <xref:System.PlatformNotSupportedException> wyjątkom w czasie wykonywania, DODAJĄC sprawdzenia systemu operacyjnego do witryn wywołań.</span><span class="sxs-lookup"><span data-stu-id="eb621-115">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

#### <a name="examples"></a><span data-ttu-id="eb621-116">Przykłady</span><span class="sxs-lookup"><span data-stu-id="eb621-116">Examples</span></span>

- <span data-ttu-id="eb621-117"><xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType>Metoda jest obsługiwana tylko w systemie Windows (z systemem `[SupportedOSPlatform("windows")]` ).</span><span class="sxs-lookup"><span data-stu-id="eb621-117">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows (it's decorated with `[SupportedOSPlatform("windows")]`).</span></span> <span data-ttu-id="eb621-118">Poniższy kod generuje ostrzeżenie CA1416 w czasie kompilacji, jeśli [obiekt docelowy](../../../../docs/standard/frameworks.md) projektu `net5.0` (ale nie `net5.0-windows` ).</span><span class="sxs-lookup"><span data-stu-id="eb621-118">The following code will produce a CA1416 warning at build time if the project [targets](../../../../docs/standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="eb621-119">W przypadku akcji, które można wykonać, aby uniknąć tego ostrzeżenia, zobacz [zalecane działanie](#recommended-action).</span><span class="sxs-lookup"><span data-stu-id="eb621-119">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="eb621-120"><xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType>Metoda nie jest obsługiwana w przeglądarce (jest dekoracyjna `[UnsupportedOSPlatform("browser")]` ).</span><span class="sxs-lookup"><span data-stu-id="eb621-120">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser (it's decorated with `[UnsupportedOSPlatform("browser")]`).</span></span> <span data-ttu-id="eb621-121">Poniższy kod generuje ostrzeżenie CA1416 w czasie kompilacji, jeśli projekt używa zestawu webassembly Blazor ( `<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">` ) lub zawiera `browser` jako obsługiwaną platformę ( `<SupportedPlatform Include="browser" />` ) w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="eb621-121">The following code will produce a CA1416 warning at build time if the project uses the Blazor WebAssembly SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) or includes `browser` as a supported platform (`<SupportedPlatform Include="browser" />`) in the project file.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a><span data-ttu-id="eb621-122">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="eb621-122">Version introduced</span></span>

<span data-ttu-id="eb621-123">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="eb621-123">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eb621-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="eb621-124">Recommended action</span></span>

<span data-ttu-id="eb621-125">Upewnij się, że interfejsy API specyficzne dla platformy są wywoływane tylko wtedy, gdy kod jest uruchomiony na odpowiedniej platformie.</span><span class="sxs-lookup"><span data-stu-id="eb621-125">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="eb621-126">`Is<Platform>` <xref:System.OperatingSystem?displayProperty=nameWithType> <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> Przed wywołaniem interfejsu API specyficznego dla platformy można sprawdzić bieżący system operacyjny przy użyciu jednej z metod w klasie.</span><span class="sxs-lookup"><span data-stu-id="eb621-126">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="eb621-127">Można użyć jednej z `Is<Platform>` metod w warunku `if` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="eb621-127">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="eb621-128">Lub, jeśli nie chcesz obciążać dodatkowej `if` instrukcji w czasie wykonywania, <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> zamiast tego wywołaj:</span><span class="sxs-lookup"><span data-stu-id="eb621-128">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="eb621-129">Możesz również oznaczyć interfejs API jako specyficzny dla platformy, w którym to przypadku obciążenie wymagające sprawdzenia wymagań znajduje się w obiektach wywołujących.</span><span class="sxs-lookup"><span data-stu-id="eb621-129">You can also mark your API as platform-specific, in which case the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="eb621-130">Można oznaczyć konkretne metody lub typy lub cały zestaw.</span><span class="sxs-lookup"><span data-stu-id="eb621-130">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="eb621-131">Jeśli nie chcesz naprawić wszystkich witryn wywołań, możesz wybrać jedną z następujących opcji, aby pominąć ostrzeżenie:</span><span class="sxs-lookup"><span data-stu-id="eb621-131">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="eb621-132">Aby pominąć regułę CA1416, można to zrobić za pomocą `#pragma` flagi kompilatora lub z flagą [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) lub ustawiając [ważność reguły](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) do `none` w pliku. editorconfig.</span><span class="sxs-lookup"><span data-stu-id="eb621-132">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="eb621-133">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="eb621-133">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="eb621-134">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="eb621-134">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="eb621-135">Kategoria</span><span class="sxs-lookup"><span data-stu-id="eb621-135">Category</span></span>

- <span data-ttu-id="eb621-136">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="eb621-136">Code analysis</span></span>
- <span data-ttu-id="eb621-137">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="eb621-137">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eb621-138">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="eb621-138">Affected APIs</span></span>

<span data-ttu-id="eb621-139">Platforma systemu Windows:</span><span class="sxs-lookup"><span data-stu-id="eb621-139">For Windows platform:</span></span>

- <span data-ttu-id="eb621-140">Wszystkie interfejsy API wymienione w <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md> .</span><span class="sxs-lookup"><span data-stu-id="eb621-140">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="eb621-141">Na platformie Blazor webassembly:</span><span class="sxs-lookup"><span data-stu-id="eb621-141">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="eb621-142">Wszystkie interfejsy API wymienione w <https://github.com/dotnet/runtime/issues/41087> .</span><span class="sxs-lookup"><span data-stu-id="eb621-142">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a><span data-ttu-id="eb621-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eb621-143">See also</span></span>

- [<span data-ttu-id="eb621-144">CA1416: Weryfikowanie zgodności platformy</span><span class="sxs-lookup"><span data-stu-id="eb621-144">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="eb621-145">Analizator interfejsów API platformy .NET</span><span class="sxs-lookup"><span data-stu-id="eb621-145">.NET API analyzer</span></span>](../../../../docs/standard/analyzers/api-analyzer.md)
