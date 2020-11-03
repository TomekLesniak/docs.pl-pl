---
title: 'Wprowadzenie do :::no-loc(char)::: kodowania acter w programie .NET'
description: 'Dowiedz się więcej :::no-loc(char)::: na temat kodowania i dekodowania acter w programie .NET.'
ms.date: 03/09/2020
no-loc:
- ':::no-loc(Rune):::'
- ':::no-loc(char):::'
- ':::no-loc(string):::'
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: 572fcd289eea720873d94e7fc71f3b4a030d1d70
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282307"
---
# <a name="character-encoding-in-net"></a><span data-ttu-id="c6a15-103">Kodowanie znaków na platformie .NET</span><span class="sxs-lookup"><span data-stu-id="c6a15-103">Character encoding in .NET</span></span>

<span data-ttu-id="c6a15-104">Ten artykuł zawiera wprowadzenie do :::no-loc(char)::: systemów kodowania acter, które są używane przez platformę .NET.</span><span class="sxs-lookup"><span data-stu-id="c6a15-104">This article provides an introduction to :::no-loc(char):::acter encoding systems that are used by .NET.</span></span> <span data-ttu-id="c6a15-105">W tym artykule wyjaśniono <xref:System.String> , jak,, <xref:System.Char> <xref:System.Text.:::no-loc(Rune):::> i <xref:System.Globalization.StringInfo> typy działają z Unicode, UTF-16 i UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c6a15-105">The article explains how the <xref:System.String>, <xref:System.Char>, <xref:System.Text.:::no-loc(Rune):::>, and <xref:System.Globalization.StringInfo> types work with Unicode, UTF-16, and UTF-8.</span></span>

<span data-ttu-id="c6a15-106">Termin *:::no-loc(char)::: acter* jest używany w tym miejscu w ogólnym sensie, *co czytnik jest postrzegany jako pojedynczy element wyświetlania*.</span><span class="sxs-lookup"><span data-stu-id="c6a15-106">The term *:::no-loc(char):::acter* is used here in the general sense of *what a reader perceives as a single display element*.</span></span> <span data-ttu-id="c6a15-107">Typowe przykłady to litera "a", symbol "@" i Emoji " 🐂 ".</span><span class="sxs-lookup"><span data-stu-id="c6a15-107">Common examples are the letter "a", the symbol "@", and the emoji "🐂".</span></span> <span data-ttu-id="c6a15-108">Czasami wygląda na to :::no-loc(char)::: , że jeden acter jest w rzeczywistości składający się z wielu niezależnych elementów wyświetlanych, ponieważ sekcja w [klastrach Grapheme](#grapheme-clusters) objaśnia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-108">Sometimes what looks like one :::no-loc(char):::acter is actually composed of multiple independent display elements, as the section on [grapheme clusters](#grapheme-clusters) explains.</span></span>

## <a name="the-no-locstring-and-no-locchar-types"></a><span data-ttu-id="c6a15-109">:::no-loc(string):::Typy i :::no-loc(char):::</span><span class="sxs-lookup"><span data-stu-id="c6a15-109">The :::no-loc(string)::: and :::no-loc(char)::: types</span></span>

<span data-ttu-id="c6a15-110">Wystąpienie [:::no-loc(string):::](xref:System.String) klasy reprezentuje jakiś tekst.</span><span class="sxs-lookup"><span data-stu-id="c6a15-110">An instance of the [:::no-loc(string):::](xref:System.String) class represents some text.</span></span> <span data-ttu-id="c6a15-111">A `:::no-loc(string):::` jest logicznie sekwencją wartości 16-bitowych, z których każdy jest wystąpieniem [:::no-loc(char):::](xref:System.Char) struktury.</span><span class="sxs-lookup"><span data-stu-id="c6a15-111">A `:::no-loc(string):::` is logically a sequence of 16-bit values, each of which is an instance of the [:::no-loc(char):::](xref:System.Char) struct.</span></span> <span data-ttu-id="c6a15-112">[ :::no-loc(string)::: . Właściwość length](xref:System.String.Length) zwraca liczbę `:::no-loc(char):::` wystąpień w `:::no-loc(string):::` wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="c6a15-112">The [:::no-loc(string):::.Length](xref:System.String.Length) property returns the number of `:::no-loc(char):::` instances in the `:::no-loc(string):::` instance.</span></span>

<span data-ttu-id="c6a15-113">Poniższa funkcja Przykładowa drukuje wartości w notacji szesnastkowej wszystkich `:::no-loc(char):::` wystąpień w `:::no-loc(string):::` :</span><span class="sxs-lookup"><span data-stu-id="c6a15-113">The following sample function prints out the values in hexadecimal notation of all the `:::no-loc(char):::` instances in a `:::no-loc(string):::`:</span></span>

<span data-ttu-id="c6a15-114">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/PrintStringChars. cs" ID = "SnippetPrintChars"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-114">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::</span></span>

<span data-ttu-id="c6a15-115">Przekaż :::no-loc(string)::: "Hello" do tej funkcji i uzyskasz następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="c6a15-115">Pass the :::no-loc(string)::: "Hello" to this function, and you get the following output:</span></span>

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

<span data-ttu-id="c6a15-116">Każdy :::no-loc(char)::: acter jest reprezentowany przez pojedynczą `:::no-loc(char):::` wartość.</span><span class="sxs-lookup"><span data-stu-id="c6a15-116">Each :::no-loc(char):::acter is represented by a single `:::no-loc(char):::` value.</span></span> <span data-ttu-id="c6a15-117">Ten wzorzec ma wartość true w przypadku większości języków świata.</span><span class="sxs-lookup"><span data-stu-id="c6a15-117">That pattern holds true for most of the world's languages.</span></span> <span data-ttu-id="c6a15-118">Na przykład poniżej przedstawiono dane wyjściowe dla dwóch chińskich :::no-loc(char)::: acters, takie jak *nǐ hǎo* i średnia *Hello* :</span><span class="sxs-lookup"><span data-stu-id="c6a15-118">For example, here's the output for two Chinese :::no-loc(char):::acters that sound like *nǐ hǎo* and mean *Hello* :</span></span>

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

<span data-ttu-id="c6a15-119">Jednakże w przypadku niektórych języków i dla niektórych symboli i znaków emoji `:::no-loc(char):::` do reprezentowania pojedynczego acter są dwa wystąpienia :::no-loc(char)::: .</span><span class="sxs-lookup"><span data-stu-id="c6a15-119">However, for some languages and for some symbols and emoji, it takes two `:::no-loc(char):::` instances to represent a single :::no-loc(char):::acter.</span></span> <span data-ttu-id="c6a15-120">Na przykład Porównaj :::no-loc(char)::: acters i `:::no-loc(char):::` wystąpienia w wyrazie oznaczające *Osage* w języku Osage:</span><span class="sxs-lookup"><span data-stu-id="c6a15-120">For example, compare the :::no-loc(char):::acters and `:::no-loc(char):::` instances in the word that means *Osage* in the Osage language:</span></span>

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

<span data-ttu-id="c6a15-121">W poprzednim przykładzie każdy acter, :::no-loc(char)::: z wyjątkiem miejsca, jest reprezentowany przez dwa `:::no-loc(char):::` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-121">In the preceding example, each :::no-loc(char):::acter except the space is represented by two `:::no-loc(char):::` instances.</span></span>

<span data-ttu-id="c6a15-122">Pojedynczy emoji Unicode jest również reprezentowany przez dwa `:::no-loc(char):::` s, jak pokazano w poniższym przykładzie pokazujący OX-emoji:</span><span class="sxs-lookup"><span data-stu-id="c6a15-122">A single Unicode emoji is also represented by two `:::no-loc(char):::`s, as seen in the following example showing an ox emoji:</span></span>

```output
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

<span data-ttu-id="c6a15-123">Te przykłady pokazują, że wartość `:::no-loc(string):::.Length` , która wskazuje liczbę `:::no-loc(char):::` wystąpień, nie zawsze wskazuje liczbę wyświetlanych :::no-loc(char)::: acters.</span><span class="sxs-lookup"><span data-stu-id="c6a15-123">These examples show that the value of `:::no-loc(string):::.Length`, which indicates the number of `:::no-loc(char):::` instances, doesn't necessarily indicate the number of displayed :::no-loc(char):::acters.</span></span> <span data-ttu-id="c6a15-124">Pojedyncze `:::no-loc(char):::` wystąpienie przez siebie samo nie musi reprezentować :::no-loc(char)::: acter.</span><span class="sxs-lookup"><span data-stu-id="c6a15-124">A single `:::no-loc(char):::` instance by itself doesn't necessarily represent a :::no-loc(char):::acter.</span></span>

<span data-ttu-id="c6a15-125">`:::no-loc(char):::`Pary, które są mapowane na pojedyncze :::no-loc(char)::: acter są nazywane *parami wieloskładnikowym*.</span><span class="sxs-lookup"><span data-stu-id="c6a15-125">The `:::no-loc(char):::` pairs that map to a single :::no-loc(char):::acter are called *surrogate pairs*.</span></span> <span data-ttu-id="c6a15-126">Aby zrozumieć, jak działają, należy zrozumieć kodowanie Unicode i UTF-16.</span><span class="sxs-lookup"><span data-stu-id="c6a15-126">To understand how they work, you need to understand Unicode and UTF-16 encoding.</span></span>

## <a name="unicode-code-points"></a><span data-ttu-id="c6a15-127">Punkty kodu Unicode</span><span class="sxs-lookup"><span data-stu-id="c6a15-127">Unicode code points</span></span>

<span data-ttu-id="c6a15-128">Unicode jest międzynarodowym standardem kodowania do użycia na różnych platformach i w różnych językach i skryptach.</span><span class="sxs-lookup"><span data-stu-id="c6a15-128">Unicode is an international encoding standard for use on various platforms and with various languages and scripts.</span></span>

<span data-ttu-id="c6a15-129">Standard Unicode definiuje ponad 1 100 000 [punktów kodów](https://www.unicode.org/glossary/#code_point).</span><span class="sxs-lookup"><span data-stu-id="c6a15-129">The Unicode Standard defines over 1.1 million [code points](https://www.unicode.org/glossary/#code_point).</span></span> <span data-ttu-id="c6a15-130">Punkt kodu jest wartością całkowitą, która może być z zakresu od 0 do `U+10FFFF` (dziesiętne 1 114 111).</span><span class="sxs-lookup"><span data-stu-id="c6a15-130">A code point is an integer value that can range from 0 to `U+10FFFF` (decimal 1,114,111).</span></span> <span data-ttu-id="c6a15-131">Niektóre punkty kodu są przypisywane do liter, symboli lub emoji.</span><span class="sxs-lookup"><span data-stu-id="c6a15-131">Some code points are assigned to letters, symbols, or emoji.</span></span> <span data-ttu-id="c6a15-132">Inne są przypisane do akcji kontrolujących sposób wyświetlania tekstu lub :::no-loc(char)::: acters, na przykład z wyprzedzeniem do nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="c6a15-132">Others are assigned to actions that control how text or :::no-loc(char):::acters are displayed, such as advance to a new line.</span></span> <span data-ttu-id="c6a15-133">Wiele punktów kodowych nie jest jeszcze przypisanych.</span><span class="sxs-lookup"><span data-stu-id="c6a15-133">Many code points are not yet assigned.</span></span>

<span data-ttu-id="c6a15-134">Poniżej przedstawiono kilka przykładów przypisań punktów kodu z linkami do kodu Unicode :::no-loc(char)::: TS, w którym są wyświetlane:</span><span class="sxs-lookup"><span data-stu-id="c6a15-134">Here are some examples of code point assignments, with links to Unicode :::no-loc(char):::ts in which they appear:</span></span>

|<span data-ttu-id="c6a15-135">Liczba dziesiętna</span><span class="sxs-lookup"><span data-stu-id="c6a15-135">Decimal</span></span>|<span data-ttu-id="c6a15-136">Hex</span><span class="sxs-lookup"><span data-stu-id="c6a15-136">Hex</span></span>       |<span data-ttu-id="c6a15-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="c6a15-137">Example</span></span>|<span data-ttu-id="c6a15-138">Opis</span><span class="sxs-lookup"><span data-stu-id="c6a15-138">Description</span></span>|
|------:|----------|-------|-----------|
|<span data-ttu-id="c6a15-139">10</span><span class="sxs-lookup"><span data-stu-id="c6a15-139">10</span></span>     | `U+000A` |<span data-ttu-id="c6a15-140">Brak</span><span class="sxs-lookup"><span data-stu-id="c6a15-140">N/A</span></span>| <span data-ttu-id="c6a15-141">[KANAŁ INFORMACYJNY WIERSZA](https://www.unicode.org/:::no-loc(char):::ts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="c6a15-141">[LINE FEED](https://www.unicode.org/:::no-loc(char):::ts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="c6a15-142">97</span><span class="sxs-lookup"><span data-stu-id="c6a15-142">97</span></span>     | `U+0061` | <span data-ttu-id="c6a15-143">a</span><span class="sxs-lookup"><span data-stu-id="c6a15-143">a</span></span> | <span data-ttu-id="c6a15-144">[MAŁA LITERA A](https://www.unicode.org/:::no-loc(char):::ts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="c6a15-144">[LATIN SMALL LETTER A](https://www.unicode.org/:::no-loc(char):::ts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="c6a15-145">562</span><span class="sxs-lookup"><span data-stu-id="c6a15-145">562</span></span>    | `U+0232` | <span data-ttu-id="c6a15-146">Ȳ</span><span class="sxs-lookup"><span data-stu-id="c6a15-146">Ȳ</span></span> | <span data-ttu-id="c6a15-147">[WIELKA LITERA Y Z MACRON](https://www.unicode.org/:::no-loc(char):::ts/PDF/U0180.pdf)</span><span class="sxs-lookup"><span data-stu-id="c6a15-147">[LATIN CAPITAL LETTER Y WITH MACRON](https://www.unicode.org/:::no-loc(char):::ts/PDF/U0180.pdf)</span></span> |
|<span data-ttu-id="c6a15-148">68 675</span><span class="sxs-lookup"><span data-stu-id="c6a15-148">68,675</span></span> | `U+10C43`| <span data-ttu-id="c6a15-149">𐱃</span><span class="sxs-lookup"><span data-stu-id="c6a15-149">𐱃</span></span> | <span data-ttu-id="c6a15-150">[STARY TURKIC LETTER ORKHON NA](https://www.unicode.org/:::no-loc(char):::ts/PDF/U10C00.pdf)</span><span class="sxs-lookup"><span data-stu-id="c6a15-150">[OLD TURKIC LETTER ORKHON AT](https://www.unicode.org/:::no-loc(char):::ts/PDF/U10C00.pdf)</span></span> |
|<span data-ttu-id="c6a15-151">127 801</span><span class="sxs-lookup"><span data-stu-id="c6a15-151">127,801</span></span>| `U+1F339`| <span data-ttu-id="c6a15-152">🌹</span><span class="sxs-lookup"><span data-stu-id="c6a15-152">🌹</span></span> | <span data-ttu-id="c6a15-153">[RÓŻAny emoji](https://www.unicode.org/:::no-loc(char):::ts/PDF/U1F300.pdf)</span><span class="sxs-lookup"><span data-stu-id="c6a15-153">[ROSE emoji](https://www.unicode.org/:::no-loc(char):::ts/PDF/U1F300.pdf)</span></span> |

<span data-ttu-id="c6a15-154">Punkty kodu są zwykle określane przy użyciu składni `U+xxxx` , gdzie `xxxx` jest wartością całkowitą zakodowaną szesnastkowo.</span><span class="sxs-lookup"><span data-stu-id="c6a15-154">Code points are customarily referred to by using the syntax `U+xxxx`, where `xxxx` is the hex-encoded integer value.</span></span>

<span data-ttu-id="c6a15-155">W całym zakresie punktów kodu istnieją dwa podzakresy:</span><span class="sxs-lookup"><span data-stu-id="c6a15-155">Within the full range of code points there are two subranges:</span></span>

* <span data-ttu-id="c6a15-156">**Podstawowa płaszczyzna wielojęzyczna (BMP)** w zakresie `U+0000..U+FFFF` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-156">The **Basic Multilingual Plane (BMP)** in the range `U+0000..U+FFFF`.</span></span> <span data-ttu-id="c6a15-157">Ten 16-bitowy zakres zapewnia 65 536 punktów kodów, wystarczających do pokrycia większości systemów pisania na świecie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-157">This 16-bit range provides 65,536 code points, enough to cover the majority of the world's writing systems.</span></span>
* <span data-ttu-id="c6a15-158">**Dodatkowe punkty kodu** z zakresu `U+10000..U+10FFFF` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-158">**Supplementary code points** in the range `U+10000..U+10FFFF`.</span></span> <span data-ttu-id="c6a15-159">Ten 21-bitowy zakres oferuje ponad milion dodatkowych punktów kodu, które mogą być używane dla mniej dobrze znanych języków i innych celów, takich jak emoji.</span><span class="sxs-lookup"><span data-stu-id="c6a15-159">This 21-bit range provides more than a million additional code points that can be used for less well-known languages and other purposes such as emojis.</span></span>

<span data-ttu-id="c6a15-160">Na poniższym diagramie przedstawiono relację między BMP i dodatkowymi punktami kodu.</span><span class="sxs-lookup"><span data-stu-id="c6a15-160">The following diagram illustrates the relationship between the BMP and the supplementary code points.</span></span>

:::image type="content" source="media/:::nie-Loc (Char)::: acter-Encoding-Introduction/BMP-and-Supplementary. SVG "Alt-text =" BMP i dodatkowe punkty kodów ":::

## <a name="utf-16-code-units"></a><span data-ttu-id="c6a15-162">Jednostki kodu UTF-16</span><span class="sxs-lookup"><span data-stu-id="c6a15-162">UTF-16 code units</span></span>

<span data-ttu-id="c6a15-163">16-bitowy format transformacji Unicode ( [UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) to :::no-loc(char)::: system kodowania acter, który używa 16-bitowych *jednostek kodu* do reprezentowania punktów kodu Unicode.</span><span class="sxs-lookup"><span data-stu-id="c6a15-163">16-bit Unicode Transformation Format ( [UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) is a :::no-loc(char):::acter encoding system that uses 16-bit *code units* to represent Unicode code points.</span></span> <span data-ttu-id="c6a15-164">.NET używa kodowania UTF-16, aby zakodować tekst w `:::no-loc(string):::` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-164">.NET uses UTF-16 to encode the text in a `:::no-loc(string):::`.</span></span> <span data-ttu-id="c6a15-165">`:::no-loc(char):::`Wystąpienie reprezentuje jednostkę kodu 16-bitowego.</span><span class="sxs-lookup"><span data-stu-id="c6a15-165">A `:::no-loc(char):::` instance represents a 16-bit code unit.</span></span>

<span data-ttu-id="c6a15-166">Pojedyncza jednostka kodowa 16-bitowa może reprezentować dowolny punkt kodu w 16-bitowym zakresie podstawowej płaszczyzny wielojęzycznej.</span><span class="sxs-lookup"><span data-stu-id="c6a15-166">A single 16-bit code unit can represent any code point in the 16-bit range of the Basic Multilingual Plane.</span></span> <span data-ttu-id="c6a15-167">Jednak w przypadku punktu kodu w dodatkowych zakresach `:::no-loc(char):::` są potrzeby dwa wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-167">But for a code point in the supplementary range, two `:::no-loc(char):::` instances are needed.</span></span>

## <a name="surrogate-pairs"></a><span data-ttu-id="c6a15-168">Pary zastępcze</span><span class="sxs-lookup"><span data-stu-id="c6a15-168">Surrogate pairs</span></span>

<span data-ttu-id="c6a15-169">Tłumaczenie wartości 2 16-bitowych na pojedynczą wartość 21-bitową jest obsługiwane przez specjalny zakres nazywany *surogatami punktów kodu* od `U+D800` do `U+DFFF` (dziesiętne 55 296 do 57 343) włącznie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-169">The translation of two 16-bit values to a single 21-bit value is facilitated by a special range called the *surrogate code points* , from `U+D800` to `U+DFFF` (decimal 55,296 to 57,343), inclusive.</span></span>

<span data-ttu-id="c6a15-170">Na poniższym diagramie przedstawiono relację między kodem BMP i surogatem.</span><span class="sxs-lookup"><span data-stu-id="c6a15-170">The following diagram illustrates the relationship between the BMP and the surrogate code points.</span></span>

:::image type="content" source="media/:::nie-Loc (Char)::: acter-Encoding-Introduction/BMP-and-Surrogate. SVG "Alt-text =" BMP i Surogat punktów kodowych ":::

<span data-ttu-id="c6a15-172">Gdy do *górnego* punktu kodowego ( `U+D800..U+DBFF` ) bezpośrednio następuje *dolny* punkt kodowy ( `U+DC00..U+DFFF` ), para jest interpretowana jako dodatkowy punkt kodu przy użyciu następującej formuły:</span><span class="sxs-lookup"><span data-stu-id="c6a15-172">When a *high surrogate* code point (`U+D800..U+DBFF`) is immediately followed by a *low surrogate* code point (`U+DC00..U+DFFF`), the pair is interpreted as a supplementary code point by using the following formula:</span></span>

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

<span data-ttu-id="c6a15-173">W tej samej formule jest używana notacja dziesiętna:</span><span class="sxs-lookup"><span data-stu-id="c6a15-173">Here's the same formula using decimal notation:</span></span>

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

<span data-ttu-id="c6a15-174">*Górny* punkt kodu wieloskładnikowego nie ma wyższej wartości liczbowej niż *dolny* punkt kodowy.</span><span class="sxs-lookup"><span data-stu-id="c6a15-174">A *high* surrogate code point doesn't have a higher number value than a *low* surrogate code point.</span></span> <span data-ttu-id="c6a15-175">Górny punkt kodowy jest nazywany "wysoki", ponieważ jest używany do obliczania wyższej liczby 11 bitów pełnego zakresu kodów 21-bitowego.</span><span class="sxs-lookup"><span data-stu-id="c6a15-175">The high surrogate code point is called "high" because it's used to calculate the higher-order 11 bits of the full 21-bit code point range.</span></span> <span data-ttu-id="c6a15-176">Dolny punkt kodowy jest używany do obliczania 10 bitów o mniejszej kolejności.</span><span class="sxs-lookup"><span data-stu-id="c6a15-176">The low surrogate code point is used to calculate the lower-order 10 bits.</span></span>

<span data-ttu-id="c6a15-177">Na przykład rzeczywisty punkt kodu, który odnosi się do pary zastępczej `0xD83C` i `0xDF39`  jest obliczany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c6a15-177">For example, the actual code point that corresponds to the surrogate pair `0xD83C` and `0xDF39`  is computed as follows:</span></span>

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

<span data-ttu-id="c6a15-178">To samo obliczenie przy użyciu notacji dziesiętnej:</span><span class="sxs-lookup"><span data-stu-id="c6a15-178">Here's the same calculation using decimal notation:</span></span>

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

<span data-ttu-id="c6a15-179">Powyższy przykład pokazuje, że `"\ud83c\udf39"` jest kodowanie UTF-16 `U+1F339 ROSE ('🌹')` powyżej wymienionego powyżej.</span><span class="sxs-lookup"><span data-stu-id="c6a15-179">The preceding example demonstrates that `"\ud83c\udf39"` is the UTF-16 encoding of the `U+1F339 ROSE ('🌹')` code point mentioned earlier.</span></span>

## <a name="unicode-scalar-values"></a><span data-ttu-id="c6a15-180">Wartości skalarne Unicode</span><span class="sxs-lookup"><span data-stu-id="c6a15-180">Unicode scalar values</span></span>

<span data-ttu-id="c6a15-181">Wyrażenie " [wartość skalarna Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) " odnosi się do wszystkich punktów kodu innych niż punkty zastępcze kodu.</span><span class="sxs-lookup"><span data-stu-id="c6a15-181">The term [Unicode scalar value](https://www.unicode.org/glossary/#unicode_scalar_value) refers to all code points other than the surrogate code points.</span></span> <span data-ttu-id="c6a15-182">Innymi słowy, wartość skalarna jest dowolnym punktem kodu przypisanym do :::no-loc(char)::: acter lub może być przypisywany :::no-loc(char)::: acter w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="c6a15-182">In other words, a scalar value is any code point that is assigned a :::no-loc(char):::acter or can be assigned a :::no-loc(char):::acter in the future.</span></span> <span data-ttu-id="c6a15-183">"Znak" odnosi się do wszystkich elementów, które można przypisać do punktu kodu, co obejmuje takie czynności jak akcje kontrolujące sposób wyświetlania tekstu lub :::no-loc(char)::: acters.</span><span class="sxs-lookup"><span data-stu-id="c6a15-183">"Character" here refers to anything that can be assigned to a code point, which includes such things as actions that control how text or :::no-loc(char):::acters are displayed.</span></span>

<span data-ttu-id="c6a15-184">Na poniższym diagramie przedstawiono punkty kodów wartości skalarnych.</span><span class="sxs-lookup"><span data-stu-id="c6a15-184">The following diagram illustrates the scalar value code points.</span></span>

:::image type="content" source="media/:::nie-Loc (Char)::: acter-Encoding-Introduction/Scalar-Values. SVG "Alt-text =" wartości skalarnych ":::

### <a name="the-no-locrune-type-as-a-scalar-value"></a><span data-ttu-id="c6a15-186">:::no-loc(Rune):::Typ jako wartość skalarną</span><span class="sxs-lookup"><span data-stu-id="c6a15-186">The :::no-loc(Rune)::: type as a scalar value</span></span>

<span data-ttu-id="c6a15-187">Począwszy od platformy .NET Core 3,0, <xref:System.Text.:::no-loc(Rune):::?displayProperty=fullName> Typ reprezentuje wartość skalarną Unicode.</span><span class="sxs-lookup"><span data-stu-id="c6a15-187">Beginning with .NET Core 3.0, the <xref:System.Text.:::no-loc(Rune):::?displayProperty=fullName> type represents a Unicode scalar value.</span></span> <span data-ttu-id="c6a15-188">**`:::no-loc(Rune):::` Program nie jest dostępny w programie .NET Core 2. x lub .NET Framework 4. x.**</span><span class="sxs-lookup"><span data-stu-id="c6a15-188">**`:::no-loc(Rune):::` is not available in .NET Core 2.x or .NET Framework 4.x.**</span></span>

<span data-ttu-id="c6a15-189">`:::no-loc(Rune):::`Konstruktory weryfikują, że wystąpienie wyniku jest prawidłową wartością skalarną Unicode, w przeciwnym razie zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="c6a15-189">The `:::no-loc(Rune):::` constructors validate that the resulting instance is a valid Unicode scalar value, otherwise they throw an exception.</span></span> <span data-ttu-id="c6a15-190">Poniższy przykład pokazuje kod, który pomyślnie tworzy wystąpienia `:::no-loc(Rune):::` wystąpień, ponieważ dane wejściowe reprezentują prawidłowe wartości skalarne:</span><span class="sxs-lookup"><span data-stu-id="c6a15-190">The following example shows code that successfully instantiates `:::no-loc(Rune):::` instances because the input represents valid scalar values:</span></span>

<span data-ttu-id="c6a15-191">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/'utwórz :::no-loc(Rune)::: s.cs" ID = "SnippetValid"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-191">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/Instantiate:::no-loc(Rune):::s.cs" id="SnippetValid":::</span></span>

<span data-ttu-id="c6a15-192">Poniższy przykład zgłasza wyjątek, ponieważ punkt kodu znajduje się w zakresie surogatu i nie jest częścią pary dwuskładnikowej:</span><span class="sxs-lookup"><span data-stu-id="c6a15-192">The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span></span>

<span data-ttu-id="c6a15-193">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/'utwórz :::no-loc(Rune)::: s.cs" ID = "SnippetInvalidSurrogate"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-193">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/Instantiate:::no-loc(Rune):::s.cs" id="SnippetInvalidSurrogate":::</span></span>

<span data-ttu-id="c6a15-194">Poniższy przykład zgłasza wyjątek, ponieważ punkt kodu znajduje się poza dodatkowym zakresem:</span><span class="sxs-lookup"><span data-stu-id="c6a15-194">The following example throws an exception because the code point is beyond the supplementary range:</span></span>

<span data-ttu-id="c6a15-195">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/'utwórz :::no-loc(Rune)::: s.cs" ID = "SnippetInvalidHigh"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-195">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/Instantiate:::no-loc(Rune):::s.cs" id="SnippetInvalidHigh":::</span></span>

### <a name="no-locrune-usage-example-changing-letter-case"></a><span data-ttu-id="c6a15-196">:::no-loc(Rune)::: przykład użycia: zmiana wielkości liter</span><span class="sxs-lookup"><span data-stu-id="c6a15-196">:::no-loc(Rune)::: usage example: changing letter case</span></span>

<span data-ttu-id="c6a15-197">Interfejs API, który przyjmuje `:::no-loc(char):::` i zakłada, że pracuje z punktem kodu, który jest wartością skalarną, nie działa poprawnie, jeśli `:::no-loc(char):::` pochodzi z pary zastępczej.</span><span class="sxs-lookup"><span data-stu-id="c6a15-197">An API that takes a `:::no-loc(char):::` and assumes it is working with a code point that is a scalar value doesn't work correctly if the `:::no-loc(char):::` is from a surrogate pair.</span></span> <span data-ttu-id="c6a15-198">Rozważmy na przykład następującą metodę, która wywołuje <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> na każdym z :::no-loc(char)::: :::no-loc(string)::: :</span><span class="sxs-lookup"><span data-stu-id="c6a15-198">For example, consider the following method that calls <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> on each :::no-loc(char)::: in a :::no-loc(string)::::</span></span>

<span data-ttu-id="c6a15-199">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/ConvertToUpper. cs" ID = "SnippetBadExample"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-199">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="c6a15-200">Jeśli `input` :::no-loc(string)::: zawiera małą literę Deseret `er` ( `𐑉` ), ten kod nie przekonwertuje go na wielkie litery ( `𐐡` ).</span><span class="sxs-lookup"><span data-stu-id="c6a15-200">If the `input` :::no-loc(string)::: contains the lowercase Deseret letter `er` (`𐑉`), this code won't convert it to uppercase (`𐐡`).</span></span> <span data-ttu-id="c6a15-201">Kod jest wywoływany `:::no-loc(char):::.ToUpperInvariant` oddzielnie w każdym punkcie kodu zastępczego `U+D801` i `U+DC49` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-201">The code calls `:::no-loc(char):::.ToUpperInvariant` separately on each surrogate code point, `U+D801` and `U+DC49`.</span></span> <span data-ttu-id="c6a15-202">Ale `U+D801` nie ma wystarczających informacji, aby zidentyfikować je jako małą literę, więc `:::no-loc(char):::.ToUpperInvariant` pozostawia ją samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-202">But `U+D801` doesn't have enough information by itself to identify it as a lowercase letter, so `:::no-loc(char):::.ToUpperInvariant` leaves it alone.</span></span> <span data-ttu-id="c6a15-203">Obsługuje to ten `U+DC49` sam sposób.</span><span class="sxs-lookup"><span data-stu-id="c6a15-203">And it handles `U+DC49` the same way.</span></span> <span data-ttu-id="c6a15-204">Wynikiem jest to, że małe litery "𐑉" w `input` :::no-loc(string)::: nie są konwertowane na wielkie litery "𐑉".</span><span class="sxs-lookup"><span data-stu-id="c6a15-204">The result is that lowercase '𐑉' in the `input` :::no-loc(string)::: doesn't get converted to uppercase '𐐡'.</span></span>

<span data-ttu-id="c6a15-205">Poniżej przedstawiono dwie opcje prawidłowej konwersji :::no-loc(string)::: na wielkie litery:</span><span class="sxs-lookup"><span data-stu-id="c6a15-205">Here are two options for correctly converting a :::no-loc(string)::: to uppercase:</span></span>

* <span data-ttu-id="c6a15-206">Wywołania <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> na wejściu :::no-loc(string)::: zamiast Iterowanie `:::no-loc(char):::` przez- `:::no-loc(char):::` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-206">Call <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> on the input :::no-loc(string)::: rather than iterating `:::no-loc(char):::`-by-`:::no-loc(char):::`.</span></span> <span data-ttu-id="c6a15-207">`:::no-loc(string):::.ToUpperInvariant`Metoda ma dostęp do obu części każdej pary surogatów, więc może prawidłowo obsługiwać wszystkie punkty kodu Unicode.</span><span class="sxs-lookup"><span data-stu-id="c6a15-207">The `:::no-loc(string):::.ToUpperInvariant` method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span></span>
* <span data-ttu-id="c6a15-208">Wykonaj iterację przez wartości skalarne Unicode jako `:::no-loc(Rune):::` wystąpienia `:::no-loc(char):::` , a nie wystąpienia, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-208">Iterate through the Unicode scalar values as `:::no-loc(Rune):::` instances instead of `:::no-loc(char):::` instances, as shown in the following example.</span></span> <span data-ttu-id="c6a15-209">Ponieważ `:::no-loc(Rune):::` wystąpienie jest prawidłową wartością skalarną Unicode, można je przesłać do interfejsów API, które oczekują na wartość skalarną.</span><span class="sxs-lookup"><span data-stu-id="c6a15-209">Since a `:::no-loc(Rune):::` instance is a valid Unicode scalar value, it can be passed to APIs that expect to operate on a scalar value.</span></span> <span data-ttu-id="c6a15-210">Na przykład wywoływanie, <xref:System.Text.:::no-loc(Rune):::.ToUpperInvariant%2A?displayProperty=nameWithType> jak pokazano w poniższym przykładzie, daje poprawne wyniki:</span><span class="sxs-lookup"><span data-stu-id="c6a15-210">For example, calling <xref:System.Text.:::no-loc(Rune):::.ToUpperInvariant%2A?displayProperty=nameWithType> as shown in the following example gives correct results:</span></span>

  <span data-ttu-id="c6a15-211">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/ConvertToUpper. cs" ID = "SnippetGoodExample"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-211">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::</span></span>

### <a name="other-no-locrune-apis"></a><span data-ttu-id="c6a15-212">Inne :::no-loc(Rune)::: interfejsy API</span><span class="sxs-lookup"><span data-stu-id="c6a15-212">Other :::no-loc(Rune)::: APIs</span></span>

<span data-ttu-id="c6a15-213">`:::no-loc(Rune):::`Typ uwidacznia analogowe wiele `:::no-loc(char):::` interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="c6a15-213">The `:::no-loc(Rune):::` type exposes analogs of many of the `:::no-loc(char):::` APIs.</span></span> <span data-ttu-id="c6a15-214">Na przykład następujące metody dublowania statycznych interfejsów API w `:::no-loc(char):::` typie:</span><span class="sxs-lookup"><span data-stu-id="c6a15-214">For example, the following methods mirror static APIs on the `:::no-loc(char):::` type:</span></span>

* <xref:System.Text.:::no-loc(Rune):::.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.:::no-loc(Rune):::.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.:::no-loc(Rune):::.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.:::no-loc(Rune):::.GetUnicodeCategory%2A?displayProperty=nameWithType>

<span data-ttu-id="c6a15-215">Aby pobrać nieprzetworzoną wartość skalarną z `:::no-loc(Rune):::` wystąpienia, użyj <xref:System.Text.:::no-loc(Rune):::.Value%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="c6a15-215">To get the raw scalar value from a `:::no-loc(Rune):::` instance, use the <xref:System.Text.:::no-loc(Rune):::.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="c6a15-216">Aby skonwertować `:::no-loc(Rune):::` wystąpienie z powrotem do sekwencji `:::no-loc(char):::` s, użyj <xref:System.Text.:::no-loc(Rune):::.ToString%2A?displayProperty=nameWithType> <xref:System.Text.:::no-loc(Rune):::.EncodeToUtf16%2A?displayProperty=nameWithType> metody lub.</span><span class="sxs-lookup"><span data-stu-id="c6a15-216">To convert a `:::no-loc(Rune):::` instance back to a sequence of `:::no-loc(char):::`s, use <xref:System.Text.:::no-loc(Rune):::.ToString%2A?displayProperty=nameWithType> or the <xref:System.Text.:::no-loc(Rune):::.EncodeToUtf16%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c6a15-217">Ponieważ każda wartość skalarna Unicode jest możliwa do zaprezentowania przez pojedynczą `:::no-loc(char):::` lub dwuskładnikową parę, każde `:::no-loc(Rune):::` wystąpienie może być reprezentowane przez co najwyżej 2 `:::no-loc(char):::` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-217">Since any Unicode scalar value is representable by a single `:::no-loc(char):::` or by a surrogate pair, any `:::no-loc(Rune):::` instance can be represented by at most 2 `:::no-loc(char):::` instances.</span></span> <span data-ttu-id="c6a15-218">Użyj <xref:System.Text.:::no-loc(Rune):::.Utf16SequenceLength%2A?displayProperty=nameWithType> , aby zobaczyć, ile `:::no-loc(char):::` wystąpień jest wymaganych do reprezentowania `:::no-loc(Rune):::` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-218">Use <xref:System.Text.:::no-loc(Rune):::.Utf16SequenceLength%2A?displayProperty=nameWithType> to see how many `:::no-loc(char):::` instances are required to represent a `:::no-loc(Rune):::` instance.</span></span>

<span data-ttu-id="c6a15-219">Aby uzyskać więcej informacji na temat `:::no-loc(Rune):::` typu .NET, zobacz [ `:::no-loc(Rune):::` Dokumentacja interfejsu API](xref:System.Text.:::no-loc(Rune):::).</span><span class="sxs-lookup"><span data-stu-id="c6a15-219">For more information about the .NET `:::no-loc(Rune):::` type, see the [`:::no-loc(Rune):::` API reference](xref:System.Text.:::no-loc(Rune):::).</span></span>

## <a name="grapheme-clusters"></a><span data-ttu-id="c6a15-220">Klastry Grapheme</span><span class="sxs-lookup"><span data-stu-id="c6a15-220">Grapheme clusters</span></span>

<span data-ttu-id="c6a15-221">Wygląda na to :::no-loc(char)::: , że jeden acter może wynikać z kombinacji wielu punktów kodowych, więc bardziej opisowy termin, który jest często używany zamiast " :::no-loc(char)::: acter", to [klaster Grapheme](https://www.unicode.org/glossary/#grapheme_cluster).</span><span class="sxs-lookup"><span data-stu-id="c6a15-221">What looks like one :::no-loc(char):::acter might result from a combination of multiple code points, so a more descriptive term that is often used in place of ":::no-loc(char):::acter" is [grapheme cluster](https://www.unicode.org/glossary/#grapheme_cluster).</span></span> <span data-ttu-id="c6a15-222">Odpowiedni termin w programie .NET to [element tekstowy](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span><span class="sxs-lookup"><span data-stu-id="c6a15-222">The equivalent term in .NET is [text element](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span></span>

<span data-ttu-id="c6a15-223">Rozważ `:::no-loc(string):::` wystąpienia "a", "o", "o" i " `👩🏽‍🚒` ".</span><span class="sxs-lookup"><span data-stu-id="c6a15-223">Consider the `:::no-loc(string):::` instances "a", "á", "á", and "`👩🏽‍🚒`".</span></span> <span data-ttu-id="c6a15-224">Jeśli system operacyjny obsługuje je zgodnie z definicją standardu Unicode, każde z tych `:::no-loc(string):::` wystąpień jest wyświetlane jako pojedynczy element tekstowy lub klaster Grapheme.</span><span class="sxs-lookup"><span data-stu-id="c6a15-224">If your operating system handles them as specified by the Unicode standard, each of these `:::no-loc(string):::` instances appears as a single text element or grapheme cluster.</span></span> <span data-ttu-id="c6a15-225">Jednak ostatnie dwa są reprezentowane przez więcej niż jeden punkt kodu wartości skalarnej.</span><span class="sxs-lookup"><span data-stu-id="c6a15-225">But the last two are represented by more than one scalar value code point.</span></span>

* <span data-ttu-id="c6a15-226">:::no-loc(string):::"A" jest reprezentowane przez jedną wartość skalarną i zawiera jedno `:::no-loc(char):::` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-226">The :::no-loc(string)::: "a" is represented by one scalar value and contains one `:::no-loc(char):::` instance.</span></span>

  * `U+0061 LATIN SMALL LETTER A`

* <span data-ttu-id="c6a15-227">"I" :::no-loc(string)::: jest reprezentowane przez jedną wartość skalarną i zawiera jedno `:::no-loc(char):::` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-227">The :::no-loc(string)::: "á" is represented by one scalar value and contains one `:::no-loc(char):::` instance.</span></span>

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* <span data-ttu-id="c6a15-228">:::no-loc(string):::"A" wygląda tak samo jak "", ale jest reprezentowane przez dwie wartości skalarne i zawiera dwa `:::no-loc(char):::` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-228">The :::no-loc(string)::: "á" looks the same as "á" but is represented by two scalar values and contains two `:::no-loc(char):::` instances.</span></span>

  * `U+0061 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* <span data-ttu-id="c6a15-229">Na koniec :::no-loc(string)::: " `👩🏽‍🚒` " jest reprezentowane przez cztery wartości skalarne i zawiera siedem `:::no-loc(char):::` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="c6a15-229">Finally, the :::no-loc(string)::: "`👩🏽‍🚒`" is represented by four scalar values and contains seven `:::no-loc(char):::` instances.</span></span>

  * <span data-ttu-id="c6a15-230">`U+1F469 WOMAN` (zakres dodatkowy, wymaga pary dwuskładnikowej)</span><span class="sxs-lookup"><span data-stu-id="c6a15-230">`U+1F469 WOMAN` (supplementary range, requires a surrogate pair)</span></span>
  * <span data-ttu-id="c6a15-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (zakres dodatkowy, wymaga pary dwuskładnikowej)</span><span class="sxs-lookup"><span data-stu-id="c6a15-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (supplementary range, requires a surrogate pair)</span></span>
  * `U+200D ZERO WIDTH JOINER`
  * <span data-ttu-id="c6a15-232">`U+1F692 FIRE ENGINE` (zakres dodatkowy, wymaga pary dwuskładnikowej)</span><span class="sxs-lookup"><span data-stu-id="c6a15-232">`U+1F692 FIRE ENGINE` (supplementary range, requires a surrogate pair)</span></span>

<span data-ttu-id="c6a15-233">W niektórych z powyższych przykładów — takich jak modyfikator łączenia akcentu lub modyfikator odcienia skórki — punkt kodu nie jest wyświetlany jako element autonomiczny na ekranie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-233">In some of the preceding examples - such as the combining accent modifier or the skin tone modifier - the code point does not display as a standalone element on the screen.</span></span> <span data-ttu-id="c6a15-234">Zamiast tego służy do modyfikowania wyglądu elementu tekstowego, który został wcześniej dołączony.</span><span class="sxs-lookup"><span data-stu-id="c6a15-234">Rather, it serves to modify the appearance of a text element that came before it.</span></span> <span data-ttu-id="c6a15-235">Te przykłady pokazują, że może przyjmować wiele wartości skalarnych, aby określić, co myślisz jako pojedynczy :::no-loc(char)::: klaster "acter" lub "Grapheme".</span><span class="sxs-lookup"><span data-stu-id="c6a15-235">These examples show that it might take multiple scalar values to make up what we think of as a single ":::no-loc(char):::acter," or "grapheme cluster."</span></span>

<span data-ttu-id="c6a15-236">Aby wyliczyć klastry Grapheme z `:::no-loc(string):::` , należy użyć <xref:System.Globalization.StringInfo> klasy, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c6a15-236">To enumerate the grapheme clusters of a `:::no-loc(string):::`, use the <xref:System.Globalization.StringInfo> class as shown in the following example.</span></span> <span data-ttu-id="c6a15-237">Jeśli znasz język SWIFT, `StringInfo` Typ .NET jest koncepcyjnie podobny do [ `:::no-loc(char):::acter` typu SWIFT](https://developer.apple.com/documentation/swift/:::no-loc(char):::acter).</span><span class="sxs-lookup"><span data-stu-id="c6a15-237">If you're familiar with Swift, the .NET `StringInfo` type is conceptually similar to [Swift's `:::no-loc(char):::acter` type](https://developer.apple.com/documentation/swift/:::no-loc(char):::acter).</span></span>

### <a name="example-count-no-locchar-no-locrune-and-text-element-instances"></a><span data-ttu-id="c6a15-238">Przykład: liczba :::no-loc(char)::: , :::no-loc(Rune)::: i wystąpienia elementu tekstowego</span><span class="sxs-lookup"><span data-stu-id="c6a15-238">Example: count :::no-loc(char):::, :::no-loc(Rune):::, and text element instances</span></span>

<span data-ttu-id="c6a15-239">W interfejsach API platformy .NET klaster Grapheme jest nazywany *elementem tekstowym*.</span><span class="sxs-lookup"><span data-stu-id="c6a15-239">In .NET APIs, a grapheme cluster is called a *text element*.</span></span> <span data-ttu-id="c6a15-240">Poniższa metoda pokazuje różnice między elementami `:::no-loc(char):::` , `:::no-loc(Rune):::` i wystąpieniami elementów tekstu w `:::no-loc(string):::` :</span><span class="sxs-lookup"><span data-stu-id="c6a15-240">The following method demonstrates the differences between `:::no-loc(char):::`, `:::no-loc(Rune):::`, and text element instances in a `:::no-loc(string):::`:</span></span>

<span data-ttu-id="c6a15-241">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/CountTextElements. cs" ID = "SnippetCountMethod"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-241">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::</span></span>

<span data-ttu-id="c6a15-242">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/CountTextElements. cs" ID = "SnippetCallCountMethod"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-242">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::</span></span>

<span data-ttu-id="c6a15-243">W przypadku uruchomienia tego kodu w .NET Framework lub .NET Core 3,1 lub starszym liczba elementów tekstowych dla znaku emoji zostanie wyświetlona `4` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-243">If you run this code in .NET Framework or .NET Core 3.1 or earlier, the text element count for the emoji shows `4`.</span></span> <span data-ttu-id="c6a15-244">Jest to spowodowane usterką w `StringInfo` klasie, która została naprawiona w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="c6a15-244">That is due to a bug in the `StringInfo` class that is fixed in .NET 5.</span></span>

### <a name="example-splitting-no-locstring-instances"></a><span data-ttu-id="c6a15-245">Przykład: dzielenie :::no-loc(string)::: wystąpień</span><span class="sxs-lookup"><span data-stu-id="c6a15-245">Example: splitting :::no-loc(string)::: instances</span></span>

<span data-ttu-id="c6a15-246">Podczas dzielenia `:::no-loc(string):::` wystąpień należy unikać dzielenia pary zastępczych i klastrów Grapheme.</span><span class="sxs-lookup"><span data-stu-id="c6a15-246">When splitting `:::no-loc(string):::` instances, avoid splitting surrogate pairs and grapheme clusters.</span></span> <span data-ttu-id="c6a15-247">Rozważmy następujący przykład nieprawidłowego kodu, który zamierza wstawiać podziały wierszy co 10 :::no-loc(char)::: acters w :::no-loc(string)::: :</span><span class="sxs-lookup"><span data-stu-id="c6a15-247">Consider the following example of incorrect code, which intends to insert line breaks every 10 :::no-loc(char):::acters in a :::no-loc(string)::::</span></span>

<span data-ttu-id="c6a15-248">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/InsertNewlines. cs" ID = "SnippetBadExample"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-248">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="c6a15-249">Ponieważ ten kod wylicza `:::no-loc(char):::` wystąpienia, para dwuskładnikowa, która ma miejsce na obramowanie międzystrefowe, `:::no-loc(char):::` zostanie podzielona i zostanie dodany nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="c6a15-249">Because this code enumerates `:::no-loc(char):::` instances, a surrogate pair that happens to straddle a 10-`:::no-loc(char):::` boundary will be split and a newline injected between them.</span></span> <span data-ttu-id="c6a15-250">W tym wstawieniu wprowadzono uszkodzenia danych, ponieważ punkty kodu surogatu są istotne tylko jako pary.</span><span class="sxs-lookup"><span data-stu-id="c6a15-250">This insertion introduces data corruption, because surrogate code points are meaningful only as pairs.</span></span>

<span data-ttu-id="c6a15-251">Potencjalne uszkodzenie danych nie jest eliminowane w przypadku wyliczania `:::no-loc(Rune):::` wystąpień (wartości skalarnych) zamiast `:::no-loc(char):::` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="c6a15-251">The potential for data corruption isn't eliminated if you enumerate `:::no-loc(Rune):::` instances (scalar values) instead of `:::no-loc(char):::` instances.</span></span> <span data-ttu-id="c6a15-252">Zestaw `:::no-loc(Rune):::` wystąpień może utworzyć klaster Grapheme, który ma międzystrefę 10 `:::no-loc(char):::` granic.</span><span class="sxs-lookup"><span data-stu-id="c6a15-252">A set of `:::no-loc(Rune):::` instances might make up a grapheme cluster that straddles a 10-`:::no-loc(char):::` boundary.</span></span> <span data-ttu-id="c6a15-253">Jeśli zestaw klastrów Grapheme jest podzielony, nie można go poprawnie zinterpretować.</span><span class="sxs-lookup"><span data-stu-id="c6a15-253">If the grapheme cluster set is split up, it can't be interpreted correctly.</span></span>

<span data-ttu-id="c6a15-254">Lepszym rozwiązaniem jest przerwanie :::no-loc(string)::: przez zliczanie klastrów Grapheme lub elementów tekstowych, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="c6a15-254">A better approach is to break the :::no-loc(string)::: by counting grapheme clusters, or text elements, as in the following example:</span></span>

<span data-ttu-id="c6a15-255">::: Code Language = "CSharp" source = "urywki/ :::no-loc(char)::: acter-Encoding-Introduction/CSharp/InsertNewlines. cs" ID = "SnippetGoodExample"::</span><span class="sxs-lookup"><span data-stu-id="c6a15-255">:::code language="csharp" source="snippets/:::no-loc(char):::acter-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::</span></span>

<span data-ttu-id="c6a15-256">Jak wspomniano wcześniej, jednak w implementacjach platformy .NET innej niż .NET 5 `StringInfo` Klasa może nieprawidłowo obsłużyć niektóre klastry Grapheme.</span><span class="sxs-lookup"><span data-stu-id="c6a15-256">As noted earlier, however, in implementations of .NET other than .NET 5, the `StringInfo` class might handle some grapheme clusters incorrectly.</span></span>

## <a name="utf-8-and-utf-32"></a><span data-ttu-id="c6a15-257">UTF-8 i UTF-32</span><span class="sxs-lookup"><span data-stu-id="c6a15-257">UTF-8 and UTF-32</span></span>

<span data-ttu-id="c6a15-258">Poprzednie sekcje skupiające się na kodowaniu UTF-16, ponieważ są używane przez platformę .NET do kodowania `:::no-loc(string):::` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="c6a15-258">The preceding sections focused on UTF-16 because that's what .NET uses to encode `:::no-loc(string):::` instances.</span></span> <span data-ttu-id="c6a15-259">Istnieją inne systemy kodowania dla standardu Unicode- [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) i [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span><span class="sxs-lookup"><span data-stu-id="c6a15-259">There are other encoding systems for Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) and [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span></span> <span data-ttu-id="c6a15-260">Te kodowania wykorzystują odpowiednio 8-bitowe jednostki kodu i 32-bitowe jednostki kodu.</span><span class="sxs-lookup"><span data-stu-id="c6a15-260">These encodings use 8-bit code units and 32-bit code units, respectively.</span></span>

<span data-ttu-id="c6a15-261">Podobnie jak w przypadku UTF-16, UTF-8 wymaga wielu jednostek kodu do reprezentowania niektórych wartości skalarnych Unicode.</span><span class="sxs-lookup"><span data-stu-id="c6a15-261">Like UTF-16, UTF-8 requires multiple code units to represent some Unicode scalar values.</span></span> <span data-ttu-id="c6a15-262">Kodowanie UTF-32 może reprezentować dowolną wartość skalarną w jednej jednostce kodu 32-bitowej.</span><span class="sxs-lookup"><span data-stu-id="c6a15-262">UTF-32 can represent any scalar value in a single 32-bit code unit.</span></span>

<span data-ttu-id="c6a15-263">Poniżej przedstawiono kilka przykładów przedstawiających sposób reprezentowania tego samego punktu kodu Unicode w każdym z tych trzech systemów kodowania Unicode:</span><span class="sxs-lookup"><span data-stu-id="c6a15-263">Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span></span>

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

<span data-ttu-id="c6a15-264">Jak wspomniano wcześniej, pojedyncza jednostka kodu UTF-16 z [pary zastępczej](#surrogate-pairs) jest bezproblemowa.</span><span class="sxs-lookup"><span data-stu-id="c6a15-264">As noted earlier, a single UTF-16 code unit from a [surrogate pair](#surrogate-pairs) is meaningless by itself.</span></span> <span data-ttu-id="c6a15-265">W ten sam sposób pojedyncza jednostka kodu UTF-8 jest bezużyteczne, jeśli jest w sekwencji dwóch, trzech lub czterech używanych do obliczania wartości skalarnej.</span><span class="sxs-lookup"><span data-stu-id="c6a15-265">In the same way, a single UTF-8 code unit is meaningless by itself if it's in a sequence of two, three, or four used to calculate a scalar value.</span></span>

### <a name="endianness"></a><span data-ttu-id="c6a15-266">Endian</span><span class="sxs-lookup"><span data-stu-id="c6a15-266">Endianness</span></span>

<span data-ttu-id="c6a15-267">W programie .NET jednostki kodu UTF-16 :::no-loc(string)::: są przechowywane w ciągłej pamięci jako sekwencja 16-bitowych liczb całkowitych ( `:::no-loc(char):::` wystąpień).</span><span class="sxs-lookup"><span data-stu-id="c6a15-267">In .NET, the UTF-16 code units of a :::no-loc(string)::: are stored in contiguous memory as a sequence of 16-bit integers (`:::no-loc(char):::` instances).</span></span> <span data-ttu-id="c6a15-268">Bity poszczególnych jednostek kodu są ustalane w zależności od liczby [bajtów](https://en.wikipedia.org/wiki/Endianness) bieżącej architektury.</span><span class="sxs-lookup"><span data-stu-id="c6a15-268">The bits of individual code units are laid out according to the [endianness](https://en.wikipedia.org/wiki/Endianness) of the current architecture.</span></span>

<span data-ttu-id="c6a15-269">W przypadku architektury little-endian :::no-loc(string)::: złożone z punktów kodu UTF-16 `[ D801 DCCC ]` zostałyby ustalone w pamięci jako bajty `[ 0x01, 0xD8, 0xCC, 0xDC ]` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-269">On a little-endian architecture, the :::no-loc(string)::: consisting of the UTF-16 code points `[ D801 DCCC ]` would be laid out in memory as the bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span></span> <span data-ttu-id="c6a15-270">W przypadku architektury big-endian :::no-loc(string)::: można ją określić w pamięci jako bajty `[ 0xD8, 0x01, 0xDC, 0xCC ]` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-270">On a big-endian architecture that same :::no-loc(string)::: would be laid out in memory as the bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span></span>

<span data-ttu-id="c6a15-271">Systemy komputerowe, które komunikują się ze sobą, muszą wyrazić zgodę na reprezentację danych przekraczających sieć.</span><span class="sxs-lookup"><span data-stu-id="c6a15-271">Computer systems that communicate with each other must agree on the representation of data crossing the wire.</span></span> <span data-ttu-id="c6a15-272">Większość protokołów sieciowych używa kodowania UTF-8 jako standard podczas przesyłania tekstu, częściowo, aby uniknąć problemów, które mogą wynikać z komputera z dużą liczbą bajtów, komunikując się z komputerem o małej przepustowości.</span><span class="sxs-lookup"><span data-stu-id="c6a15-272">Most network protocols use UTF-8 as a standard when transmitting text, partly to avoid issues that might result from a big-endian machine communicating with a little-endian machine.</span></span> <span data-ttu-id="c6a15-273">:::no-loc(string):::Składowe składające się z punktów kodu UTF-8 `[ F0 90 93 8C ]` będą zawsze reprezentowane jako bajty, `[ 0xF0, 0x90, 0x93, 0x8C ]` niezależnie od liczby bajtów.</span><span class="sxs-lookup"><span data-stu-id="c6a15-273">The :::no-loc(string)::: consisting of the UTF-8 code points `[ F0 90 93 8C ]` will always be represented as the bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` regardless of endianness.</span></span>

<span data-ttu-id="c6a15-274">Aby użyć UTF-8 do przesyłania tekstu, aplikacje .NET często używają kodu, takiego jak Poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="c6a15-274">To use UTF-8 for transmitting text, .NET applications often use code like the following example:</span></span>

```csharp
:::no-loc(string)::: :::no-loc(string):::ToWrite = GetString();
byte[] :::no-loc(string):::AsUtf8Bytes = Encoding.UTF8.GetBytes(:::no-loc(string):::ToWrite);
await outputStream.WriteAsync(:::no-loc(string):::AsUtf8Bytes, 0, :::no-loc(string):::AsUtf8Bytes.Length);
```

<span data-ttu-id="c6a15-275">W poprzednim przykładzie metoda [Encoding. UTF8. GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) dekoduje kod UTF-16 `:::no-loc(string):::` do serii wartości skalarnych Unicode, a następnie ponownie koduje te wartości skalarne na UTF-8 i umieszcza wyniki sekwencji w `byte` tablicy.</span><span class="sxs-lookup"><span data-stu-id="c6a15-275">In the preceding example, the method [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodes the UTF-16 `:::no-loc(string):::` back into a series of Unicode scalar values, then it re-encodes those scalar values into UTF-8 and places the resulting sequence into a `byte` array.</span></span> <span data-ttu-id="c6a15-276">Metoda [Encoding. UTF8. GetString](xref:System.Text.UTF8Encoding.GetString%2A) wykonuje odwrotną transformację, konwertując tablicę UTF-8 `byte` na UTF-16 `:::no-loc(string):::` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-276">The method [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) performs the opposite transformation, converting a UTF-8 `byte` array to a UTF-16 `:::no-loc(string):::`.</span></span>

> [!WARNING]
> <span data-ttu-id="c6a15-277">Ponieważ UTF-8 jest commonplace w Internecie, może być skłonny do odczytu nieprzetworzonych bajtów z sieci i do traktowania danych, tak jakby była to UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c6a15-277">Since UTF-8 is commonplace on the internet, it may be tempting to read raw bytes from the wire and to treat the data as if it were UTF-8.</span></span> <span data-ttu-id="c6a15-278">Należy jednak sprawdzić, czy jest on rzeczywiście poprawnie sformułowany.</span><span class="sxs-lookup"><span data-stu-id="c6a15-278">However, you should validate that it is indeed well-formed.</span></span> <span data-ttu-id="c6a15-279">Złośliwy klient może przesłać do usługi źle sformułowany format UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c6a15-279">A malicious client might submit ill-formed UTF-8 to your service.</span></span> <span data-ttu-id="c6a15-280">Jeśli te dane są używane w taki sposób, jakby były poprawnie sformułowane, może to spowodować błędy lub luki w zabezpieczeniach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c6a15-280">If you operate on that data as if it were well-formed, it could cause errors or security holes in your application.</span></span> <span data-ttu-id="c6a15-281">Aby sprawdzić poprawność danych UTF-8, można użyć metody takiej jak `Encoding.UTF8.GetString` , która przeprowadza walidację podczas konwertowania danych przychodzących na `:::no-loc(string):::` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-281">To validate UTF-8 data, you can use a method like `Encoding.UTF8.GetString`, which will perform validation while converting the incoming data to a `:::no-loc(string):::`.</span></span>

### <a name="well-formed-encoding"></a><span data-ttu-id="c6a15-282">Poprawnie sformułowane kodowanie</span><span class="sxs-lookup"><span data-stu-id="c6a15-282">Well-formed encoding</span></span>

<span data-ttu-id="c6a15-283">Poprawnie sformułowane kodowanie Unicode to :::no-loc(string)::: jednostki kodu, które można zdekodować w sposób niejednoznaczny i bez błędu do sekwencji wartości skalarnych Unicode.</span><span class="sxs-lookup"><span data-stu-id="c6a15-283">A well-formed Unicode encoding is a :::no-loc(string)::: of code units that can be decoded unambiguously and without error into a sequence of Unicode scalar values.</span></span> <span data-ttu-id="c6a15-284">Poprawnie sformułowane dane można transkodować bez ograniczeń i z powrotem między UTF-8, UTF-16 i UTF-32.</span><span class="sxs-lookup"><span data-stu-id="c6a15-284">Well-formed data can be transcoded freely back and forth between UTF-8, UTF-16, and UTF-32.</span></span>

<span data-ttu-id="c6a15-285">Pytanie, czy sekwencja kodowania jest poprawnie sformułowana, czy nie jest niezwiązana z przydziałami architektury maszyny.</span><span class="sxs-lookup"><span data-stu-id="c6a15-285">The question of whether an encoding sequence is well-formed or not is unrelated to the endianness of a machine's architecture.</span></span> <span data-ttu-id="c6a15-286">Nieprawidłowo sformułowana sekwencja UTF-8 jest źle sformułowana w taki sam sposób na maszynach big-endian i little-endian.</span><span class="sxs-lookup"><span data-stu-id="c6a15-286">An ill-formed UTF-8 sequence is ill-formed in the same way on both big-endian and little-endian machines.</span></span>

<span data-ttu-id="c6a15-287">Poniżej przedstawiono kilka przykładów niewłaściwie sformułowanych kodowań:</span><span class="sxs-lookup"><span data-stu-id="c6a15-287">Here are some examples of ill-formed encodings:</span></span>

* <span data-ttu-id="c6a15-288">W UTF-8 sekwencja `[ 6C C2 61 ]` jest źle sformułowana, ponieważ `C2` nie może następować po niej `61` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-288">In UTF-8, the sequence `[ 6C C2 61 ]` is ill-formed because `C2` cannot be followed by `61`.</span></span>

* <span data-ttu-id="c6a15-289">W UTF-16, sekwencja `[ DC00 DD00 ]` (lub, w języku C#, :::no-loc(string)::: `"\udc00\udd00"` ) jest źle sformułowana, ponieważ dolny Surogat `DC00` nie może następować po drugim dolnym surogatie `DD00` .</span><span class="sxs-lookup"><span data-stu-id="c6a15-289">In UTF-16, the sequence `[ DC00 DD00 ]` (or, in C#, the :::no-loc(string)::: `"\udc00\udd00"`) is ill-formed because the low surrogate `DC00` cannot be followed by another low surrogate `DD00`.</span></span>

* <span data-ttu-id="c6a15-290">W UTF-32 sekwencja `[ 0011ABCD ]` jest źle sformułowana, ponieważ `0011ABCD` znajduje się poza zakresem wartości skalarnych Unicode.</span><span class="sxs-lookup"><span data-stu-id="c6a15-290">In UTF-32, the sequence `[ 0011ABCD ]` is ill-formed because `0011ABCD` is outside the range of Unicode scalar values.</span></span>

<span data-ttu-id="c6a15-291">W programie .NET `:::no-loc(string):::` wystąpienia prawie zawsze zawierają poprawnie sformułowane dane UTF-16, ale nie są one gwarantowane.</span><span class="sxs-lookup"><span data-stu-id="c6a15-291">In .NET, `:::no-loc(string):::` instances almost always contain well-formed UTF-16 data, but that isn't guaranteed.</span></span> <span data-ttu-id="c6a15-292">W poniższych przykładach pokazano prawidłowy kod w języku C#, który tworzy nieprawidłowo sformułowane dane UTF-16 w `:::no-loc(string):::` wystąpieniach.</span><span class="sxs-lookup"><span data-stu-id="c6a15-292">The following examples show valid C# code that creates ill-formed UTF-16 data in `:::no-loc(string):::` instances.</span></span>

* <span data-ttu-id="c6a15-293">Nieprawidłowo sformułowany literał:</span><span class="sxs-lookup"><span data-stu-id="c6a15-293">An ill-formed literal:</span></span>

  ```csharp
  const :::no-loc(string)::: s = "\ud800";
  ```

* <span data-ttu-id="c6a15-294">Sub :::no-loc(string)::: dzieląca parę zastępczą:</span><span class="sxs-lookup"><span data-stu-id="c6a15-294">A sub:::no-loc(string)::: that splits up a surrogate pair:</span></span>

  ```csharp
  :::no-loc(string)::: x = "\ud83e\udd70"; // "🥰"
  :::no-loc(string)::: y = x.Sub:::no-loc(string):::(1, 1); // "\udd70" standalone low surrogate
  ```

<span data-ttu-id="c6a15-295">Interfejsy API, takie jak [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) nigdy nie zwracają źle sformułowane `:::no-loc(string):::` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c6a15-295">APIs like [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) never return ill-formed `:::no-loc(string):::` instances.</span></span> <span data-ttu-id="c6a15-296">`Encoding.GetString``Encoding.GetBytes`metody i wykrywają źle sformułowane sekwencje w danych wejściowych i wykonują :::no-loc(char)::: podstawienie acter podczas generowania danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="c6a15-296">`Encoding.GetString` and `Encoding.GetBytes` methods detect ill-formed sequences in the input and perform :::no-loc(char):::acter substitution when generating the output.</span></span> <span data-ttu-id="c6a15-297">Jeśli na przykład [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) w danych wejściowych zostanie wyświetlony bajt inny niż ASCII (poza zakresem u + 0000.. u + 007F), wstawiany jest znak "?" w zwracanym `:::no-loc(string):::` wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="c6a15-297">For example, if [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) sees a non-ASCII byte in the input (outside the range U+0000..U+007F), it inserts a '?' into the returned `:::no-loc(string):::` instance.</span></span> <span data-ttu-id="c6a15-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) zamienia źle sformułowane sekwencje UTF-8 z `U+FFFD REPLACEMENT CHARACTER ('�')` w zwracanym `:::no-loc(string):::` wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="c6a15-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) replaces ill-formed UTF-8 sequences with `U+FFFD REPLACEMENT CHARACTER ('�')` in the returned `:::no-loc(string):::` instance.</span></span> <span data-ttu-id="c6a15-299">Aby uzyskać więcej informacji, zobacz [standard Unicode](https://www.unicode.org/versions/latest/), sekcje 5,22 i 3,9.</span><span class="sxs-lookup"><span data-stu-id="c6a15-299">For more information, see [the Unicode Standard](https://www.unicode.org/versions/latest/), Sections 5.22 and 3.9.</span></span>

<span data-ttu-id="c6a15-300">Wbudowane `Encoding` klasy można również skonfigurować tak, aby zgłaszać wyjątek, a nie :::no-loc(char)::: przestawiać acter, gdy widoczne są źle sformułowane sekwencje.</span><span class="sxs-lookup"><span data-stu-id="c6a15-300">The built-in `Encoding` classes can also be configured to throw an exception rather than perform :::no-loc(char):::acter substitution when ill-formed sequences are seen.</span></span> <span data-ttu-id="c6a15-301">Takie podejście jest często stosowane w aplikacjach z uwzględnieniem zabezpieczeń, w których :::no-loc(char)::: podstawianie acter może być niedopuszczalne.</span><span class="sxs-lookup"><span data-stu-id="c6a15-301">This approach is often used in security-sensitive applications where :::no-loc(char):::acter substitution might not be acceptable.</span></span>

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
:::no-loc(string)::: asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

<span data-ttu-id="c6a15-302">Aby uzyskać informacje o sposobach korzystania z wbudowanych `Encoding` klas, zobacz [How to use :::no-loc(char)::: acter Encoding Classes in .NET](:::no-loc(char):::acter-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="c6a15-302">For information about how to use the built-in `Encoding` classes, see [How to use :::no-loc(char):::acter encoding classes in .NET](:::no-loc(char):::acter-encoding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6a15-303">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c6a15-303">See also</span></span>

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.:::no-loc(Rune):::>
- [<span data-ttu-id="c6a15-304">Globalizacja i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="c6a15-304">Globalization and Localization</span></span>](../globalization-localization/index.md)
