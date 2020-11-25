---
title: 'Zmiana podziału: CA1417: atrybut unattribute for P/Invoke'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA1417.
ms.date: 09/29/2020
ms.openlocfilehash: 3316d07108ec7f9da985494413336cba6d560dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761336"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="7ec8c-103">Ostrzeżenie CA1417: atrybut unattribute for P/Invoke</span><span class="sxs-lookup"><span data-stu-id="7ec8c-103">Warning CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="7ec8c-104">Reguła analizatora kodu platformy .NET [CA1417](/visualstudio/code-quality/ca1417) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-104">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="7ec8c-105">Generuje ostrzeżenie kompilacji dla wszystkich definicji metody [wywołania platformy (P/Invoke)](../../../../standard/native-interop/pinvoke.md) , w których <xref:System.String> parametr jest przesyłany przez wartość i oznaczony przez <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="7ec8c-105">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

## <a name="change-description"></a><span data-ttu-id="7ec8c-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="7ec8c-106">Change description</span></span>

<span data-ttu-id="7ec8c-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="7ec8c-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="7ec8c-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="7ec8c-108">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="7ec8c-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="7ec8c-110">Reguły CA1417 flagi [P/Invoke](../../../../standard/native-interop/pinvoke.md) definicje metod, gdzie <xref:System.String> parametr jest oznaczony <xref:System.Runtime.InteropServices.OutAttribute> atrybutem i jest przenoszona przez wartość.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-110">Rule CA1417 flags [P/Invoke](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="7ec8c-111">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="7ec8c-111">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="7ec8c-112">Środowisko uruchomieniowe platformy .NET utrzymuje tabelę, nazywaną pulą InterNIC, która zawiera pojedyncze odwołanie do każdego unikatowego ciągu literału w programie.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-112">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="7ec8c-113">Jeśli ciąg z stażystem oznaczony jako z <xref:System.Runtime.InteropServices.OutAttribute> jest przenoszona przez wartość do metody P/Invoke, środowisko uruchomieniowe może być niestabilne.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-113">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="7ec8c-114">Aby uzyskać więcej informacji na temat informowania o ciągach, zobacz uwagi dla <xref:System.String.Intern(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7ec8c-114">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7ec8c-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="7ec8c-115">Version introduced</span></span>

<span data-ttu-id="7ec8c-116">5,0</span><span class="sxs-lookup"><span data-stu-id="7ec8c-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7ec8c-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="7ec8c-117">Recommended action</span></span>

- <span data-ttu-id="7ec8c-118">Jeśli musisz zorganizować zmodyfikowane dane ciągu z powrotem do obiektu wywołującego, Przekaż ciąg przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-118">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="7ec8c-119">Jeśli nie musisz zorganizować zmodyfikowanych danych ciągu z powrotem do obiektu wywołującego, po prostu usuń <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="7ec8c-119">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="7ec8c-120">Aby uzyskać więcej informacji, zobacz [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="7ec8c-120">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="7ec8c-121">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-121">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="7ec8c-122">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="7ec8c-122">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7ec8c-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7ec8c-123">Affected APIs</span></span>

<span data-ttu-id="7ec8c-124">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="7ec8c-124">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
