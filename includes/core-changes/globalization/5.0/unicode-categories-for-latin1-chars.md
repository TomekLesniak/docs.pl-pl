---
ms.openlocfilehash: 48d2f1b5fa2eced30d3c9fb65804268904f11ab8
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065070"
---
### <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="0a84a-101">Zmieniono kategorię Unicode dla niektórych znaków łacińskich 1</span><span class="sxs-lookup"><span data-stu-id="0a84a-101">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="0a84a-102"><xref:System.Char> Metody teraz zwracają poprawną kategorię Unicode dla znaków w zakresie łaciński-1.</span><span class="sxs-lookup"><span data-stu-id="0a84a-102"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="0a84a-103">Kategoria jest zgodna z normą standardu Unicode.</span><span class="sxs-lookup"><span data-stu-id="0a84a-103">The category matches that of the Unicode standard.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0a84a-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="0a84a-104">Change description</span></span>

<span data-ttu-id="0a84a-105">W poprzednich wersjach .NET, <xref:System.Char> metody używały ustalonej listy kategorii Unicode dla znaków w zakresie łaciński-1.</span><span class="sxs-lookup"><span data-stu-id="0a84a-105">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="0a84a-106">Jednak standard Unicode zmienił kategorie niektórych z tych znaków, ponieważ te interfejsy API zostały zaimplementowane, tworząc niezgodność.</span><span class="sxs-lookup"><span data-stu-id="0a84a-106">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="0a84a-107">Ponadto istnieje również rozbieżność między <xref:System.Char> i <xref:System.Globalization.CharUnicodeInfo> interfejsami API, które są zgodne ze standardem Unicode.</span><span class="sxs-lookup"><span data-stu-id="0a84a-107">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="0a84a-108">W programie .NET 5,0 i jego nowszych wersjach <xref:System.Char> metody używają i zwracają kategorię Unicode zgodną ze standardem Unicode dla wszystkich znaków.</span><span class="sxs-lookup"><span data-stu-id="0a84a-108">In .NET 5.0 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="0a84a-109">W poniższej tabeli przedstawiono znaki, których kategorie Unicode zostały zmienione w programie .NET 5,0:</span><span class="sxs-lookup"><span data-stu-id="0a84a-109">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="0a84a-110">Znak</span><span class="sxs-lookup"><span data-stu-id="0a84a-110">Character</span></span>    | <span data-ttu-id="0a84a-111">Kategoria Unicode</span><span class="sxs-lookup"><span data-stu-id="0a84a-111">Unicode category</span></span><br><span data-ttu-id="0a84a-112">w poprzednich wersjach programu .NET</span><span class="sxs-lookup"><span data-stu-id="0a84a-112">in previous .NET versions</span></span> | <span data-ttu-id="0a84a-113">Kategoria Unicode</span><span class="sxs-lookup"><span data-stu-id="0a84a-113">Unicode category</span></span><br><span data-ttu-id="0a84a-114">w programie .NET 5,0 i jego nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="0a84a-114">in .NET 5.0 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="0a84a-115">§ (\u00a7)</span><span class="sxs-lookup"><span data-stu-id="0a84a-115">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="0a84a-116">ª (\u00aa)</span><span class="sxs-lookup"><span data-stu-id="0a84a-116">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="0a84a-117">LUBISZ (\u00ad)</span><span class="sxs-lookup"><span data-stu-id="0a84a-117">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="0a84a-118">¶ (\u00b6)</span><span class="sxs-lookup"><span data-stu-id="0a84a-118">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="0a84a-119">€ (\u00ba)</span><span class="sxs-lookup"><span data-stu-id="0a84a-119">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

#### <a name="version-introduced"></a><span data-ttu-id="0a84a-120">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="0a84a-120">Version introduced</span></span>

<span data-ttu-id="0a84a-121">.NET 5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="0a84a-121">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0a84a-122">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="0a84a-122">Recommended action</span></span>

<span data-ttu-id="0a84a-123">Jeśli masz kod, który pobiera kategorię znaku Unicode przy użyciu <xref:System.Char> klasy i zakłada, że Kategoria nigdy nie ulegnie zmianie, może być konieczne jej zaktualizowanie.</span><span class="sxs-lookup"><span data-stu-id="0a84a-123">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0a84a-124">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="0a84a-124">Reason for change</span></span>

<span data-ttu-id="0a84a-125">Ta zmiana została wprowadzona w taki sposób, aby kategorie zwracane przez <xref:System.Char> Typ były zgodne ze standardem Unicode i <xref:System.Globalization.CharUnicodeInfo> typem.</span><span class="sxs-lookup"><span data-stu-id="0a84a-125">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

#### <a name="category"></a><span data-ttu-id="0a84a-126">Kategoria</span><span class="sxs-lookup"><span data-stu-id="0a84a-126">Category</span></span>

- <span data-ttu-id="0a84a-127">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0a84a-127">Core .NET libraries</span></span>
- <span data-ttu-id="0a84a-128">Globalizacja</span><span class="sxs-lookup"><span data-stu-id="0a84a-128">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0a84a-129">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0a84a-129">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="0a84a-130">Ponadto ta zmiana ma wpływ na każdą klasę, która jest zależna od elementu w <xref:System.Char> celu uzyskania kategorii znaków Unicode, na przykład <xref:System.Text.RegularExpressions.Regex> .</span><span class="sxs-lookup"><span data-stu-id="0a84a-130">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

#### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

-->
