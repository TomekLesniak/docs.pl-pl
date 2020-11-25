---
title: 'Istotna zmiana: symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której projekty nie definiują już symboli preprocesora dla wcześniejszych wersji.
ms.date: 09/17/2020
ms.openlocfilehash: 61a5e4fce258d2be3d584318e154bb752b88ebe1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761452"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="6b2f6-103">Symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5</span><span class="sxs-lookup"><span data-stu-id="6b2f6-103">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="6b2f6-104">W programie .NET 5,0 RC2 i nowszych wersjach projekty nie definiują już symboli preprocesora dla wcześniejszych wersji, ale tylko dla wersji docelowej.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-104">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="6b2f6-105">Jest to takie samo zachowanie jak .NET Core 1,0-3,1.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-105">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6b2f6-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="6b2f6-106">Version introduced</span></span>

<span data-ttu-id="6b2f6-107">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="6b2f6-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="6b2f6-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="6b2f6-108">Change description</span></span>

<span data-ttu-id="6b2f6-109">W programie .NET 5,0 w wersji zapoznawczej 7 do RC1, projekty, dla których `net5.0` zdefiniowano zarówno `NETCOREAPP3_1` `NET5_0` symbole preprocesora, jak i.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-109">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="6b2f6-110">Zamiarem tej zmiany zachowania było rozpoczęcie od platformy .NET 5,0, a warunkowe [symbole kompilacji byłyby skumulowane](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="6b2f6-110">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="6b2f6-111">W programie .NET 5,0 RC2 lub nowszym projekty definiują tylko symbole dla monikerów platformy docelowej (TFM), które są przeznaczone dla wszystkich wcześniejszych wersji.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-111">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6b2f6-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="6b2f6-112">Reason for change</span></span>

<span data-ttu-id="6b2f6-113">Zmiana z wersji zapoznawczej 7 została przywrócona ze względu na Opinie klientów.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-113">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="6b2f6-114">Definiowanie symboli dla wcześniejszych wersji jest zaskoczenie i pomylić klientów, a niektóre założono, że była usterką w kompilatorze języka C#.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-114">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6b2f6-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="6b2f6-115">Recommended action</span></span>

<span data-ttu-id="6b2f6-116">Upewnij się, że `#if` logika nie założono, że `NETCOREAPP3_1` jest zdefiniowana, gdy projekt jest `net5.0` lub wyższy.</span><span class="sxs-lookup"><span data-stu-id="6b2f6-116">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="6b2f6-117">Zamiast tego przyjmuje się, że `NETCOREAPP3_1` jest on definiowany tylko wtedy, gdy projekt jest jawnie obiekt docelowy `netcoreapp3.1` .</span><span class="sxs-lookup"><span data-stu-id="6b2f6-117">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="6b2f6-118">Na przykład jeśli projekt jest przeznaczony dla platformy .NET Core 2,1 i .NET Core 3,1 i interfejsy API, które zostały wprowadzone w programie .NET Core 3,1, `#if` logika powinna wyglądać w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6b2f6-118">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a><span data-ttu-id="6b2f6-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6b2f6-119">Affected APIs</span></span>

<span data-ttu-id="6b2f6-120">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="6b2f6-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
