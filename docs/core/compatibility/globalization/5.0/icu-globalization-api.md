---
title: 'Istotna zmiana: interfejsy API globalizacji używają bibliotek ICU w systemie Windows'
description: Dowiedz się więcej na temat istotnej zmiany globalizacji w programie .NET 5,0, gdzie biblioteki ICU są używane na potrzeby funkcji globalizacji zamiast programu NLS.
ms.date: 05/19/2020
ms.openlocfilehash: efc20e21969ea4a83c9122e40b262e1dc38e6770
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761707"
---
# <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="a4b94-103">Interfejsy API globalizacji korzystają z bibliotek ICU w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="a4b94-103">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="a4b94-104">.NET 5,0 i nowsze wersje używają [międzynarodowych składników dla bibliotek Unicode (ICU)](http://site.icu-project.org/home) do obsługi funkcji globalizacji w przypadku uruchamiania w systemie Windows 10 maja 2019 Update lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="a4b94-104">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

## <a name="change-description"></a><span data-ttu-id="a4b94-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a4b94-105">Change description</span></span>

<span data-ttu-id="a4b94-106">W przypadku oprogramowania .NET Core 1,0-3,1 i .NET Framework 4 i nowszych biblioteki platformy .NET używają interfejsów API [obsługi języków (NLS)](/windows/win32/intl/national-language-support) dla funkcji globalizacji w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="a4b94-106">In .NET Core 1.0 - 3.1 and .NET Framework 4 and later, .NET libraries use [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality on Windows.</span></span> <span data-ttu-id="a4b94-107">Na przykład funkcje NLS były używane do porównywania ciągów, uzyskiwania informacji o kulturze i wykonywania wielkich liter w odpowiedniej kulturze.</span><span class="sxs-lookup"><span data-stu-id="a4b94-107">For example, NLS functions were used to compare strings, get culture information, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="a4b94-108">Począwszy od platformy .NET 5,0, jeśli aplikacja jest uruchomiona w systemie Windows 10 maja 2019 Update lub nowszym, biblioteki platformy .NET domyślnie używają interfejsów API [ICU](http://site.icu-project.org/home) globalizacji.</span><span class="sxs-lookup"><span data-stu-id="a4b94-108">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs, by default.</span></span>

> [!NOTE]
> <span data-ttu-id="a4b94-109">System Windows 10 maja 2019 Update i nowsze wersje są dostarczane z natywną biblioteką ICU.</span><span class="sxs-lookup"><span data-stu-id="a4b94-109">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="a4b94-110">Jeśli środowisko uruchomieniowe platformy .NET nie może załadować ICU, zamiast tego używa środowiska NLS.</span><span class="sxs-lookup"><span data-stu-id="a4b94-110">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="a4b94-111">Różnice w zachowaniu</span><span class="sxs-lookup"><span data-stu-id="a4b94-111">Behavioral differences</span></span>

<span data-ttu-id="a4b94-112">Zmiany w aplikacji mogą być widoczne nawet wtedy, gdy nie są używane funkcje globalizacji.</span><span class="sxs-lookup"><span data-stu-id="a4b94-112">You might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="a4b94-113">Ta sekcja zawiera kilka zmian w zachowaniu, które mogą się pojawić, ale również inne.</span><span class="sxs-lookup"><span data-stu-id="a4b94-113">This section lists a couple of the behavioral changes you might see, but there are others too.</span></span>

### <a name="stringindexof"></a><span data-ttu-id="a4b94-114">String. IndexOf</span><span class="sxs-lookup"><span data-stu-id="a4b94-114">String.IndexOf</span></span>

<span data-ttu-id="a4b94-115">Rozważmy następujący kod, który wywołuje, <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> Aby znaleźć indeks znaku nowego wiersza w ciągu.</span><span class="sxs-lookup"><span data-stu-id="a4b94-115">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="a4b94-116">W poprzednich wersjach programu .NET w systemie Windows, fragment kodu drukuje `6` .</span><span class="sxs-lookup"><span data-stu-id="a4b94-116">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="a4b94-117">W przypadku programu .NET 5,0 i jego nowszych wersji w systemie Windows 19H1 i nowszych wersjach fragment zostanie wydrukowany `-1` .</span><span class="sxs-lookup"><span data-stu-id="a4b94-117">In .NET 5.0 and later versions on Windows 19H1 and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="a4b94-118">Aby naprawić ten kod, przeprowadź wyszukiwanie porządkowe zamiast wyszukiwania z uwzględnieniem kultury, wywołaj <xref:System.String.IndexOf(System.String,System.StringComparison)> Przeciążenie i przekaż <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> jako argument.</span><span class="sxs-lookup"><span data-stu-id="a4b94-118">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="a4b94-119">Można uruchamiać reguły analizy kodu [CA1307: Określ StringComparison dla przejrzystości](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) i [CA1309: Użyj StringComparison porządkowej](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) , aby znaleźć te lokacje wywołań w kodzie.</span><span class="sxs-lookup"><span data-stu-id="a4b94-119">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="a4b94-120">Aby uzyskać więcej informacji, zobacz temat [zachowanie zmian w przypadku porównywania ciągów w programie .NET 5](../../../../standard/base-types/string-comparison-net-5-plus.md)lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="a4b94-120">For more information, see [Behavior changes when comparing strings on .NET 5+](../../../../standard/base-types/string-comparison-net-5-plus.md).</span></span>

### <a name="currency-symbol"></a><span data-ttu-id="a4b94-121">Symbol waluty</span><span class="sxs-lookup"><span data-stu-id="a4b94-121">Currency symbol</span></span>

<span data-ttu-id="a4b94-122">Rozważmy następujący kod, który sformatuje ciąg przy użyciu specyfikatora formatu waluty `C` .</span><span class="sxs-lookup"><span data-stu-id="a4b94-122">Consider the following code that formats a string using the currency format specifier `C`.</span></span> <span data-ttu-id="a4b94-123">Kultura bieżącego wątku jest ustawiona na kulturę, która zawiera tylko język, a nie kraj.</span><span class="sxs-lookup"><span data-stu-id="a4b94-123">The current thread's culture is set to a culture that includes only the language and not the country.</span></span>

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- <span data-ttu-id="a4b94-124">W poprzednich wersjach programu .NET w systemie Windows wartością tekstową jest `"100,00 €"` .</span><span class="sxs-lookup"><span data-stu-id="a4b94-124">In previous versions of .NET on Windows, the value of text is `"100,00 €"`.</span></span>
- <span data-ttu-id="a4b94-125">W programie .NET 5,0 i nowszych wersjach w systemie Windows 19H1 i nowszych wersjach wartość tekst to `"100,00 ¤"` , która używa symbolu waluty międzynarodowej zamiast euro.</span><span class="sxs-lookup"><span data-stu-id="a4b94-125">In .NET 5.0 and later versions on Windows 19H1 and later versions, the value of text is `"100,00 ¤"`, which uses the international currency symbol instead of the euro.</span></span> <span data-ttu-id="a4b94-126">W ICU projekt jest, że walutą jest właściwość kraju lub regionu, a nie język.</span><span class="sxs-lookup"><span data-stu-id="a4b94-126">In ICU, the design is that a currency is a property of a country or region, not a language.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a4b94-127">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a4b94-127">Reason for change</span></span>

<span data-ttu-id="a4b94-128">Ta zmiana została wprowadzona w celu ujednolicenia. Zachowanie globalizacji sieci we wszystkich obsługiwanych systemach operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="a4b94-128">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="a4b94-129">Zapewnia również możliwość tworzenia przez aplikacje własnych bibliotek globalizacji, a nie zależą od bibliotek wbudowanych systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a4b94-129">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the operating system's built-in libraries.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a4b94-130">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a4b94-130">Version introduced</span></span>

<span data-ttu-id="a4b94-131">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a4b94-131">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a4b94-132">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a4b94-132">Recommended action</span></span>

<span data-ttu-id="a4b94-133">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="a4b94-133">No action is required on the part of the developer.</span></span> <span data-ttu-id="a4b94-134">Jeśli jednak chcesz kontynuować korzystanie z interfejsów API globalizacji NLS, możesz ustawić [przełącznik czasu wykonywania](../../../run-time-config/globalization.md#nls) w celu przywrócenia tego zachowania.</span><span class="sxs-lookup"><span data-stu-id="a4b94-134">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="a4b94-135">Aby uzyskać więcej informacji na temat dostępnych przełączników, zobacz artykuł [globalizacja i ICU platformy .NET](../../../../standard/globalization-localization/globalization-icu.md) .</span><span class="sxs-lookup"><span data-stu-id="a4b94-135">For more information about the available switches, see the [.NET globalization and ICU](../../../../standard/globalization-localization/globalization-icu.md) article.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a4b94-136">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a4b94-136">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="a4b94-137">Większość typów w <xref:System.Globalization?displayProperty=fullName> przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="a4b94-137">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>
- <span data-ttu-id="a4b94-138"><xref:System.Array.Sort%2A?displayProperty=fullName> (podczas sortowania tablicy ciągów)</span><span class="sxs-lookup"><span data-stu-id="a4b94-138"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting an array of strings)</span></span>
- <span data-ttu-id="a4b94-139"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (gdy elementy listy są ciągami)</span><span class="sxs-lookup"><span data-stu-id="a4b94-139"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="a4b94-140"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (gdy klucze są ciągami)</span><span class="sxs-lookup"><span data-stu-id="a4b94-140"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="a4b94-141"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (gdy klucze są ciągami)</span><span class="sxs-lookup"><span data-stu-id="a4b94-141"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="a4b94-142"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (gdy zestaw zawiera ciągi)</span><span class="sxs-lookup"><span data-stu-id="a4b94-142"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

<!--

### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

### Category

- Core .NET libraries
- Globalization

-->
