---
title: Like — Operator
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: 49dfe5cf5dbcf8dc6f79f569a92e36aa81806913
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866775"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="9d7b1-102">Like — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d7b1-102">Like Operator (Visual Basic)</span></span>

<span data-ttu-id="9d7b1-103">Porównuje ciąg ze wzorcem.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="9d7b1-104">`Like`Operator nie jest obecnie obsługiwany w projektach .NET Core i .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d7b1-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9d7b1-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="9d7b1-106">Części</span><span class="sxs-lookup"><span data-stu-id="9d7b1-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="9d7b1-107">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-107">Required.</span></span> <span data-ttu-id="9d7b1-108">Dowolna `Boolean` zmienna.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-108">Any `Boolean` variable.</span></span> <span data-ttu-id="9d7b1-109">Wynik jest `Boolean` wartością wskazującą, czy jest to element `string` spełniający kryteria `pattern` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="9d7b1-110">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-110">Required.</span></span> <span data-ttu-id="9d7b1-111">Dowolne `String` wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="9d7b1-112">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-112">Required.</span></span> <span data-ttu-id="9d7b1-113">Każde `String` wyrażenie zgodne z konwencjami dopasowania wzorca opisanymi w "uwagi".</span><span class="sxs-lookup"><span data-stu-id="9d7b1-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d7b1-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9d7b1-114">Remarks</span></span>  

 <span data-ttu-id="9d7b1-115">Jeśli wartość w jest równa `string` wzorzec zawarte w `pattern` , `result` to `True` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="9d7b1-116">Jeśli ciąg nie spełnia wzorca, `result` jest `False` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="9d7b1-117">Jeśli oba `string` i `pattern` są pustymi ciągami, wynik jest `True` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="9d7b1-118">Metoda porównania</span><span class="sxs-lookup"><span data-stu-id="9d7b1-118">Comparison Method</span></span>  

 <span data-ttu-id="9d7b1-119">Zachowanie `Like` operatora zależy od [opcji Compare instrukcji](../statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9d7b1-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../statements/option-compare-statement.md).</span></span> <span data-ttu-id="9d7b1-120">Domyślną metodą porównywania ciągów dla każdego pliku źródłowego jest `Option Compare Binary` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="9d7b1-121">Opcje wzorca</span><span class="sxs-lookup"><span data-stu-id="9d7b1-121">Pattern Options</span></span>  

 <span data-ttu-id="9d7b1-122">Wbudowane dopasowania wzorców zapewniają uniwersalne narzędzie do porównywania ciągów.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="9d7b1-123">Funkcje dopasowania wzorców umożliwiają dopasowanie każdego znaku w `string` odniesieniu do określonego znaku, symbolu wieloznacznego, listy znaków lub zakresu znaków.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="9d7b1-124">W poniższej tabeli przedstawiono znaki dozwolone w `pattern` i ich zgodność.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="9d7b1-125">Znaki w `pattern`</span><span class="sxs-lookup"><span data-stu-id="9d7b1-125">Characters in `pattern`</span></span>|<span data-ttu-id="9d7b1-126">Pasuje do `string`</span><span class="sxs-lookup"><span data-stu-id="9d7b1-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="9d7b1-127">Dowolny pojedynczy znak</span><span class="sxs-lookup"><span data-stu-id="9d7b1-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="9d7b1-128">Zero lub więcej znaków</span><span class="sxs-lookup"><span data-stu-id="9d7b1-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="9d7b1-129">Dowolna pojedyncza cyfra (0 – 9)</span><span class="sxs-lookup"><span data-stu-id="9d7b1-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="9d7b1-130">Dowolny pojedynczy znak w `charlist`</span><span class="sxs-lookup"><span data-stu-id="9d7b1-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="9d7b1-131">Dowolny pojedynczy znak, który nie znajduje się w `charlist`</span><span class="sxs-lookup"><span data-stu-id="9d7b1-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="9d7b1-132">Listy znaków</span><span class="sxs-lookup"><span data-stu-id="9d7b1-132">Character Lists</span></span>  

 <span data-ttu-id="9d7b1-133">Grupa zawierająca jeden lub więcej znaków ( `charlist` ) ujęta w nawiasy kwadratowe ( `[ ]` ) może być używana do dopasowania dowolnego pojedynczego znaku w `string` i może zawierać prawie dowolny kod znaku, w tym cyfry.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="9d7b1-134">Wykrzyknik ( `!` ) na początku `charlist` oznacza, że jest to dopasowanie, jeśli którykolwiek znak z wyjątkiem znaków w `charlist` jest znaleziony w `string` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="9d7b1-135">Gdy używany jest nawiasy klamrowe, wykrzyknik dopasowuje się do samego siebie.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="9d7b1-136">Znaki specjalne</span><span class="sxs-lookup"><span data-stu-id="9d7b1-136">Special Characters</span></span>  

 <span data-ttu-id="9d7b1-137">Aby dopasować znaki specjalne do lewego nawiasu ( `[` ), znaku zapytania ( `?` ), znaku numeru ( `#` ) i gwiazdki ( `*` ), umieść je w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="9d7b1-138">Nie można użyć prawego nawiasu ( `]` ) w grupie, aby dopasować się do siebie, ale może być używany poza grupą jako pojedynczy znak.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="9d7b1-139">Sekwencja znaków `[]` jest traktowana jako ciąg o zerowej długości ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="9d7b1-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="9d7b1-140">Jednak nie może być częścią listy znaków ujętej w nawiasy klamrowe.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="9d7b1-141">Jeśli chcesz sprawdzić, czy pozycja w polu `string` zawiera jedną z grup znaków lub nie ma żadnego znaku, możesz użyć `Like` dwa razy.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="9d7b1-142">Aby zapoznać się z przykładem, zobacz [jak: dopasowywanie ciągu do wzorca](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="9d7b1-142">For an example, see [How to: Match a String against a Pattern](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="9d7b1-143">Zakresy znaków</span><span class="sxs-lookup"><span data-stu-id="9d7b1-143">Character Ranges</span></span>  

 <span data-ttu-id="9d7b1-144">Używając łącznika ( `–` ), aby oddzielić dolną i górną granicę zakresu, `charlist` można określić zakres znaków.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="9d7b1-145">Na przykład `[A–Z]` wynikiem jest dopasowanie, jeśli odpowiadająca pozycja znaku w `string` zawiera dowolny znak z zakresu `A` – `Z` , a `[!H–L]` wynikiem jest dopasowanie, Jeśli odpowiednia pozycja znaku zawiera dowolny znak poza zakresem `H` — `L` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="9d7b1-146">Po określeniu zakresu znaków muszą one znajdować się w rosnącej kolejności sortowania, czyli od najniższego do najwyższego.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="9d7b1-147">W tym celu, `[A–Z]` jest prawidłowym wzorcem, ale `[Z–A]` nie jest.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="9d7b1-148">Wiele zakresów znaków</span><span class="sxs-lookup"><span data-stu-id="9d7b1-148">Multiple Character Ranges</span></span>  

 <span data-ttu-id="9d7b1-149">Aby określić wiele zakresów dla tej samej pozycji znaku, umieść je w tych samych nawiasach bez ograniczników.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="9d7b1-150">Na przykład `[A–CX–Z]` wynikiem jest dopasowanie, Jeśli odpowiednia pozycja znaku w `string` zawiera dowolny znak z zakresu `A` `C` lub zakresu `X` — `Z` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="9d7b1-151">Użycie łącznika</span><span class="sxs-lookup"><span data-stu-id="9d7b1-151">Usage of the Hyphen</span></span>  

 <span data-ttu-id="9d7b1-152">Łącznik ( `–` ) może pojawić się na początku (po wykrzykniku, jeśli istnieje) lub na końcu, `charlist` Aby dopasować sam siebie.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="9d7b1-153">W każdej innej lokalizacji łącznik identyfikuje zakres znaków, które są rozdzielane znakami po obu stronach łącznika.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="9d7b1-154">Kolejność sortowania</span><span class="sxs-lookup"><span data-stu-id="9d7b1-154">Collating Sequence</span></span>  

 <span data-ttu-id="9d7b1-155">Znaczenie określonego zakresu zależy od kolejności znaków w czasie wykonywania, zgodnie z ustawieniami `Option Compare` regionalnymi systemu, w którym jest uruchomiony kod.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="9d7b1-156">Z `Option Compare Binary` , zakres `[A–E]` dopasowuje `A` , `B` , `C` , `D` , i `E` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="9d7b1-157">With `Option Compare Text` , dopasowuje,,,,,,,, `[A–E]` `A` ,, `a` `À` `à` `B` `b` `C` `c` `D` `d` `E` i `e` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="9d7b1-158">Zakres nie pasuje `Ê` lub `ê` ponieważ znaki akcentowane są sortowane po nieakcentowane znaki w kolejności sortowania.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="9d7b1-159">Znaki odgrafu</span><span class="sxs-lookup"><span data-stu-id="9d7b1-159">Digraph Characters</span></span>  

 <span data-ttu-id="9d7b1-160">W niektórych językach istnieją znaki alfabetyczne, które reprezentują dwa oddzielne znaki.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="9d7b1-161">Na przykład kilka języków używa znaku, `æ` aby reprezentować znaki `a` i `e` kiedy pojawiają się razem.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="9d7b1-162">`Like`Operator rozpoznaje, że pojedynczy znak dwugrafu i dwa poszczególne znaki są równoważne.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="9d7b1-163">Gdy język, który używa znaku oddzielenia, jest określony w ustawieniach regionalnych systemu, wystąpienie pojedynczego znaku w `pattern` lub `string` pasuje do równoważnej dwuznakowej sekwencji w innym ciągu.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="9d7b1-164">Analogicznie, znak podgrafu `pattern` umieszczony w nawiasach (na liście lub w zakresie) jest zgodny z równoważną dwuznakową sekwencją w `string` .</span><span class="sxs-lookup"><span data-stu-id="9d7b1-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9d7b1-165">Przeciążenie</span><span class="sxs-lookup"><span data-stu-id="9d7b1-165">Overloading</span></span>  

 <span data-ttu-id="9d7b1-166">`Like`Operator może być *przeciążony*, co oznacza, że Klasa lub struktura może przedefiniować jej zachowanie, gdy operand ma typ tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9d7b1-167">Jeśli Twój kod używa tego operatora dla takiej klasy lub struktury, pamiętaj o tym, aby zrozumieć jego ponownie zdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9d7b1-168">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9d7b1-168">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d7b1-169">Przykład</span><span class="sxs-lookup"><span data-stu-id="9d7b1-169">Example</span></span>  

 <span data-ttu-id="9d7b1-170">W tym przykładzie używa `Like` operatora do porównywania ciągów z różnymi wzorcami.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="9d7b1-171">Wyniki są wprowadzane do `Boolean` zmiennej wskazującej, czy każdy ciąg spełnia wzorzec.</span><span class="sxs-lookup"><span data-stu-id="9d7b1-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="9d7b1-172">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9d7b1-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="9d7b1-173">Operatory porównania</span><span class="sxs-lookup"><span data-stu-id="9d7b1-173">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="9d7b1-174">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d7b1-174">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="9d7b1-175">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="9d7b1-175">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="9d7b1-176">Option Compare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="9d7b1-176">Option Compare Statement</span></span>](../statements/option-compare-statement.md)
- [<span data-ttu-id="9d7b1-177">Operatory i wyrażenia</span><span class="sxs-lookup"><span data-stu-id="9d7b1-177">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="9d7b1-178">Instrukcje: dopasowywanie ciągu do wzorca</span><span class="sxs-lookup"><span data-stu-id="9d7b1-178">How to: Match a String against a Pattern</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
