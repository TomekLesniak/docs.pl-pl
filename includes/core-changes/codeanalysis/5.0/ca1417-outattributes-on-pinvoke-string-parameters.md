---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065170"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="9f2f7-101">CA1417: atrybut unattribute dla parametru String dla elementu P/Invoke</span><span class="sxs-lookup"><span data-stu-id="9f2f7-101">CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="9f2f7-102">Reguła analizatora kodu platformy .NET [CA1417](/visualstudio/code-quality/ca1417) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-102">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="9f2f7-103">Generuje ostrzeżenie kompilacji dla wszystkich definicji metody [wywołania platformy (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) , w których <xref:System.String> parametr jest przesyłany przez wartość i oznaczony przez <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="9f2f7-103">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9f2f7-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="9f2f7-104">Change description</span></span>

<span data-ttu-id="9f2f7-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="9f2f7-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="9f2f7-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="9f2f7-106">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="9f2f7-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="9f2f7-108">Reguły CA1417 flagi [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) definicje metod, gdzie <xref:System.String> parametr jest oznaczony <xref:System.Runtime.InteropServices.OutAttribute> atrybutem i jest przenoszona przez wartość.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-108">Rule CA1417 flags [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="9f2f7-109">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="9f2f7-109">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="9f2f7-110">Środowisko uruchomieniowe platformy .NET utrzymuje tabelę, nazywaną pulą InterNIC, która zawiera pojedyncze odwołanie do każdego unikatowego ciągu literału w programie.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-110">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="9f2f7-111">Jeśli ciąg z stażystem oznaczony jako z <xref:System.Runtime.InteropServices.OutAttribute> jest przenoszona przez wartość do metody P/Invoke, środowisko uruchomieniowe może być niestabilne.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-111">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="9f2f7-112">Aby uzyskać więcej informacji na temat informowania o ciągach, zobacz uwagi dla <xref:System.String.Intern(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9f2f7-112">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9f2f7-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9f2f7-113">Version introduced</span></span>

<span data-ttu-id="9f2f7-114">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="9f2f7-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9f2f7-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9f2f7-115">Recommended action</span></span>

- <span data-ttu-id="9f2f7-116">Jeśli musisz zorganizować zmodyfikowane dane ciągu z powrotem do obiektu wywołującego, Przekaż ciąg przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-116">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="9f2f7-117">Jeśli nie musisz zorganizować zmodyfikowanych danych ciągu z powrotem do obiektu wywołującego, po prostu usuń <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="9f2f7-117">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="9f2f7-118">Aby uzyskać więcej informacji, zobacz [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="9f2f7-118">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="9f2f7-119">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-119">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="9f2f7-120">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="9f2f7-120">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="9f2f7-121">Kategoria</span><span class="sxs-lookup"><span data-stu-id="9f2f7-121">Category</span></span>

<span data-ttu-id="9f2f7-122">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="9f2f7-122">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9f2f7-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9f2f7-123">Affected APIs</span></span>

<span data-ttu-id="9f2f7-124">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="9f2f7-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
