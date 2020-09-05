---
ms.openlocfilehash: 14581b193fc000c7f805a0602e191cad688c014a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496472"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="448a8-101">W kalendarzu Perski jest teraz używany algorytm słoneczny Hijri</span><span class="sxs-lookup"><span data-stu-id="448a8-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="448a8-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="448a8-102">Details</span></span>

<span data-ttu-id="448a8-103">Począwszy od .NET Framework 4,6, <xref:System.Globalization.PersianCalendar?displayProperty=fullName> Klasa używa algorytmu słonecznego kalendarza Hidżry.</span><span class="sxs-lookup"><span data-stu-id="448a8-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="448a8-104">Konwertowanie dat między <xref:System.Globalization.PersianCalendar?displayProperty=fullName> i innymi kalendarzami może spowodować nieco inne wyniki zaczynające się od .NET Framework 4,6 dla dat wcześniejszych niż 1800 lub późniejsze niż 2023 (gregoriański). Ponadto <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> jest teraz <code>March 22, 0622</code> zamiast <code>March 21, 0622</code> .</span><span class="sxs-lookup"><span data-stu-id="448a8-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="448a8-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="448a8-105">Suggestion</span></span>

<span data-ttu-id="448a8-106">Należy pamiętać, że niektóre wczesne lub późne daty mogą być nieco inne podczas korzystania z PersianCalendar w .NET Framework 4,6.</span><span class="sxs-lookup"><span data-stu-id="448a8-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="448a8-107">Ponadto podczas serializowania dat między procesami, które mogą być uruchamiane w różnych wersjach .NET Framework, nie należy przechowywać ich jako ciągów dat PersianCalendar (ponieważ te wartości mogą być różne).</span><span class="sxs-lookup"><span data-stu-id="448a8-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="448a8-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="448a8-108">Name</span></span>    | <span data-ttu-id="448a8-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="448a8-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="448a8-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="448a8-110">Scope</span></span>   |<span data-ttu-id="448a8-111">Mały</span><span class="sxs-lookup"><span data-stu-id="448a8-111">Minor</span></span>|
|<span data-ttu-id="448a8-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="448a8-112">Version</span></span>|<span data-ttu-id="448a8-113">4,6</span><span class="sxs-lookup"><span data-stu-id="448a8-113">4.6</span></span>|
|<span data-ttu-id="448a8-114">Typ</span><span class="sxs-lookup"><span data-stu-id="448a8-114">Type</span></span>|<span data-ttu-id="448a8-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="448a8-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="448a8-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="448a8-116">Affected APIs</span></span>

- <xref:System.Globalization.PersianCalendar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Globalization.PersianCalendar`

-->
