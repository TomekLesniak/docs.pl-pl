---
title: 'Zmiana podziału: zmiana zachowania dla Vector2. Lerp i Vector4. Lerp'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których implementacja Vector2. Lerp i Vector4. Lerp została zmieniona na prawidłowo w przypadku błędu zaokrąglania zmiennoprzecinkowego.
ms.date: 11/01/2020
ms.openlocfilehash: 8e363a559dba8b7563c40637c47f101d59951216
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761411"
---
# <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="5259b-103">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="5259b-103">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="5259b-104">Implementacja <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> i <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> zmiana na prawidłowe konto dla błędu zaokrąglania zmiennoprzecinkowego.</span><span class="sxs-lookup"><span data-stu-id="5259b-104">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

## <a name="change-description"></a><span data-ttu-id="5259b-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="5259b-105">Change description</span></span>

<span data-ttu-id="5259b-106">Wcześniej <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> i <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> zostały zaimplementowane jako `value1 + (value2 - value1) * amount` .</span><span class="sxs-lookup"><span data-stu-id="5259b-106">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="5259b-107">Jednak ze względu na błąd zaokrąglania liczb zmiennoprzecinkowych ten algorytm nie zawsze zwraca `value2` wartość, gdy `amount` jest `1.0f` .</span><span class="sxs-lookup"><span data-stu-id="5259b-107">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="5259b-108">W przypadku programu .NET 5,0 lub nowszego implementacja używa tego samego algorytmu co <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType> `(value1 * (1.0f - amount)) + (value2 * amount)` .</span><span class="sxs-lookup"><span data-stu-id="5259b-108">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="5259b-109">Ten algorytm poprawnie rozliczy dla błędu zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="5259b-109">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="5259b-110">Teraz, gdy `amount` jest `1.0f` , wynik jest precyzyjna `value2` .</span><span class="sxs-lookup"><span data-stu-id="5259b-110">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="5259b-111">Zaktualizowany algorytm umożliwia także swobodne zoptymalizowanie algorytmu przy użyciu, <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> gdy jest on dostępny.</span><span class="sxs-lookup"><span data-stu-id="5259b-111">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5259b-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="5259b-112">Version introduced</span></span>

<span data-ttu-id="5259b-113">5,0</span><span class="sxs-lookup"><span data-stu-id="5259b-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5259b-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="5259b-114">Recommended action</span></span>

<span data-ttu-id="5259b-115">Nie jest wymagane żadne działanie.</span><span class="sxs-lookup"><span data-stu-id="5259b-115">No action is necessary.</span></span> <span data-ttu-id="5259b-116">Jeśli jednak chcesz zachować stare zachowanie, możesz zaimplementować własną `Lerp` funkcję, która używa poprzedniego algorytmu `value1 + (value2 - value1) * amount` .</span><span class="sxs-lookup"><span data-stu-id="5259b-116">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5259b-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="5259b-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
