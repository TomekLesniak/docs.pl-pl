---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024705"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="722aa-101">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="722aa-101">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="722aa-102"><xref:System.IntPtr>i <xref:System.UIntPtr> teraz implementowane <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="722aa-102"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="722aa-103">Funkcje, które sprawdzają <xref:System.IFormattable> obsługę, mogą teraz zwracać różne wyniki dla tych typów, ponieważ mogą one być przekazywane specyfikatorem formatu i kulturą.</span><span class="sxs-lookup"><span data-stu-id="722aa-103">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

#### <a name="change-description"></a><span data-ttu-id="722aa-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="722aa-104">Change description</span></span>

<span data-ttu-id="722aa-105">We wcześniejszych wersjach programu .NET <xref:System.IntPtr> i <xref:System.UIntPtr> nie należy implementować programu <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="722aa-105">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="722aa-106">Funkcje, które sprawdzają, mogą powracać <xref:System.IFormattable> do samego wywołania <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> lub <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> , co oznacza, że specyfikatory formatu i kultury nie są przestrzegane.</span><span class="sxs-lookup"><span data-stu-id="722aa-106">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="722aa-107">W programie .NET 5,0 i jego nowszych wersjach <xref:System.IntPtr> i <xref:System.UIntPtr> implementacji <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="722aa-107">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="722aa-108">Funkcje, które sprawdzają <xref:System.IFormattable> obsługę, mogą teraz zwracać różne wyniki dla tych typów, ponieważ mogą one być przekazywane specyfikatorem formatu i kulturą.</span><span class="sxs-lookup"><span data-stu-id="722aa-108">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="722aa-109">Ta zmiana ma wpływ na scenariusze, takie jak interpolowane ciągi i <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> , między innymi.</span><span class="sxs-lookup"><span data-stu-id="722aa-109">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="722aa-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="722aa-110">Reason for change</span></span>

<span data-ttu-id="722aa-111"><xref:System.IntPtr><xref:System.UIntPtr>Język C# obsługuje teraz `nint` `nuint` słowa kluczowe i.</span><span class="sxs-lookup"><span data-stu-id="722aa-111"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="722aa-112">Typy kopii zapasowych zostały zaktualizowane, aby zapewnić bliską parzystość (tam, gdzie to możliwe) funkcje udostępniane przez inne typy pierwotne, na przykład <xref:System.Int32?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="722aa-112">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="722aa-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="722aa-113">Version introduced</span></span>

<span data-ttu-id="722aa-114">5,0 wersja zapoznawcza 4</span><span class="sxs-lookup"><span data-stu-id="722aa-114">5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="722aa-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="722aa-115">Recommended action</span></span>

<span data-ttu-id="722aa-116">Jeśli nie chcesz używać specyfikatora formatu lub kultury niestandardowej, która ma być używana podczas wyświetlania wartości tych typów, możesz wywołać <xref:System.IntPtr.ToString?displayProperty=nameWithType> i <xref:System.UIntPtr.ToString?displayProperty=nameWithType> przeciążenia `ToString()` .</span><span class="sxs-lookup"><span data-stu-id="722aa-116">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

#### <a name="category"></a><span data-ttu-id="722aa-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="722aa-117">Category</span></span>

<span data-ttu-id="722aa-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="722aa-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="722aa-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="722aa-119">Affected APIs</span></span>

<span data-ttu-id="722aa-120">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="722aa-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
