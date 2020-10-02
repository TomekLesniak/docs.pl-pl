---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654744"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="74774-101">Symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5</span><span class="sxs-lookup"><span data-stu-id="74774-101">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="74774-102">W programie .NET 5,0 RC2 i nowszych wersjach projekty nie definiują już symboli preprocesora dla wcześniejszych wersji, ale tylko dla wersji docelowej.</span><span class="sxs-lookup"><span data-stu-id="74774-102">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="74774-103">Jest to takie samo zachowanie jak .NET Core 1,0-3,1.</span><span class="sxs-lookup"><span data-stu-id="74774-103">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="74774-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="74774-104">Version introduced</span></span>

<span data-ttu-id="74774-105">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="74774-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="74774-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="74774-106">Change description</span></span>

<span data-ttu-id="74774-107">W programie .NET 5,0 w wersji zapoznawczej 7 do RC1, projekty, dla których `net5.0` zdefiniowano zarówno `NETCOREAPP3_1` `NET5_0` symbole preprocesora, jak i.</span><span class="sxs-lookup"><span data-stu-id="74774-107">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="74774-108">Zamiarem tej zmiany zachowania było rozpoczęcie od platformy .NET 5,0, a warunkowe [symbole kompilacji byłyby skumulowane](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="74774-108">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="74774-109">W programie .NET 5,0 RC2 lub nowszym projekty definiują tylko symbole dla monikerów platformy docelowej (TFM), które są przeznaczone dla wszystkich wcześniejszych wersji.</span><span class="sxs-lookup"><span data-stu-id="74774-109">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="74774-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="74774-110">Reason for change</span></span>

<span data-ttu-id="74774-111">Zmiana z wersji zapoznawczej 7 została przywrócona ze względu na Opinie klientów.</span><span class="sxs-lookup"><span data-stu-id="74774-111">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="74774-112">Definiowanie symboli dla wcześniejszych wersji jest zaskoczenie i pomylić klientów, a niektóre założono, że była usterką w kompilatorze języka C#.</span><span class="sxs-lookup"><span data-stu-id="74774-112">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="74774-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="74774-113">Recommended action</span></span>

<span data-ttu-id="74774-114">Upewnij się, że `#if` logika nie założono, że `NETCOREAPP3_1` jest zdefiniowana, gdy projekt jest `net5.0` lub wyższy.</span><span class="sxs-lookup"><span data-stu-id="74774-114">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="74774-115">Zamiast tego przyjmuje się, że `NETCOREAPP3_1` jest on definiowany tylko wtedy, gdy projekt jest jawnie obiekt docelowy `netcoreapp3.1` .</span><span class="sxs-lookup"><span data-stu-id="74774-115">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="74774-116">Na przykład jeśli projekt jest przeznaczony dla platformy .NET Core 2,1 i .NET Core 3,1 i interfejsy API, które zostały wprowadzone w programie .NET Core 3,1, `#if` logika powinna wyglądać w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="74774-116">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a><span data-ttu-id="74774-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="74774-117">Category</span></span>

<span data-ttu-id="74774-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="74774-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74774-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="74774-119">Affected APIs</span></span>

<span data-ttu-id="74774-120">Brak</span><span class="sxs-lookup"><span data-stu-id="74774-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
