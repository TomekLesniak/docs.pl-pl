---
title: 'Zmiana podziału: wartość domyślna ActivityIdFormat jest W3C'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w podstawowych bibliotekach platformy .NET, w których domyślnym ActivityIdFormat jest teraz W3C.
ms.date: 11/01/2020
ms.openlocfilehash: 77ee705ac18065c84ddeab3127e01b6a40c3b84d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761560"
---
# <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="73b81-103">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="73b81-103">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="73b81-104">Domyślny format identyfikatora dla działania ( <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> ) to teraz <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="73b81-104">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="change-description"></a><span data-ttu-id="73b81-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="73b81-105">Change description</span></span>

<span data-ttu-id="73b81-106">Format identyfikatora działania W3C został wprowadzony w programie .NET Core 3,0 jako alternatywa dla formatu identyfikatora hierarchicznego.</span><span class="sxs-lookup"><span data-stu-id="73b81-106">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="73b81-107">Jednak w celu zachowania zgodności format W3C nie został wprowadzony domyślnie do programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="73b81-107">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="73b81-108">Wartość domyślna została zmieniona w programie .NET 5,0, ponieważ [format W3C został ratyfikowany](https://www.w3.org/TR/trace-context/) i uzyskano trakcję w wielu implementacjach języka.</span><span class="sxs-lookup"><span data-stu-id="73b81-108">The default was changed in .NET 5.0 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="73b81-109">Jeśli aplikacja jest przeznaczona na platformę inną niż .NET 5,0 lub nowsza, środowisko będzie miało stare zachowanie, gdzie <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> jest formatem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="73b81-109">If your app targets a platform other than .NET 5.0 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="73b81-110">Ta wartość domyślna dotyczy platform net45 +, standard 1.1 + i netcoreapp (1. x, 2. x i 3. x).</span><span class="sxs-lookup"><span data-stu-id="73b81-110">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="73b81-111">W programie .NET 5,0 i nowszych <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> jest ustawiona na <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="73b81-111">In .NET 5.0 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="73b81-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="73b81-112">Version introduced</span></span>

<span data-ttu-id="73b81-113">5,0</span><span class="sxs-lookup"><span data-stu-id="73b81-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="73b81-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="73b81-114">Recommended action</span></span>

<span data-ttu-id="73b81-115">Jeśli aplikacja jest niezależny od do identyfikatora, który jest używany na potrzeby śledzenia rozproszonego, nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="73b81-115">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="73b81-116">Biblioteki, takie jak ASP.NET Core i <xref:System.Net.Http.HttpClient> mogą zużywać lub propagować obie wersje programu <xref:System.Diagnostics.ActivityIdFormat> .</span><span class="sxs-lookup"><span data-stu-id="73b81-116">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="73b81-117">Jeśli wymagane jest współdziałanie z istniejącymi systemami lub bieżące systemy korzystają z formatu identyfikatora, można zachować stare zachowanie przez ustawienie wartości <xref:System.Diagnostics.Activity.DefaultIdFormat> <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="73b81-117">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="73b81-118">Alternatywnie można ustawić przełącznik AppContext na jeden z trzech sposobów:</span><span class="sxs-lookup"><span data-stu-id="73b81-118">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="73b81-119">W pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="73b81-119">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="73b81-120">W *runtimeconfig.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="73b81-120">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="73b81-121">Za przy użyciu zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="73b81-121">Through an environment variable.</span></span>

  <span data-ttu-id="73b81-122">Ustaw `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` wartość `true` lub 1.</span><span class="sxs-lookup"><span data-stu-id="73b81-122">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="73b81-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="73b81-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
