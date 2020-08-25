---
title: Wprowadzenie do char kodowania acter w programie .NET
description: Dowiedz się więcej char na temat kodowania i dekodowania acter w programie .NET.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: d1f9878c7e7c07944a943c0b05e557ceaa5d1b2f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812123"
---
# <a name="character-encoding-in-net"></a><span data-ttu-id="05e10-103">Kodowanie znaków na platformie .NET</span><span class="sxs-lookup"><span data-stu-id="05e10-103">Character encoding in .NET</span></span>

<span data-ttu-id="05e10-104">Ten artykuł zawiera wprowadzenie do char systemów kodowania acter, które są używane przez platformę .NET.</span><span class="sxs-lookup"><span data-stu-id="05e10-104">This article provides an introduction to character encoding systems that are used by .NET.</span></span> <span data-ttu-id="05e10-105">W tym artykule wyjaśniono <xref:System.String> , jak,, <xref:System.Char> <xref:System.Text.Rune> i <xref:System.Globalization.StringInfo> typy działają z Unicode, UTF-16 i UTF-8.</span><span class="sxs-lookup"><span data-stu-id="05e10-105">The article explains how the <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune>, and <xref:System.Globalization.StringInfo> types work with Unicode, UTF-16, and UTF-8.</span></span>

<span data-ttu-id="05e10-106">Termin \* char acter\* jest używany w tym miejscu w ogólnym sensie, *co czytnik jest postrzegany jako pojedynczy element wyświetlania*.</span><span class="sxs-lookup"><span data-stu-id="05e10-106">The term *character* is used here in the general sense of *what a reader perceives as a single display element*.</span></span> <span data-ttu-id="05e10-107">Typowe przykłady to litera "a", symbol "@" i Emoji " 🐂 ".</span><span class="sxs-lookup"><span data-stu-id="05e10-107">Common examples are the letter "a", the symbol "@", and the emoji "🐂".</span></span> <span data-ttu-id="05e10-108">Czasami wygląda na to char , że jeden acter jest w rzeczywistości składający się z wielu niezależnych elementów wyświetlanych, ponieważ sekcja w [klastrach Grapheme](#grapheme-clusters) objaśnia.</span><span class="sxs-lookup"><span data-stu-id="05e10-108">Sometimes what looks like one character is actually composed of multiple independent display elements, as the section on [grapheme clusters](#grapheme-clusters) explains.</span></span>

## <a name="the-no-locstring-and-no-locchar-types"></a><span data-ttu-id="05e10-109">stringTypy i char</span><span class="sxs-lookup"><span data-stu-id="05e10-109">The string and char types</span></span>

<span data-ttu-id="05e10-110">Wystąpienie [string](xref:System.String) klasy reprezentuje jakiś tekst.</span><span class="sxs-lookup"><span data-stu-id="05e10-110">An instance of the [string](xref:System.String) class represents some text.</span></span> <span data-ttu-id="05e10-111">A `string` jest logicznie sekwencją wartości 16-bitowych, z których każdy jest wystąpieniem [char](xref:System.Char) struktury.</span><span class="sxs-lookup"><span data-stu-id="05e10-111">A `string` is logically a sequence of 16-bit values, each of which is an instance of the [char](xref:System.Char) struct.</span></span> <span data-ttu-id="05e10-112">[ string . Właściwość length](xref:System.String.Length) zwraca liczbę `char` wystąpień w `string` wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="05e10-112">The [string.Length](xref:System.String.Length) property returns the number of `char` instances in the `string` instance.</span></span>

<span data-ttu-id="05e10-113">Poniższa funkcja Przykładowa drukuje wartości w notacji szesnastkowej wszystkich `char` wystąpień w `string` :</span><span class="sxs-lookup"><span data-stu-id="05e10-113">The following sample function prints out the values in hexadecimal notation of all the `char` instances in a `string`:</span></span>

<span data-ttu-id="05e10-114">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/PrintStringChars. cs" ID = "SnippetPrintChars"::</span><span class="sxs-lookup"><span data-stu-id="05e10-114">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::</span></span>

<span data-ttu-id="05e10-115">Przekaż string "Hello" do tej funkcji i uzyskasz następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="05e10-115">Pass the string "Hello" to this function, and you get the following output:</span></span>

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

<span data-ttu-id="05e10-116">Każdy char acter jest reprezentowany przez pojedynczą `char` wartość.</span><span class="sxs-lookup"><span data-stu-id="05e10-116">Each character is represented by a single `char` value.</span></span> <span data-ttu-id="05e10-117">Ten wzorzec ma wartość true w przypadku większości języków świata.</span><span class="sxs-lookup"><span data-stu-id="05e10-117">That pattern holds true for most of the world's languages.</span></span> <span data-ttu-id="05e10-118">Na przykład poniżej przedstawiono dane wyjściowe dla dwóch chińskich char acters, takie jak *nǐ hǎo* i średnia *Hello*:</span><span class="sxs-lookup"><span data-stu-id="05e10-118">For example, here's the output for two Chinese characters that sound like *nǐ hǎo* and mean *Hello*:</span></span>

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

<span data-ttu-id="05e10-119">Jednakże w przypadku niektórych języków i dla niektórych symboli i znaków emoji `char` do reprezentowania pojedynczego acter są dwa wystąpienia char .</span><span class="sxs-lookup"><span data-stu-id="05e10-119">However, for some languages and for some symbols and emoji, it takes two `char` instances to represent a single character.</span></span> <span data-ttu-id="05e10-120">Na przykład Porównaj char acters i `char` wystąpienia w wyrazie oznaczające *Osage* w języku Osage:</span><span class="sxs-lookup"><span data-stu-id="05e10-120">For example, compare the characters and `char` instances in the word that means *Osage* in the Osage language:</span></span>

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

<span data-ttu-id="05e10-121">W poprzednim przykładzie każdy acter, char z wyjątkiem miejsca, jest reprezentowany przez dwa `char` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05e10-121">In the preceding example, each character except the space is represented by two `char` instances.</span></span>

<span data-ttu-id="05e10-122">Pojedynczy emoji Unicode jest również reprezentowany przez dwa `char` s, jak pokazano w poniższym przykładzie pokazujący OX-emoji:</span><span class="sxs-lookup"><span data-stu-id="05e10-122">A single Unicode emoji is also represented by two `char`s, as seen in the following example showing an ox emoji:</span></span>

```output
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

<span data-ttu-id="05e10-123">Te przykłady pokazują, że wartość `string.Length` , która wskazuje liczbę `char` wystąpień, nie zawsze wskazuje liczbę wyświetlanych char acters.</span><span class="sxs-lookup"><span data-stu-id="05e10-123">These examples show that the value of `string.Length`, which indicates the number of `char` instances, doesn't necessarily indicate the number of displayed characters.</span></span> <span data-ttu-id="05e10-124">Pojedyncze `char` wystąpienie przez siebie samo nie musi reprezentować char acter.</span><span class="sxs-lookup"><span data-stu-id="05e10-124">A single `char` instance by itself doesn't necessarily represent a character.</span></span>

<span data-ttu-id="05e10-125">`char`Pary, które są mapowane na pojedyncze char acter są nazywane *parami wieloskładnikowym*.</span><span class="sxs-lookup"><span data-stu-id="05e10-125">The `char` pairs that map to a single character are called *surrogate pairs*.</span></span> <span data-ttu-id="05e10-126">Aby zrozumieć, jak działają, należy zrozumieć kodowanie Unicode i UTF-16.</span><span class="sxs-lookup"><span data-stu-id="05e10-126">To understand how they work, you need to understand Unicode and UTF-16 encoding.</span></span>

## <a name="unicode-code-points"></a><span data-ttu-id="05e10-127">Punkty kodu Unicode</span><span class="sxs-lookup"><span data-stu-id="05e10-127">Unicode code points</span></span>

<span data-ttu-id="05e10-128">Unicode jest międzynarodowym standardem kodowania do użycia na różnych platformach i w różnych językach i skryptach.</span><span class="sxs-lookup"><span data-stu-id="05e10-128">Unicode is an international encoding standard for use on various platforms and with various languages and scripts.</span></span>

<span data-ttu-id="05e10-129">Standard Unicode definiuje ponad 1 100 000 [punktów kodów](https://www.unicode.org/glossary/#code_point).</span><span class="sxs-lookup"><span data-stu-id="05e10-129">The Unicode Standard defines over 1.1 million [code points](https://www.unicode.org/glossary/#code_point).</span></span> <span data-ttu-id="05e10-130">Punkt kodu jest wartością całkowitą, która może być z zakresu od 0 do `U+10FFFF` (dziesiętne 1 114 111).</span><span class="sxs-lookup"><span data-stu-id="05e10-130">A code point is an integer value that can range from 0 to `U+10FFFF` (decimal 1,114,111).</span></span> <span data-ttu-id="05e10-131">Niektóre punkty kodu są przypisywane do liter, symboli lub emoji.</span><span class="sxs-lookup"><span data-stu-id="05e10-131">Some code points are assigned to letters, symbols, or emoji.</span></span> <span data-ttu-id="05e10-132">Inne są przypisane do akcji kontrolujących sposób wyświetlania tekstu lub char acters, na przykład z wyprzedzeniem do nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="05e10-132">Others are assigned to actions that control how text or characters are displayed, such as advance to a new line.</span></span> <span data-ttu-id="05e10-133">Wiele punktów kodowych nie jest jeszcze przypisanych.</span><span class="sxs-lookup"><span data-stu-id="05e10-133">Many code points are not yet assigned.</span></span>

<span data-ttu-id="05e10-134">Poniżej przedstawiono kilka przykładów przypisań punktów kodu z linkami do kodu Unicode char TS, w którym są wyświetlane:</span><span class="sxs-lookup"><span data-stu-id="05e10-134">Here are some examples of code point assignments, with links to Unicode charts in which they appear:</span></span>

|<span data-ttu-id="05e10-135">Liczba dziesiętna</span><span class="sxs-lookup"><span data-stu-id="05e10-135">Decimal</span></span>|<span data-ttu-id="05e10-136">Hex</span><span class="sxs-lookup"><span data-stu-id="05e10-136">Hex</span></span>       |<span data-ttu-id="05e10-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="05e10-137">Example</span></span>|<span data-ttu-id="05e10-138">Opis</span><span class="sxs-lookup"><span data-stu-id="05e10-138">Description</span></span>|
|------:|----------|-------|-----------|
|<span data-ttu-id="05e10-139">10</span><span class="sxs-lookup"><span data-stu-id="05e10-139">10</span></span>     | `U+000A` |<span data-ttu-id="05e10-140">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="05e10-140">N/A</span></span>| <span data-ttu-id="05e10-141">[KANAŁ INFORMACYJNY WIERSZA](https://www.unicode.org/charts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="05e10-141">[LINE FEED](https://www.unicode.org/charts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="05e10-142">65</span><span class="sxs-lookup"><span data-stu-id="05e10-142">65</span></span>     | `U+0061` | <span data-ttu-id="05e10-143">a</span><span class="sxs-lookup"><span data-stu-id="05e10-143">a</span></span> | <span data-ttu-id="05e10-144">[MAŁA LITERA A](https://www.unicode.org/charts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="05e10-144">[LATIN SMALL LETTER A](https://www.unicode.org/charts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="05e10-145">562</span><span class="sxs-lookup"><span data-stu-id="05e10-145">562</span></span>    | `U+0232` | <span data-ttu-id="05e10-146">Ȳ</span><span class="sxs-lookup"><span data-stu-id="05e10-146">Ȳ</span></span> | <span data-ttu-id="05e10-147">[WIELKA LITERA Y Z MACRON](https://www.unicode.org/charts/PDF/U0180.pdf)</span><span class="sxs-lookup"><span data-stu-id="05e10-147">[LATIN CAPITAL LETTER Y WITH MACRON](https://www.unicode.org/charts/PDF/U0180.pdf)</span></span> |
|<span data-ttu-id="05e10-148">68 675</span><span class="sxs-lookup"><span data-stu-id="05e10-148">68,675</span></span> | `U+10C43`| <span data-ttu-id="05e10-149">𐱃</span><span class="sxs-lookup"><span data-stu-id="05e10-149">𐱃</span></span> | <span data-ttu-id="05e10-150">[STARY TURKIC LETTER ORKHON NA](https://www.unicode.org/charts/PDF/U10C00.pdf)</span><span class="sxs-lookup"><span data-stu-id="05e10-150">[OLD TURKIC LETTER ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf)</span></span> |
|<span data-ttu-id="05e10-151">127 801</span><span class="sxs-lookup"><span data-stu-id="05e10-151">127,801</span></span>| `U+1F339`| <span data-ttu-id="05e10-152">🌹</span><span class="sxs-lookup"><span data-stu-id="05e10-152">🌹</span></span> | <span data-ttu-id="05e10-153">[RÓŻAny emoji](https://www.unicode.org/charts/PDF/U1F300.pdf)</span><span class="sxs-lookup"><span data-stu-id="05e10-153">[ROSE emoji](https://www.unicode.org/charts/PDF/U1F300.pdf)</span></span> |

<span data-ttu-id="05e10-154">Punkty kodu są zwykle określane przy użyciu składni `U+xxxx` , gdzie `xxxx` jest wartością całkowitą zakodowaną szesnastkowo.</span><span class="sxs-lookup"><span data-stu-id="05e10-154">Code points are customarily referred to by using the syntax `U+xxxx`, where `xxxx` is the hex-encoded integer value.</span></span>

<span data-ttu-id="05e10-155">W całym zakresie punktów kodu istnieją dwa podzakresy:</span><span class="sxs-lookup"><span data-stu-id="05e10-155">Within the full range of code points there are two subranges:</span></span>

* <span data-ttu-id="05e10-156">**Podstawowa płaszczyzna wielojęzyczna (BMP)** w zakresie `U+0000..U+FFFF` .</span><span class="sxs-lookup"><span data-stu-id="05e10-156">The **Basic Multilingual Plane (BMP)** in the range `U+0000..U+FFFF`.</span></span> <span data-ttu-id="05e10-157">Ten 16-bitowy zakres zapewnia 65 536 punktów kodów, wystarczających do pokrycia większości systemów pisania na świecie.</span><span class="sxs-lookup"><span data-stu-id="05e10-157">This 16-bit range provides 65,536 code points, enough to cover the majority of the world's writing systems.</span></span>
* <span data-ttu-id="05e10-158">**Dodatkowe punkty kodu** z zakresu `U+10000..U+10FFFF` .</span><span class="sxs-lookup"><span data-stu-id="05e10-158">**Supplementary code points** in the range `U+10000..U+10FFFF`.</span></span> <span data-ttu-id="05e10-159">Ten 21-bitowy zakres oferuje ponad milion dodatkowych punktów kodu, które mogą być używane dla mniej dobrze znanych języków i innych celów, takich jak emoji.</span><span class="sxs-lookup"><span data-stu-id="05e10-159">This 21-bit range provides more than a million additional code points that can be used for less well-known languages and other purposes such as emojis.</span></span>

<span data-ttu-id="05e10-160">Na poniższym diagramie przedstawiono relację między BMP i dodatkowymi punktami kodu.</span><span class="sxs-lookup"><span data-stu-id="05e10-160">The following diagram illustrates the relationship between the BMP and the supplementary code points.</span></span>

:::image type="content" source="media/:::nie-Loc (Char)::: acter-Encoding-Introduction/BMP-and-Supplementary. SVG "Alt-text =" BMP i dodatkowe punkty kodów ":::

## <a name="utf-16-code-units"></a><span data-ttu-id="05e10-162">Jednostki kodu UTF-16</span><span class="sxs-lookup"><span data-stu-id="05e10-162">UTF-16 code units</span></span>

<span data-ttu-id="05e10-163">16-bitowy format transformacji Unicode ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) to char system kodowania acter, który używa 16-bitowych *jednostek kodu* do reprezentowania punktów kodu Unicode.</span><span class="sxs-lookup"><span data-stu-id="05e10-163">16-bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) is a character encoding system that uses 16-bit *code units* to represent Unicode code points.</span></span> <span data-ttu-id="05e10-164">.NET używa kodowania UTF-16, aby zakodować tekst w `string` .</span><span class="sxs-lookup"><span data-stu-id="05e10-164">.NET uses UTF-16 to encode the text in a `string`.</span></span> <span data-ttu-id="05e10-165">`char`Wystąpienie reprezentuje jednostkę kodu 16-bitowego.</span><span class="sxs-lookup"><span data-stu-id="05e10-165">A `char` instance represents a 16-bit code unit.</span></span>

<span data-ttu-id="05e10-166">Pojedyncza jednostka kodowa 16-bitowa może reprezentować dowolny punkt kodu w 16-bitowym zakresie podstawowej płaszczyzny wielojęzycznej.</span><span class="sxs-lookup"><span data-stu-id="05e10-166">A single 16-bit code unit can represent any code point in the 16-bit range of the Basic Multilingual Plane.</span></span> <span data-ttu-id="05e10-167">Jednak w przypadku punktu kodu w dodatkowych zakresach `char` są potrzeby dwa wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05e10-167">But for a code point in the supplementary range, two `char` instances are needed.</span></span>

## <a name="surrogate-pairs"></a><span data-ttu-id="05e10-168">Pary zastępcze</span><span class="sxs-lookup"><span data-stu-id="05e10-168">Surrogate pairs</span></span>

<span data-ttu-id="05e10-169">Tłumaczenie wartości 2 16-bitowych na pojedynczą wartość 21-bitową jest obsługiwane przez specjalny zakres nazywany *surogatami punktów kodu*od `U+D800` do `U+DFFF` (dziesiętne 55 296 do 57 343) włącznie.</span><span class="sxs-lookup"><span data-stu-id="05e10-169">The translation of two 16-bit values to a single 21-bit value is facilitated by a special range called the *surrogate code points*, from `U+D800` to `U+DFFF` (decimal 55,296 to 57,343), inclusive.</span></span>

<span data-ttu-id="05e10-170">Na poniższym diagramie przedstawiono relację między kodem BMP i surogatem.</span><span class="sxs-lookup"><span data-stu-id="05e10-170">The following diagram illustrates the relationship between the BMP and the surrogate code points.</span></span>

:::image type="content" source="media/:::nie-Loc (Char)::: acter-Encoding-Introduction/BMP-and-Surrogate. SVG "Alt-text =" BMP i Surogat punktów kodowych ":::

<span data-ttu-id="05e10-172">Gdy do *górnego* punktu kodowego ( `U+D800..U+DBFF` ) bezpośrednio następuje *dolny* punkt kodowy ( `U+DC00..U+DFFF` ), para jest interpretowana jako dodatkowy punkt kodu przy użyciu następującej formuły:</span><span class="sxs-lookup"><span data-stu-id="05e10-172">When a *high surrogate* code point (`U+D800..U+DBFF`) is immediately followed by a *low surrogate* code point (`U+DC00..U+DFFF`), the pair is interpreted as a supplementary code point by using the following formula:</span></span>

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

<span data-ttu-id="05e10-173">W tej samej formule jest używana notacja dziesiętna:</span><span class="sxs-lookup"><span data-stu-id="05e10-173">Here's the same formula using decimal notation:</span></span>

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

<span data-ttu-id="05e10-174">*Górny* punkt kodu wieloskładnikowego nie ma wyższej wartości liczbowej niż *dolny* punkt kodowy.</span><span class="sxs-lookup"><span data-stu-id="05e10-174">A *high* surrogate code point doesn't have a higher number value than a *low* surrogate code point.</span></span> <span data-ttu-id="05e10-175">Górny punkt kodowy jest nazywany "wysoki", ponieważ jest używany do obliczania wyższej liczby 11 bitów pełnego zakresu kodów 21-bitowego.</span><span class="sxs-lookup"><span data-stu-id="05e10-175">The high surrogate code point is called "high" because it's used to calculate the higher-order 11 bits of the full 21-bit code point range.</span></span> <span data-ttu-id="05e10-176">Dolny punkt kodowy jest używany do obliczania 10 bitów o mniejszej kolejności.</span><span class="sxs-lookup"><span data-stu-id="05e10-176">The low surrogate code point is used to calculate the lower-order 10 bits.</span></span>

<span data-ttu-id="05e10-177">Na przykład rzeczywisty punkt kodu, który odnosi się do pary zastępczej `0xD83C` i `0xDF39`  jest obliczany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="05e10-177">For example, the actual code point that corresponds to the surrogate pair `0xD83C` and `0xDF39`  is computed as follows:</span></span>

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

<span data-ttu-id="05e10-178">To samo obliczenie przy użyciu notacji dziesiętnej:</span><span class="sxs-lookup"><span data-stu-id="05e10-178">Here's the same calculation using decimal notation:</span></span>

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

<span data-ttu-id="05e10-179">Powyższy przykład pokazuje, że `"\ud83c\udf39"` jest kodowanie UTF-16 `U+1F339 ROSE ('🌹')` powyżej wymienionego powyżej.</span><span class="sxs-lookup"><span data-stu-id="05e10-179">The preceding example demonstrates that `"\ud83c\udf39"` is the UTF-16 encoding of the `U+1F339 ROSE ('🌹')` code point mentioned earlier.</span></span>

## <a name="unicode-scalar-values"></a><span data-ttu-id="05e10-180">Wartości skalarne Unicode</span><span class="sxs-lookup"><span data-stu-id="05e10-180">Unicode scalar values</span></span>

<span data-ttu-id="05e10-181">Wyrażenie " [wartość skalarna Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) " odnosi się do wszystkich punktów kodu innych niż punkty zastępcze kodu.</span><span class="sxs-lookup"><span data-stu-id="05e10-181">The term [Unicode scalar value](https://www.unicode.org/glossary/#unicode_scalar_value) refers to all code points other than the surrogate code points.</span></span> <span data-ttu-id="05e10-182">Innymi słowy, wartość skalarna jest dowolnym punktem kodu przypisanym do char acter lub może być przypisywany char acter w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="05e10-182">In other words, a scalar value is any code point that is assigned a character or can be assigned a character in the future.</span></span> <span data-ttu-id="05e10-183">"Znak" odnosi się do wszystkich elementów, które można przypisać do punktu kodu, co obejmuje takie czynności jak akcje kontrolujące sposób wyświetlania tekstu lub char acters.</span><span class="sxs-lookup"><span data-stu-id="05e10-183">"Character" here refers to anything that can be assigned to a code point, which includes such things as actions that control how text or characters are displayed.</span></span>

<span data-ttu-id="05e10-184">Na poniższym diagramie przedstawiono punkty kodów wartości skalarnych.</span><span class="sxs-lookup"><span data-stu-id="05e10-184">The following diagram illustrates the scalar value code points.</span></span>

:::image type="content" source="media/:::nie-Loc (Char)::: acter-Encoding-Introduction/Scalar-Values. SVG "Alt-text =" wartości skalarnych ":::

### <a name="the-no-locrune-type-as-a-scalar-value"></a><span data-ttu-id="05e10-186">RuneTyp jako wartość skalarną</span><span class="sxs-lookup"><span data-stu-id="05e10-186">The Rune type as a scalar value</span></span>

<span data-ttu-id="05e10-187">Począwszy od platformy .NET Core 3,0, <xref:System.Text.Rune?displayProperty=fullName> Typ reprezentuje wartość skalarną Unicode.</span><span class="sxs-lookup"><span data-stu-id="05e10-187">Beginning with .NET Core 3.0, the <xref:System.Text.Rune?displayProperty=fullName> type represents a Unicode scalar value.</span></span> <span data-ttu-id="05e10-188">**`Rune` Program nie jest dostępny w programie .NET Core 2. x lub .NET Framework 4. x.**</span><span class="sxs-lookup"><span data-stu-id="05e10-188">**`Rune` is not available in .NET Core 2.x or .NET Framework 4.x.**</span></span>

<span data-ttu-id="05e10-189">`Rune`Konstruktory weryfikują, że wystąpienie wyniku jest prawidłową wartością skalarną Unicode, w przeciwnym razie zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="05e10-189">The `Rune` constructors validate that the resulting instance is a valid Unicode scalar value, otherwise they throw an exception.</span></span> <span data-ttu-id="05e10-190">Poniższy przykład pokazuje kod, który pomyślnie tworzy wystąpienia `Rune` wystąpień, ponieważ dane wejściowe reprezentują prawidłowe wartości skalarne:</span><span class="sxs-lookup"><span data-stu-id="05e10-190">The following example shows code that successfully instantiates `Rune` instances because the input represents valid scalar values:</span></span>

<span data-ttu-id="05e10-191">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/'utwórz Rune s.cs" ID = "SnippetValid"::</span><span class="sxs-lookup"><span data-stu-id="05e10-191">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::</span></span>

<span data-ttu-id="05e10-192">Poniższy przykład zgłasza wyjątek, ponieważ punkt kodu znajduje się w zakresie surogatu i nie jest częścią pary dwuskładnikowej:</span><span class="sxs-lookup"><span data-stu-id="05e10-192">The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span></span>

<span data-ttu-id="05e10-193">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/'utwórz Rune s.cs" ID = "SnippetInvalidSurrogate"::</span><span class="sxs-lookup"><span data-stu-id="05e10-193">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::</span></span>

<span data-ttu-id="05e10-194">Poniższy przykład zgłasza wyjątek, ponieważ punkt kodu znajduje się poza dodatkowym zakresem:</span><span class="sxs-lookup"><span data-stu-id="05e10-194">The following example throws an exception because the code point is beyond the supplementary range:</span></span>

<span data-ttu-id="05e10-195">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/'utwórz Rune s.cs" ID = "SnippetInvalidHigh"::</span><span class="sxs-lookup"><span data-stu-id="05e10-195">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::</span></span>

### <a name="no-locrune-usage-example-changing-letter-case"></a><span data-ttu-id="05e10-196">Rune przykład użycia: zmiana wielkości liter</span><span class="sxs-lookup"><span data-stu-id="05e10-196">Rune usage example: changing letter case</span></span>

<span data-ttu-id="05e10-197">Interfejs API, który przyjmuje `char` i zakłada, że pracuje z punktem kodu, który jest wartością skalarną, nie działa poprawnie, jeśli `char` pochodzi z pary zastępczej.</span><span class="sxs-lookup"><span data-stu-id="05e10-197">An API that takes a `char` and assumes it is working with a code point that is a scalar value doesn't work correctly if the `char` is from a surrogate pair.</span></span> <span data-ttu-id="05e10-198">Rozważmy na przykład następującą metodę, która wywołuje <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> na każdym z char string :</span><span class="sxs-lookup"><span data-stu-id="05e10-198">For example, consider the following method that calls <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> on each char in a string:</span></span>

<span data-ttu-id="05e10-199">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/ConvertToUpper. cs" ID = "SnippetBadExample"::</span><span class="sxs-lookup"><span data-stu-id="05e10-199">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="05e10-200">Jeśli `input` string zawiera małą literę Deseret `er` ( `𐑉` ), ten kod nie przekonwertuje go na wielkie litery ( `𐐡` ).</span><span class="sxs-lookup"><span data-stu-id="05e10-200">If the `input` string contains the lowercase Deseret letter `er` (`𐑉`), this code won't convert it to uppercase (`𐐡`).</span></span> <span data-ttu-id="05e10-201">Kod jest wywoływany `char.ToUpperInvariant` oddzielnie w każdym punkcie kodu zastępczego `U+D801` i `U+DC49` .</span><span class="sxs-lookup"><span data-stu-id="05e10-201">The code calls `char.ToUpperInvariant` separately on each surrogate code point, `U+D801` and `U+DC49`.</span></span> <span data-ttu-id="05e10-202">Ale `U+D801` nie ma wystarczających informacji, aby zidentyfikować je jako małą literę, więc `char.ToUpperInvariant` pozostawia ją samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="05e10-202">But `U+D801` doesn't have enough information by itself to identify it as a lowercase letter, so `char.ToUpperInvariant` leaves it alone.</span></span> <span data-ttu-id="05e10-203">Obsługuje to ten `U+DC49` sam sposób.</span><span class="sxs-lookup"><span data-stu-id="05e10-203">And it handles `U+DC49` the same way.</span></span> <span data-ttu-id="05e10-204">Wynikiem jest to, że małe litery "𐑉" w `input` string nie są konwertowane na wielkie litery "𐑉".</span><span class="sxs-lookup"><span data-stu-id="05e10-204">The result is that lowercase '𐑉' in the `input` string doesn't get converted to uppercase '𐐡'.</span></span>

<span data-ttu-id="05e10-205">Poniżej przedstawiono dwie opcje prawidłowej konwersji string na wielkie litery:</span><span class="sxs-lookup"><span data-stu-id="05e10-205">Here are two options for correctly converting a string to uppercase:</span></span>

* <span data-ttu-id="05e10-206">Wywołania <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> na wejściu string zamiast Iterowanie `char` przez- `char` .</span><span class="sxs-lookup"><span data-stu-id="05e10-206">Call <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> on the input string rather than iterating `char`-by-`char`.</span></span> <span data-ttu-id="05e10-207">`string.ToUpperInvariant`Metoda ma dostęp do obu części każdej pary surogatów, więc może prawidłowo obsługiwać wszystkie punkty kodu Unicode.</span><span class="sxs-lookup"><span data-stu-id="05e10-207">The `string.ToUpperInvariant` method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span></span>
* <span data-ttu-id="05e10-208">Wykonaj iterację przez wartości skalarne Unicode jako `Rune` wystąpienia `char` , a nie wystąpienia, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="05e10-208">Iterate through the Unicode scalar values as `Rune` instances instead of `char` instances, as shown in the following example.</span></span> <span data-ttu-id="05e10-209">Ponieważ `Rune` wystąpienie jest prawidłową wartością skalarną Unicode, można je przesłać do interfejsów API, które oczekują na wartość skalarną.</span><span class="sxs-lookup"><span data-stu-id="05e10-209">Since a `Rune` instance is a valid Unicode scalar value, it can be passed to APIs that expect to operate on a scalar value.</span></span> <span data-ttu-id="05e10-210">Na przykład wywoływanie, <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> jak pokazano w poniższym przykładzie, daje poprawne wyniki:</span><span class="sxs-lookup"><span data-stu-id="05e10-210">For example, calling <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> as shown in the following example gives correct results:</span></span>

  <span data-ttu-id="05e10-211">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/ConvertToUpper. cs" ID = "SnippetGoodExample"::</span><span class="sxs-lookup"><span data-stu-id="05e10-211">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::</span></span>

### <a name="other-no-locrune-apis"></a><span data-ttu-id="05e10-212">Inne Rune interfejsy API</span><span class="sxs-lookup"><span data-stu-id="05e10-212">Other Rune APIs</span></span>

<span data-ttu-id="05e10-213">`Rune`Typ uwidacznia analogowe wiele `char` interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="05e10-213">The `Rune` type exposes analogs of many of the `char` APIs.</span></span> <span data-ttu-id="05e10-214">Na przykład następujące metody dublowania statycznych interfejsów API w `char` typie:</span><span class="sxs-lookup"><span data-stu-id="05e10-214">For example, the following methods mirror static APIs on the `char` type:</span></span>

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

<span data-ttu-id="05e10-215">Aby pobrać nieprzetworzoną wartość skalarną z `Rune` wystąpienia, użyj <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="05e10-215">To get the raw scalar value from a `Rune` instance, use the <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="05e10-216">Aby skonwertować `Rune` wystąpienie z powrotem do sekwencji `char` s, użyj <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> metody lub.</span><span class="sxs-lookup"><span data-stu-id="05e10-216">To convert a `Rune` instance back to a sequence of `char`s, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> or the <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="05e10-217">Ponieważ każda wartość skalarna Unicode jest możliwa do zaprezentowania przez pojedynczą `char` lub dwuskładnikową parę, każde `Rune` wystąpienie może być reprezentowane przez co najwyżej 2 `char` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05e10-217">Since any Unicode scalar value is representable by a single `char` or by a surrogate pair, any `Rune` instance can be represented by at most 2 `char` instances.</span></span> <span data-ttu-id="05e10-218">Użyj <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> , aby zobaczyć, ile `char` wystąpień jest wymaganych do reprezentowania `Rune` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05e10-218">Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> to see how many `char` instances are required to represent a `Rune` instance.</span></span>

<span data-ttu-id="05e10-219">Aby uzyskać więcej informacji na temat `Rune` typu .NET, zobacz [ `Rune` Dokumentacja interfejsu API](xref:System.Text.Rune).</span><span class="sxs-lookup"><span data-stu-id="05e10-219">For more information about the .NET `Rune` type, see the [`Rune` API reference](xref:System.Text.Rune).</span></span>

## <a name="grapheme-clusters"></a><span data-ttu-id="05e10-220">Klastry Grapheme</span><span class="sxs-lookup"><span data-stu-id="05e10-220">Grapheme clusters</span></span>

<span data-ttu-id="05e10-221">Wygląda na to char , że jeden acter może wynikać z kombinacji wielu punktów kodowych, więc bardziej opisowy termin, który jest często używany zamiast " char acter", to [klaster Grapheme](https://www.unicode.org/glossary/#grapheme_cluster).</span><span class="sxs-lookup"><span data-stu-id="05e10-221">What looks like one character might result from a combination of multiple code points, so a more descriptive term that is often used in place of "character" is [grapheme cluster](https://www.unicode.org/glossary/#grapheme_cluster).</span></span> <span data-ttu-id="05e10-222">Odpowiedni termin w programie .NET to [element tekstowy](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span><span class="sxs-lookup"><span data-stu-id="05e10-222">The equivalent term in .NET is [text element](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span></span>

<span data-ttu-id="05e10-223">Rozważ `string` wystąpienia "a", "o", "o" i " `👩🏽‍🚒` ".</span><span class="sxs-lookup"><span data-stu-id="05e10-223">Consider the `string` instances "a", "á", "á", and "`👩🏽‍🚒`".</span></span> <span data-ttu-id="05e10-224">Jeśli system operacyjny obsługuje je zgodnie z definicją standardu Unicode, każde z tych `string` wystąpień jest wyświetlane jako pojedynczy element tekstowy lub klaster Grapheme.</span><span class="sxs-lookup"><span data-stu-id="05e10-224">If your operating system handles them as specified by the Unicode standard, each of these `string` instances appears as a single text element or grapheme cluster.</span></span> <span data-ttu-id="05e10-225">Jednak ostatnie dwa są reprezentowane przez więcej niż jeden punkt kodu wartości skalarnej.</span><span class="sxs-lookup"><span data-stu-id="05e10-225">But the last two are represented by more than one scalar value code point.</span></span>

* <span data-ttu-id="05e10-226">string"A" jest reprezentowane przez jedną wartość skalarną i zawiera jedno `char` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="05e10-226">The string "a" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+0061 LATIN SMALL LETTER A`

* <span data-ttu-id="05e10-227">"I" string jest reprezentowane przez jedną wartość skalarną i zawiera jedno `char` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="05e10-227">The string "á" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* <span data-ttu-id="05e10-228">string"A" wygląda tak samo jak "", ale jest reprezentowane przez dwie wartości skalarne i zawiera dwa `char` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05e10-228">The string "á" looks the same as "á" but is represented by two scalar values and contains two `char` instances.</span></span>

  * `U+0061 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* <span data-ttu-id="05e10-229">Na koniec string " `👩🏽‍🚒` " jest reprezentowane przez cztery wartości skalarne i zawiera siedem `char` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="05e10-229">Finally, the string "`👩🏽‍🚒`" is represented by four scalar values and contains seven `char` instances.</span></span>

  * <span data-ttu-id="05e10-230">`U+1F469 WOMAN` (zakres dodatkowy, wymaga pary dwuskładnikowej)</span><span class="sxs-lookup"><span data-stu-id="05e10-230">`U+1F469 WOMAN` (supplementary range, requires a surrogate pair)</span></span>
  * <span data-ttu-id="05e10-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (zakres dodatkowy, wymaga pary dwuskładnikowej)</span><span class="sxs-lookup"><span data-stu-id="05e10-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (supplementary range, requires a surrogate pair)</span></span>
  * `U+200D ZERO WIDTH JOINER`
  * <span data-ttu-id="05e10-232">`U+1F692 FIRE ENGINE` (zakres dodatkowy, wymaga pary dwuskładnikowej)</span><span class="sxs-lookup"><span data-stu-id="05e10-232">`U+1F692 FIRE ENGINE` (supplementary range, requires a surrogate pair)</span></span>

<span data-ttu-id="05e10-233">W niektórych z powyższych przykładów — takich jak modyfikator łączenia akcentu lub modyfikator odcienia skórki — punkt kodu nie jest wyświetlany jako element autonomiczny na ekranie.</span><span class="sxs-lookup"><span data-stu-id="05e10-233">In some of the preceding examples - such as the combining accent modifier or the skin tone modifier - the code point does not display as a standalone element on the screen.</span></span> <span data-ttu-id="05e10-234">Zamiast tego służy do modyfikowania wyglądu elementu tekstowego, który został wcześniej dołączony.</span><span class="sxs-lookup"><span data-stu-id="05e10-234">Rather, it serves to modify the appearance of a text element that came before it.</span></span> <span data-ttu-id="05e10-235">Te przykłady pokazują, że może przyjmować wiele wartości skalarnych, aby określić, co myślisz jako pojedynczy char klaster "acter" lub "Grapheme".</span><span class="sxs-lookup"><span data-stu-id="05e10-235">These examples show that it might take multiple scalar values to make up what we think of as a single "character," or "grapheme cluster."</span></span>

<span data-ttu-id="05e10-236">Aby wyliczyć klastry Grapheme z `string` , należy użyć <xref:System.Globalization.StringInfo> klasy, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="05e10-236">To enumerate the grapheme clusters of a `string`, use the <xref:System.Globalization.StringInfo> class as shown in the following example.</span></span> <span data-ttu-id="05e10-237">Jeśli znasz język SWIFT, `StringInfo` Typ .NET jest koncepcyjnie podobny do [ `character` typu SWIFT](https://developer.apple.com/documentation/swift/character).</span><span class="sxs-lookup"><span data-stu-id="05e10-237">If you're familiar with Swift, the .NET `StringInfo` type is conceptually similar to [Swift's `character` type](https://developer.apple.com/documentation/swift/character).</span></span>

### <a name="example-count-no-locchar-no-locrune-and-text-element-instances"></a><span data-ttu-id="05e10-238">Przykład: liczba char , Rune i wystąpienia elementu tekstowego</span><span class="sxs-lookup"><span data-stu-id="05e10-238">Example: count char, Rune, and text element instances</span></span>

<span data-ttu-id="05e10-239">W interfejsach API platformy .NET klaster Grapheme jest nazywany *elementem tekstowym*.</span><span class="sxs-lookup"><span data-stu-id="05e10-239">In .NET APIs, a grapheme cluster is called a *text element*.</span></span> <span data-ttu-id="05e10-240">Poniższa metoda pokazuje różnice między elementami `char` , `Rune` i wystąpieniami elementów tekstu w `string` :</span><span class="sxs-lookup"><span data-stu-id="05e10-240">The following method demonstrates the differences between `char`, `Rune`, and text element instances in a `string`:</span></span>

<span data-ttu-id="05e10-241">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/CountTextElements. cs" ID = "SnippetCountMethod"::</span><span class="sxs-lookup"><span data-stu-id="05e10-241">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::</span></span>

<span data-ttu-id="05e10-242">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/CountTextElements. cs" ID = "SnippetCallCountMethod"::</span><span class="sxs-lookup"><span data-stu-id="05e10-242">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::</span></span>

<span data-ttu-id="05e10-243">W przypadku uruchomienia tego kodu w .NET Framework lub .NET Core 3,1 lub starszym liczba elementów tekstowych dla znaku emoji zostanie wyświetlona `4` .</span><span class="sxs-lookup"><span data-stu-id="05e10-243">If you run this code in .NET Framework or .NET Core 3.1 or earlier, the text element count for the emoji shows `4`.</span></span> <span data-ttu-id="05e10-244">Jest to spowodowane usterką w `StringInfo` klasie, która została naprawiona w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="05e10-244">That is due to a bug in the `StringInfo` class that is fixed in .NET 5.</span></span>

### <a name="example-splitting-no-locstring-instances"></a><span data-ttu-id="05e10-245">Przykład: dzielenie string wystąpień</span><span class="sxs-lookup"><span data-stu-id="05e10-245">Example: splitting string instances</span></span>

<span data-ttu-id="05e10-246">Podczas dzielenia `string` wystąpień należy unikać dzielenia pary zastępczych i klastrów Grapheme.</span><span class="sxs-lookup"><span data-stu-id="05e10-246">When splitting `string` instances, avoid splitting surrogate pairs and grapheme clusters.</span></span> <span data-ttu-id="05e10-247">Rozważmy następujący przykład nieprawidłowego kodu, który zamierza wstawiać podziały wierszy co 10 char acters w string :</span><span class="sxs-lookup"><span data-stu-id="05e10-247">Consider the following example of incorrect code, which intends to insert line breaks every 10 characters in a string:</span></span>

<span data-ttu-id="05e10-248">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/InsertNewlines. cs" ID = "SnippetBadExample"::</span><span class="sxs-lookup"><span data-stu-id="05e10-248">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="05e10-249">Ponieważ ten kod wylicza `char` wystąpienia, para dwuskładnikowa, która ma miejsce na obramowanie międzystrefowe, `char` zostanie podzielona i zostanie dodany nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="05e10-249">Because this code enumerates `char` instances, a surrogate pair that happens to straddle a 10-`char` boundary will be split and a newline injected between them.</span></span> <span data-ttu-id="05e10-250">W tym wstawieniu wprowadzono uszkodzenia danych, ponieważ punkty kodu surogatu są istotne tylko jako pary.</span><span class="sxs-lookup"><span data-stu-id="05e10-250">This insertion introduces data corruption, because surrogate code points are meaningful only as pairs.</span></span>

<span data-ttu-id="05e10-251">Potencjalne uszkodzenie danych nie jest eliminowane w przypadku wyliczania `Rune` wystąpień (wartości skalarnych) zamiast `char` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="05e10-251">The potential for data corruption isn't eliminated if you enumerate `Rune` instances (scalar values) instead of `char` instances.</span></span> <span data-ttu-id="05e10-252">Zestaw `Rune` wystąpień może utworzyć klaster Grapheme, który ma międzystrefę 10 `char` granic.</span><span class="sxs-lookup"><span data-stu-id="05e10-252">A set of `Rune` instances might make up a grapheme cluster that straddles a 10-`char` boundary.</span></span> <span data-ttu-id="05e10-253">Jeśli zestaw klastrów Grapheme jest podzielony, nie można go poprawnie zinterpretować.</span><span class="sxs-lookup"><span data-stu-id="05e10-253">If the grapheme cluster set is split up, it can't be interpreted correctly.</span></span>

<span data-ttu-id="05e10-254">Lepszym rozwiązaniem jest przerwanie string przez zliczanie klastrów Grapheme lub elementów tekstowych, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="05e10-254">A better approach is to break the string by counting grapheme clusters, or text elements, as in the following example:</span></span>

<span data-ttu-id="05e10-255">::: Code Language = "CSharp" source = "urywki/ char acter-Encoding-Introduction/CSharp/InsertNewlines. cs" ID = "SnippetGoodExample"::</span><span class="sxs-lookup"><span data-stu-id="05e10-255">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::</span></span>

<span data-ttu-id="05e10-256">Jak wspomniano wcześniej, jednak w implementacjach platformy .NET innej niż .NET 5 `StringInfo` Klasa może nieprawidłowo obsłużyć niektóre klastry Grapheme.</span><span class="sxs-lookup"><span data-stu-id="05e10-256">As noted earlier, however, in implementations of .NET other than .NET 5, the `StringInfo` class might handle some grapheme clusters incorrectly.</span></span>

## <a name="utf-8-and-utf-32"></a><span data-ttu-id="05e10-257">UTF-8 i UTF-32</span><span class="sxs-lookup"><span data-stu-id="05e10-257">UTF-8 and UTF-32</span></span>

<span data-ttu-id="05e10-258">Poprzednie sekcje skupiające się na kodowaniu UTF-16, ponieważ są używane przez platformę .NET do kodowania `string` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="05e10-258">The preceding sections focused on UTF-16 because that's what .NET uses to encode `string` instances.</span></span> <span data-ttu-id="05e10-259">Istnieją inne systemy kodowania dla standardu Unicode- [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) i [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span><span class="sxs-lookup"><span data-stu-id="05e10-259">There are other encoding systems for Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) and [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span></span> <span data-ttu-id="05e10-260">Te kodowania wykorzystują odpowiednio 8-bitowe jednostki kodu i 32-bitowe jednostki kodu.</span><span class="sxs-lookup"><span data-stu-id="05e10-260">These encodings use 8-bit code units and 32-bit code units, respectively.</span></span>

<span data-ttu-id="05e10-261">Podobnie jak w przypadku UTF-16, UTF-8 wymaga wielu jednostek kodu do reprezentowania niektórych wartości skalarnych Unicode.</span><span class="sxs-lookup"><span data-stu-id="05e10-261">Like UTF-16, UTF-8 requires multiple code units to represent some Unicode scalar values.</span></span> <span data-ttu-id="05e10-262">Kodowanie UTF-32 może reprezentować dowolną wartość skalarną w jednej jednostce kodu 32-bitowej.</span><span class="sxs-lookup"><span data-stu-id="05e10-262">UTF-32 can represent any scalar value in a single 32-bit code unit.</span></span>

<span data-ttu-id="05e10-263">Poniżej przedstawiono kilka przykładów przedstawiających sposób reprezentowania tego samego punktu kodu Unicode w każdym z tych trzech systemów kodowania Unicode:</span><span class="sxs-lookup"><span data-stu-id="05e10-263">Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span></span>

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

<span data-ttu-id="05e10-264">Jak wspomniano wcześniej, pojedyncza jednostka kodu UTF-16 z [pary zastępczej](#surrogate-pairs) jest bezproblemowa.</span><span class="sxs-lookup"><span data-stu-id="05e10-264">As noted earlier, a single UTF-16 code unit from a [surrogate pair](#surrogate-pairs) is meaningless by itself.</span></span> <span data-ttu-id="05e10-265">W ten sam sposób pojedyncza jednostka kodu UTF-8 jest bezużyteczne, jeśli jest w sekwencji dwóch, trzech lub czterech używanych do obliczania wartości skalarnej.</span><span class="sxs-lookup"><span data-stu-id="05e10-265">In the same way, a single UTF-8 code unit is meaningless by itself if it's in a sequence of two, three, or four used to calculate a scalar value.</span></span>

### <a name="endianness"></a><span data-ttu-id="05e10-266">Endian</span><span class="sxs-lookup"><span data-stu-id="05e10-266">Endianness</span></span>

<span data-ttu-id="05e10-267">W programie .NET jednostki kodu UTF-16 string są przechowywane w ciągłej pamięci jako sekwencja 16-bitowych liczb całkowitych ( `char` wystąpień).</span><span class="sxs-lookup"><span data-stu-id="05e10-267">In .NET, the UTF-16 code units of a string are stored in contiguous memory as a sequence of 16-bit integers (`char` instances).</span></span> <span data-ttu-id="05e10-268">Bity poszczególnych jednostek kodu są ustalane w zależności od liczby [bajtów](https://en.wikipedia.org/wiki/Endianness) bieżącej architektury.</span><span class="sxs-lookup"><span data-stu-id="05e10-268">The bits of individual code units are laid out according to the [endianness](https://en.wikipedia.org/wiki/Endianness) of the current architecture.</span></span>

<span data-ttu-id="05e10-269">W przypadku architektury little-endian string złożone z punktów kodu UTF-16 `[ D801 DCCC ]` zostałyby ustalone w pamięci jako bajty `[ 0x01, 0xD8, 0xCC, 0xDC ]` .</span><span class="sxs-lookup"><span data-stu-id="05e10-269">On a little-endian architecture, the string consisting of the UTF-16 code points `[ D801 DCCC ]` would be laid out in memory as the bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span></span> <span data-ttu-id="05e10-270">W przypadku architektury big-endian string można ją określić w pamięci jako bajty `[ 0xD8, 0x01, 0xDC, 0xCC ]` .</span><span class="sxs-lookup"><span data-stu-id="05e10-270">On a big-endian architecture that same string would be laid out in memory as the bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span></span>

<span data-ttu-id="05e10-271">Systemy komputerowe, które komunikują się ze sobą, muszą wyrazić zgodę na reprezentację danych przekraczających sieć.</span><span class="sxs-lookup"><span data-stu-id="05e10-271">Computer systems that communicate with each other must agree on the representation of data crossing the wire.</span></span> <span data-ttu-id="05e10-272">Większość protokołów sieciowych używa kodowania UTF-8 jako standard podczas przesyłania tekstu, częściowo, aby uniknąć problemów, które mogą wynikać z komputera z dużą liczbą bajtów, komunikując się z komputerem o małej przepustowości.</span><span class="sxs-lookup"><span data-stu-id="05e10-272">Most network protocols use UTF-8 as a standard when transmitting text, partly to avoid issues that might result from a big-endian machine communicating with a little-endian machine.</span></span> <span data-ttu-id="05e10-273">stringSkładowe składające się z punktów kodu UTF-8 `[ F0 90 93 8C ]` będą zawsze reprezentowane jako bajty, `[ 0xF0, 0x90, 0x93, 0x8C ]` niezależnie od liczby bajtów.</span><span class="sxs-lookup"><span data-stu-id="05e10-273">The string consisting of the UTF-8 code points `[ F0 90 93 8C ]` will always be represented as the bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` regardless of endianness.</span></span>

<span data-ttu-id="05e10-274">Aby użyć UTF-8 do przesyłania tekstu, aplikacje .NET często używają kodu, takiego jak Poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="05e10-274">To use UTF-8 for transmitting text, .NET applications often use code like the following example:</span></span>

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

<span data-ttu-id="05e10-275">W poprzednim przykładzie metoda [Encoding. UTF8. GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) dekoduje kod UTF-16 `string` do serii wartości skalarnych Unicode, a następnie ponownie koduje te wartości skalarne na UTF-8 i umieszcza wyniki sekwencji w `byte` tablicy.</span><span class="sxs-lookup"><span data-stu-id="05e10-275">In the preceding example, the method [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodes the UTF-16 `string` back into a series of Unicode scalar values, then it re-encodes those scalar values into UTF-8 and places the resulting sequence into a `byte` array.</span></span> <span data-ttu-id="05e10-276">Metoda [Encoding. UTF8. GetString](xref:System.Text.UTF8Encoding.GetString%2A) wykonuje odwrotną transformację, konwertując tablicę UTF-8 `byte` na UTF-16 `string` .</span><span class="sxs-lookup"><span data-stu-id="05e10-276">The method [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) performs the opposite transformation, converting a UTF-8 `byte` array to a UTF-16 `string`.</span></span>

> [!WARNING]
> <span data-ttu-id="05e10-277">Ponieważ UTF-8 jest commonplace w Internecie, może być skłonny do odczytu nieprzetworzonych bajtów z sieci i do traktowania danych, tak jakby była to UTF-8.</span><span class="sxs-lookup"><span data-stu-id="05e10-277">Since UTF-8 is commonplace on the internet, it may be tempting to read raw bytes from the wire and to treat the data as if it were UTF-8.</span></span> <span data-ttu-id="05e10-278">Należy jednak sprawdzić, czy jest on rzeczywiście poprawnie sformułowany.</span><span class="sxs-lookup"><span data-stu-id="05e10-278">However, you should validate that it is indeed well-formed.</span></span> <span data-ttu-id="05e10-279">Złośliwy klient może przesłać do usługi źle sformułowany format UTF-8.</span><span class="sxs-lookup"><span data-stu-id="05e10-279">A malicious client might submit ill-formed UTF-8 to your service.</span></span> <span data-ttu-id="05e10-280">Jeśli te dane są używane w taki sposób, jakby były poprawnie sformułowane, może to spowodować błędy lub luki w zabezpieczeniach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="05e10-280">If you operate on that data as if it were well-formed, it could cause errors or security holes in your application.</span></span> <span data-ttu-id="05e10-281">Aby sprawdzić poprawność danych UTF-8, można użyć metody takiej jak `Encoding.UTF8.GetString` , która przeprowadza walidację podczas konwertowania danych przychodzących na `string` .</span><span class="sxs-lookup"><span data-stu-id="05e10-281">To validate UTF-8 data, you can use a method like `Encoding.UTF8.GetString`, which will perform validation while converting the incoming data to a `string`.</span></span>

### <a name="well-formed-encoding"></a><span data-ttu-id="05e10-282">Poprawnie sformułowane kodowanie</span><span class="sxs-lookup"><span data-stu-id="05e10-282">Well-formed encoding</span></span>

<span data-ttu-id="05e10-283">Poprawnie sformułowane kodowanie Unicode to string jednostki kodu, które można zdekodować w sposób niejednoznaczny i bez błędu do sekwencji wartości skalarnych Unicode.</span><span class="sxs-lookup"><span data-stu-id="05e10-283">A well-formed Unicode encoding is a string of code units that can be decoded unambiguously and without error into a sequence of Unicode scalar values.</span></span> <span data-ttu-id="05e10-284">Poprawnie sformułowane dane można transkodować bez ograniczeń i z powrotem między UTF-8, UTF-16 i UTF-32.</span><span class="sxs-lookup"><span data-stu-id="05e10-284">Well-formed data can be transcoded freely back and forth between UTF-8, UTF-16, and UTF-32.</span></span>

<span data-ttu-id="05e10-285">Pytanie, czy sekwencja kodowania jest poprawnie sformułowana, czy nie jest niezwiązana z przydziałami architektury maszyny.</span><span class="sxs-lookup"><span data-stu-id="05e10-285">The question of whether an encoding sequence is well-formed or not is unrelated to the endianness of a machine's architecture.</span></span> <span data-ttu-id="05e10-286">Nieprawidłowo sformułowana sekwencja UTF-8 jest źle sformułowana w taki sam sposób na maszynach big-endian i little-endian.</span><span class="sxs-lookup"><span data-stu-id="05e10-286">An ill-formed UTF-8 sequence is ill-formed in the same way on both big-endian and little-endian machines.</span></span>

<span data-ttu-id="05e10-287">Poniżej przedstawiono kilka przykładów niewłaściwie sformułowanych kodowań:</span><span class="sxs-lookup"><span data-stu-id="05e10-287">Here are some examples of ill-formed encodings:</span></span>

* <span data-ttu-id="05e10-288">W UTF-8 sekwencja `[ 6C C2 61 ]` jest źle sformułowana, ponieważ `C2` nie może następować po niej `61` .</span><span class="sxs-lookup"><span data-stu-id="05e10-288">In UTF-8, the sequence `[ 6C C2 61 ]` is ill-formed because `C2` cannot be followed by `61`.</span></span>

* <span data-ttu-id="05e10-289">W UTF-16, sekwencja `[ DC00 DD00 ]` (lub, w języku C#, string `"\udc00\udd00"` ) jest źle sformułowana, ponieważ dolny Surogat `DC00` nie może następować po drugim dolnym surogatie `DD00` .</span><span class="sxs-lookup"><span data-stu-id="05e10-289">In UTF-16, the sequence `[ DC00 DD00 ]` (or, in C#, the string `"\udc00\udd00"`) is ill-formed because the low surrogate `DC00` cannot be followed by another low surrogate `DD00`.</span></span>

* <span data-ttu-id="05e10-290">W UTF-32 sekwencja `[ 0011ABCD ]` jest źle sformułowana, ponieważ `0011ABCD` znajduje się poza zakresem wartości skalarnych Unicode.</span><span class="sxs-lookup"><span data-stu-id="05e10-290">In UTF-32, the sequence `[ 0011ABCD ]` is ill-formed because `0011ABCD` is outside the range of Unicode scalar values.</span></span>

<span data-ttu-id="05e10-291">W programie .NET `string` wystąpienia prawie zawsze zawierają poprawnie sformułowane dane UTF-16, ale nie są one gwarantowane.</span><span class="sxs-lookup"><span data-stu-id="05e10-291">In .NET, `string` instances almost always contain well-formed UTF-16 data, but that isn't guaranteed.</span></span> <span data-ttu-id="05e10-292">W poniższych przykładach pokazano prawidłowy kod w języku C#, który tworzy nieprawidłowo sformułowane dane UTF-16 w `string` wystąpieniach.</span><span class="sxs-lookup"><span data-stu-id="05e10-292">The following examples show valid C# code that creates ill-formed UTF-16 data in `string` instances.</span></span>

* <span data-ttu-id="05e10-293">Nieprawidłowo sformułowany literał:</span><span class="sxs-lookup"><span data-stu-id="05e10-293">An ill-formed literal:</span></span>

  ```csharp
  const string s = "\ud800";
  ```

* <span data-ttu-id="05e10-294">Sub string dzieląca parę zastępczą:</span><span class="sxs-lookup"><span data-stu-id="05e10-294">A substring that splits up a surrogate pair:</span></span>

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

<span data-ttu-id="05e10-295">Interfejsy API, takie jak [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) nigdy nie zwracają źle sformułowane `string` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="05e10-295">APIs like [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) never return ill-formed `string` instances.</span></span> <span data-ttu-id="05e10-296">`Encoding.GetString``Encoding.GetBytes`metody i wykrywają źle sformułowane sekwencje w danych wejściowych i wykonują char podstawienie acter podczas generowania danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="05e10-296">`Encoding.GetString` and `Encoding.GetBytes` methods detect ill-formed sequences in the input and perform character substitution when generating the output.</span></span> <span data-ttu-id="05e10-297">Jeśli na przykład [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) w danych wejściowych zostanie wyświetlony bajt inny niż ASCII (poza zakresem u + 0000.. u + 007F), wstawiany jest znak "?" w zwracanym `string` wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="05e10-297">For example, if [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) sees a non-ASCII byte in the input (outside the range U+0000..U+007F), it inserts a '?' into the returned `string` instance.</span></span> <span data-ttu-id="05e10-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) zamienia źle sformułowane sekwencje UTF-8 z `U+FFFD REPLACEMENT CHARACTER ('�')` w zwracanym `string` wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="05e10-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) replaces ill-formed UTF-8 sequences with `U+FFFD REPLACEMENT CHARACTER ('�')` in the returned `string` instance.</span></span> <span data-ttu-id="05e10-299">Aby uzyskać więcej informacji, zobacz [standard Unicode](https://www.unicode.org/versions/latest/), sekcje 5,22 i 3,9.</span><span class="sxs-lookup"><span data-stu-id="05e10-299">For more information, see [the Unicode Standard](https://www.unicode.org/versions/latest/), Sections 5.22 and 3.9.</span></span>

<span data-ttu-id="05e10-300">Wbudowane `Encoding` klasy można również skonfigurować tak, aby zgłaszać wyjątek, a nie char przestawiać acter, gdy widoczne są źle sformułowane sekwencje.</span><span class="sxs-lookup"><span data-stu-id="05e10-300">The built-in `Encoding` classes can also be configured to throw an exception rather than perform character substitution when ill-formed sequences are seen.</span></span> <span data-ttu-id="05e10-301">Takie podejście jest często stosowane w aplikacjach z uwzględnieniem zabezpieczeń, w których char podstawianie acter może być niedopuszczalne.</span><span class="sxs-lookup"><span data-stu-id="05e10-301">This approach is often used in security-sensitive applications where character substitution might not be acceptable.</span></span>

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

<span data-ttu-id="05e10-302">Aby uzyskać informacje o sposobach korzystania z wbudowanych `Encoding` klas, zobacz [How to use char acter Encoding Classes in .NET](character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="05e10-302">For information about how to use the built-in `Encoding` classes, see [How to use character encoding classes in .NET](character-encoding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05e10-303">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="05e10-303">See also</span></span>

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [<span data-ttu-id="05e10-304">Globalizacja i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="05e10-304">Globalization and Localization</span></span>](../globalization-localization/index.md)
