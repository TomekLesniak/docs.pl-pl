---
title: Analizatory kodu dla .NET Framework
titleSuffix: ''
description: Dowiedz się, jak używać analizatorów w pakiecie .NET Framework analizatorów, aby znajdować i rozwiązywać problemy w kodzie.
author: billwagner
ms.author: wiwagn
ms.date: 10/23/2020
ms.openlocfilehash: 69dfbc9f9645c7f602ffbce46308b241c119fd96
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687904"
---
# <a name="code-analysis"></a><span data-ttu-id="96004-103">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="96004-103">Code analysis</span></span>

<span data-ttu-id="96004-104">Analizatorów kodu można użyć, aby znaleźć potencjalne problemy w .NET Framework kodzie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="96004-104">You can use code analyzers to find potential issues in your .NET Framework application code.</span></span> <span data-ttu-id="96004-105">Analizatory wyszukują potencjalne problemy i sugerują dla nich poprawki.</span><span class="sxs-lookup"><span data-stu-id="96004-105">The analyzers find potential issues and suggest fixes for them.</span></span>

<span data-ttu-id="96004-106">Analizatory kodu oparte na Roslyn działają interaktywnie w programie Visual Studio podczas pisania kodu lub jako część kompilacji elementu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="96004-106">Roslyn-based code analyzers run interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="96004-107">Analizatory należy dodać do projektu tak szybko, jak to możliwe w cyklu programowania.</span><span class="sxs-lookup"><span data-stu-id="96004-107">You should add the analyzers to your project as early as possible in the development cycle.</span></span> <span data-ttu-id="96004-108">Wkrótce znajdziesz ewentualne potencjalne problemy w kodzie, tym łatwiejsze jest ich naprawa.</span><span class="sxs-lookup"><span data-stu-id="96004-108">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="96004-109">Analizatory sprawdzają problemy w istniejącym kodzie i ostrzegają o nowych problemach podczas dalszej pracy.</span><span class="sxs-lookup"><span data-stu-id="96004-109">The analyzers flag issues in existing code and warn about new issues as you continue development.</span></span>

## <a name="install-and-configure-analyzers"></a><span data-ttu-id="96004-110">Instalowanie i Konfigurowanie analizatorów</span><span class="sxs-lookup"><span data-stu-id="96004-110">Install and configure analyzers</span></span>

<span data-ttu-id="96004-111">Analizator .NET Framework jest dostarczany w pakiecie NuGet [Microsoft. NETFramework. analizators](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) .</span><span class="sxs-lookup"><span data-stu-id="96004-111">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="96004-112">Ten pakiet udostępnia analizatory charakterystyczne dla .NET Framework interfejsów API, które obejmują analizatory zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="96004-112">This package provides analyzers that are specific to .NET Framework APIs, which includes security analyzers.</span></span> <span data-ttu-id="96004-113">Pakiet jest dostarczany z [pakietem Microsoft. CodeAnalysis. FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers), dlatego w przypadku zainstalowania tego pakietu nie trzeba oddzielnie instalować .NET Framework analizatorów.</span><span class="sxs-lookup"><span data-stu-id="96004-113">The package is included with the [Microsoft.CodeAnalysis.FxCopAnalyzers package](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers), so if you install that package, there's no need to install the .NET Framework analyzers separately.</span></span>

<span data-ttu-id="96004-114">Zainstaluj pakiet NuGet na każdym projekcie, w którym mają być uruchamiane analizatory.</span><span class="sxs-lookup"><span data-stu-id="96004-114">Install the NuGet package on every project where you want the analyzers to run.</span></span> <span data-ttu-id="96004-115">Tylko jeden Deweloper musi dodać je do projektu.</span><span class="sxs-lookup"><span data-stu-id="96004-115">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="96004-116">Pakiet analizatora jest zależnością projektu i będzie działać na każdym komputerze dewelopera, gdy ma zaktualizowane rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="96004-116">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="96004-117">Aby zainstalować pakiet, kliknij prawym przyciskiem myszy projekt i wybierz polecenie "Zarządzaj zależnościami".</span><span class="sxs-lookup"><span data-stu-id="96004-117">To install the package, right-click on the project, and select "Manage Dependencies".</span></span> <span data-ttu-id="96004-118">W Eksploratorze NuGet Wyszukaj ciąg "Microsoft. NetFramework. analizatory".</span><span class="sxs-lookup"><span data-stu-id="96004-118">From the NuGet explorer, search for "Microsoft.NetFramework.Analyzers".</span></span> <span data-ttu-id="96004-119">Zainstaluj najnowszą stabilną wersję we wszystkich projektach w rozwiązaniu.</span><span class="sxs-lookup"><span data-stu-id="96004-119">Install the latest stable version in all projects in your solution.</span></span>

## <a name="use-the-analyzers"></a><span data-ttu-id="96004-120">Korzystanie z analizatorów</span><span class="sxs-lookup"><span data-stu-id="96004-120">Use the analyzers</span></span>

<span data-ttu-id="96004-121">Po zainstalowaniu pakietu NuGet Skompiluj rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="96004-121">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="96004-122">Analizator zgłosi wszelkie problemy, które znajdują się w bazie kodu.</span><span class="sxs-lookup"><span data-stu-id="96004-122">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="96004-123">Problemy są raportowane jako ostrzeżenia w oknie Lista błędów programu Visual Studio, jak pokazano na poniższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="96004-123">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![Problemy zgłoszone przez analizatory .NET Framework.](./media/framework-analyzers-2.png)

<span data-ttu-id="96004-125">Podczas pisania kodu zobaczysz zygzaki poniżej dowolnego potencjalnego problemu w kodzie.</span><span class="sxs-lookup"><span data-stu-id="96004-125">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="96004-126">Umieść wskaźnik myszy nad dowolnym problemem, aby uzyskać więcej informacji, i zapoznaj się z sugestiami dotyczącymi ewentualnych poprawek, jak pokazano na poniższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="96004-126">Hover over any issue to get more information and see suggestions for any possible fix, as shown in the following image:</span></span>

![Interaktywny raport dotyczący problemów znalezionych przez analizatory kodu.](./media/framework-analyzers-1.png)

<span data-ttu-id="96004-128">Aby uzyskać więcej informacji, zobacz [Analiza kodu w programie Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview).</span><span class="sxs-lookup"><span data-stu-id="96004-128">For more information, see [Code analysis in Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview).</span></span>

## <a name="types-of-rules"></a><span data-ttu-id="96004-129">Typy reguł</span><span class="sxs-lookup"><span data-stu-id="96004-129">Types of rules</span></span>

<span data-ttu-id="96004-130">Analizatory badają kod w rozwiązaniu i ostrzeżenia powierzchni z `CA` prefiksem.</span><span class="sxs-lookup"><span data-stu-id="96004-130">The analyzers examine the code in your solution and surface warnings with a `CA` prefix.</span></span> <span data-ttu-id="96004-131">Aby uzyskać listę wszystkich możliwych ostrzeżeń, zobacz [reguły jakości kodu](../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="96004-131">For a list of all possible warnings, see [Code quality rules](../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="96004-132">Tylko niektóre z tych ostrzeżeń mają zastosowanie do .NET Framework interfejsów API, w tym:</span><span class="sxs-lookup"><span data-stu-id="96004-132">Only some of these warnings apply to .NET Framework APIS, including:</span></span>

- [<span data-ttu-id="96004-133">CA1058: Typy nie powinny rozszerzać niektórych typów podstawowych</span><span class="sxs-lookup"><span data-stu-id="96004-133">CA1058: Types should not extend certain base types</span></span>](../fundamentals/code-analysis/quality-rules/ca1058.md)

- [<span data-ttu-id="96004-134">CA2153: nie Przechwytuj wyjątków uszkodzonych Stanów</span><span class="sxs-lookup"><span data-stu-id="96004-134">CA2153: Do not catch corrupted state exceptions</span></span>](../fundamentals/code-analysis/quality-rules/ca2153.md)

- [<span data-ttu-id="96004-135">CA2229: Zaimplementuj konstruktory serializacji</span><span class="sxs-lookup"><span data-stu-id="96004-135">CA2229: Implement serialization constructors</span></span>](../fundamentals/code-analysis/quality-rules/ca2229.md)

- [<span data-ttu-id="96004-136">CA2235: Oznacz wszystkie pola nieprzeznaczone do serializacji</span><span class="sxs-lookup"><span data-stu-id="96004-136">CA2235: Mark all non-serializable fields</span></span>](../fundamentals/code-analysis/quality-rules/ca2235.md)

- [<span data-ttu-id="96004-137">CA2237: Oznacz typy ISerializable z możliwością serializacji</span><span class="sxs-lookup"><span data-stu-id="96004-137">CA2237: Mark ISerializable types with serializable</span></span>](../fundamentals/code-analysis/quality-rules/ca2237.md)

- [<span data-ttu-id="96004-138">CA3075: niezabezpieczone przetwarzanie DTD w kodzie XML</span><span class="sxs-lookup"><span data-stu-id="96004-138">CA3075: Insecure DTD processing in XML</span></span>](../fundamentals/code-analysis/quality-rules/ca3075.md)

- [<span data-ttu-id="96004-139">CA5350: nie używaj słabych algorytmów kryptograficznych</span><span class="sxs-lookup"><span data-stu-id="96004-139">CA5350: Do not use weak cryptographic algorithms</span></span>](../fundamentals/code-analysis/quality-rules/ca5350.md)

- [<span data-ttu-id="96004-140">CA5351 nie używają uszkodzonych algorytmów kryptograficznych</span><span class="sxs-lookup"><span data-stu-id="96004-140">CA5351 Do not use broken cryptographic algorithms</span></span>](../fundamentals/code-analysis/quality-rules/ca5351.md)

## <a name="see-also"></a><span data-ttu-id="96004-141">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="96004-141">See also</span></span>

- [<span data-ttu-id="96004-142">Analiza kodu w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96004-142">Code analysis in Visual Studio</span></span>](/visualstudio/code-quality/roslyn-analyzers-overview)
- [<span data-ttu-id="96004-143">Analiza kodu w zestawie SDK platformy .NET</span><span class="sxs-lookup"><span data-stu-id="96004-143">Code analysis in the .NET SDK</span></span>](../fundamentals/code-analysis/overview.md)
