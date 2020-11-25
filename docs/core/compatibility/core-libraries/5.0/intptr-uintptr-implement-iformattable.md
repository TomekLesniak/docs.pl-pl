---
title: 'Zmiana podziału: IntPtr i UIntPtr Implementuj IFormattable'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których IntPtr i UIntPtr implementują teraz IFormattable.
ms.date: 11/01/2020
ms.openlocfilehash: 0684652cdc2b8cf1d237074263bf0809082b0dcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761640"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="a3df5-103">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="a3df5-103">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="a3df5-104"><xref:System.IntPtr> i <xref:System.UIntPtr> teraz implementowane <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="a3df5-104"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="a3df5-105">Funkcje, które sprawdzają <xref:System.IFormattable> obsługę, mogą teraz zwracać różne wyniki dla tych typów, ponieważ mogą one być przekazywane specyfikatorem formatu i kulturą.</span><span class="sxs-lookup"><span data-stu-id="a3df5-105">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

## <a name="change-description"></a><span data-ttu-id="a3df5-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a3df5-106">Change description</span></span>

<span data-ttu-id="a3df5-107">We wcześniejszych wersjach programu .NET <xref:System.IntPtr> i <xref:System.UIntPtr> nie należy implementować programu <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="a3df5-107">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="a3df5-108">Funkcje, które sprawdzają, mogą powracać <xref:System.IFormattable> do samego wywołania <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> lub <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> , co oznacza, że specyfikatory formatu i kultury nie są przestrzegane.</span><span class="sxs-lookup"><span data-stu-id="a3df5-108">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="a3df5-109">W programie .NET 5,0 i jego nowszych wersjach <xref:System.IntPtr> i <xref:System.UIntPtr> implementacji <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="a3df5-109">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="a3df5-110">Funkcje, które sprawdzają <xref:System.IFormattable> obsługę, mogą teraz zwracać różne wyniki dla tych typów, ponieważ mogą one być przekazywane specyfikatorem formatu i kulturą.</span><span class="sxs-lookup"><span data-stu-id="a3df5-110">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="a3df5-111">Ta zmiana ma wpływ na scenariusze, takie jak interpolowane ciągi i <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> , między innymi.</span><span class="sxs-lookup"><span data-stu-id="a3df5-111">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a3df5-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a3df5-112">Reason for change</span></span>

<span data-ttu-id="a3df5-113"><xref:System.IntPtr><xref:System.UIntPtr>Język C# obsługuje teraz `nint` `nuint` słowa kluczowe i.</span><span class="sxs-lookup"><span data-stu-id="a3df5-113"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="a3df5-114">Typy kopii zapasowych zostały zaktualizowane, aby zapewnić bliską parzystość (tam, gdzie to możliwe) funkcje udostępniane przez inne typy pierwotne, na przykład <xref:System.Int32?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a3df5-114">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a3df5-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a3df5-115">Version introduced</span></span>

<span data-ttu-id="a3df5-116">5,0</span><span class="sxs-lookup"><span data-stu-id="a3df5-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a3df5-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a3df5-117">Recommended action</span></span>

<span data-ttu-id="a3df5-118">Jeśli nie chcesz używać specyfikatora formatu lub kultury niestandardowej, która ma być używana podczas wyświetlania wartości tych typów, możesz wywołać <xref:System.IntPtr.ToString?displayProperty=nameWithType> i <xref:System.UIntPtr.ToString?displayProperty=nameWithType> przeciążenia `ToString()` .</span><span class="sxs-lookup"><span data-stu-id="a3df5-118">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a3df5-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a3df5-119">Affected APIs</span></span>

<span data-ttu-id="a3df5-120">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a3df5-120">Not detectable via API analysis.</span></span>

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
