---
title: 'Zmiana podziału: kolejność tagów w działaniu. Tagi są odwrócone'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w podstawowych bibliotekach .NET, w których działanie. Tagi zawierają teraz elementy na liście zgodnie z kolejnością, w której zostały dodane.
ms.date: 11/01/2020
ms.openlocfilehash: 1ff14dc1a4f7a0bf8cf9e79f3750b819f4d4a5ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761496"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="bae2b-103">Kolejność tagów w działaniu. Tagi są odwrócone</span><span class="sxs-lookup"><span data-stu-id="bae2b-103">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="bae2b-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> teraz przechowuje elementy na liście zgodnie z kolejnością, w której zostały dodane, czyli pierwszy dodany element znajduje się na liście.</span><span class="sxs-lookup"><span data-stu-id="bae2b-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="bae2b-105">Ta zmiana została wprowadzona w celu dopasowania do [specyfikacji atrybutów OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span><span class="sxs-lookup"><span data-stu-id="bae2b-105">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

## <a name="change-description"></a><span data-ttu-id="bae2b-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="bae2b-106">Change description</span></span>

<span data-ttu-id="bae2b-107">W poprzednich wersjach .NET program <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> przechowuje elementy w odwrotnej kolejności, z której są dodawane.</span><span class="sxs-lookup"><span data-stu-id="bae2b-107">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="bae2b-108">Oznacza to, że pierwszy dodany element jest ostatni na liście.</span><span class="sxs-lookup"><span data-stu-id="bae2b-108">That is, the first item added is last in the list.</span></span> <span data-ttu-id="bae2b-109">Począwszy od platformy .NET 5,0, kolejność elementów jest odwracana, a pierwszy dodany element jest zawsze na liście.</span><span class="sxs-lookup"><span data-stu-id="bae2b-109">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="bae2b-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="bae2b-110">Version introduced</span></span>

<span data-ttu-id="bae2b-111">5,0</span><span class="sxs-lookup"><span data-stu-id="bae2b-111">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bae2b-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="bae2b-112">Recommended action</span></span>

<span data-ttu-id="bae2b-113">Jeśli aplikacja ma zależność od <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> kolejności listy i uaktualniasz do programu .net 5,0 lub nowszego, musisz zmienić tę część kodu.</span><span class="sxs-lookup"><span data-stu-id="bae2b-113">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="bae2b-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bae2b-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
