---
title: Listy
description: 'Zapoznaj się z listami języka F #, uporządkowaną, niemodyfikowalną serią elementów tego samego typu.'
ms.date: 08/13/2020
ms.openlocfilehash: 567731eb57b77d60d3dd847630d5676e8d047d09
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720351"
---
# <a name="lists"></a><span data-ttu-id="d7d69-103">Listy</span><span class="sxs-lookup"><span data-stu-id="d7d69-103">Lists</span></span>

<span data-ttu-id="d7d69-104">Lista w F # to uporządkowana, niezmienna seria elementów tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-104">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="d7d69-105">Aby wykonać podstawowe operacje na listach, użyj funkcji w [module list](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="d7d69-105">To perform basic operations on lists, use the functions in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="d7d69-106">Tworzenie i Inicjowanie list</span><span class="sxs-lookup"><span data-stu-id="d7d69-106">Creating and Initializing Lists</span></span>

<span data-ttu-id="d7d69-107">Możesz zdefiniować listę, jawnie wymieniając elementy, oddzielając je średnikami i ujęte w nawiasy kwadratowe, jak pokazano w poniższym wierszu kodu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-107">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="d7d69-108">Można również umieścić podziały wierszy między elementami, w tym przypadku średniki są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="d7d69-108">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="d7d69-109">Druga składnia może spowodować bardziej czytelny kod, gdy wyrażenia inicjowania elementu są dłuższe lub jeśli chcesz dołączyć komentarz dla każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-109">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="d7d69-110">Zwykle wszystkie elementy listy muszą być tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-110">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="d7d69-111">Wyjątek polega na tym, że lista, w której elementy są określone jako typ podstawowy może mieć elementy, które są typami pochodnymi.</span><span class="sxs-lookup"><span data-stu-id="d7d69-111">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="d7d69-112">W związku z tym następujące elementy są dopuszczalne, ponieważ obie `Button` i `CheckBox` pochodzą od `Control` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-112">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="d7d69-113">Można również zdefiniować elementy listy przy użyciu zakresu wskazywanego przez liczby całkowite oddzielone operatorem zakresu ( `..` ), jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-113">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="d7d69-114">Pusta lista jest określana przez parę nawiasów kwadratowych, w których nie ma niczego między nimi.</span><span class="sxs-lookup"><span data-stu-id="d7d69-114">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="d7d69-115">Możesz również użyć wyrażenia sekwencji, aby utworzyć listę.</span><span class="sxs-lookup"><span data-stu-id="d7d69-115">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="d7d69-116">Aby uzyskać więcej informacji, zobacz [wyrażenia sekwencji](sequences.md#sequence-expressions) .</span><span class="sxs-lookup"><span data-stu-id="d7d69-116">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="d7d69-117">Na przykład poniższy kod tworzy listę kwadratów liczb całkowitych z zakresu od 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="d7d69-117">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="d7d69-118">Operatory pracy z listami</span><span class="sxs-lookup"><span data-stu-id="d7d69-118">Operators for Working with Lists</span></span>

<span data-ttu-id="d7d69-119">Możesz dołączyć elementy do listy za pomocą `::` operatora (wady).</span><span class="sxs-lookup"><span data-stu-id="d7d69-119">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="d7d69-120">Jeśli `list1` jest `[2; 3; 4]` , poniższy kod tworzy `list2` jako `[100; 2; 3; 4]` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-120">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="d7d69-121">Można łączyć listy z zgodnymi typami przy użyciu `@` operatora, jak w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-121">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="d7d69-122">Jeśli `list1` jest `[2; 3; 4]` i `list2` ma `[100; 2; 3; 4]` , ten kod tworzy `list3` jako `[2; 3; 4; 100; 2; 3; 4]` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-122">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="d7d69-123">Funkcje do wykonywania operacji na listach są dostępne w [module list](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="d7d69-123">Functions for performing operations on lists are available in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

<span data-ttu-id="d7d69-124">Ponieważ listy w języku F # są niezmienne, wszelkie operacje modyfikacji generują nowe listy zamiast modyfikować istniejące.</span><span class="sxs-lookup"><span data-stu-id="d7d69-124">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="d7d69-125">Listy w języku F # są implementowane jako pojedynczo połączone listy, co oznacza, że operacje, które uzyskują dostęp tylko do nagłówka listy, mają wartość O (1), a dostęp do elementów to O (*n*).</span><span class="sxs-lookup"><span data-stu-id="d7d69-125">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="d7d69-126">Właściwości</span><span class="sxs-lookup"><span data-stu-id="d7d69-126">Properties</span></span>

<span data-ttu-id="d7d69-127">Typ listy obsługuje następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="d7d69-127">The list type supports the following properties:</span></span>

|<span data-ttu-id="d7d69-128">Właściwość</span><span class="sxs-lookup"><span data-stu-id="d7d69-128">Property</span></span>|<span data-ttu-id="d7d69-129">Typ</span><span class="sxs-lookup"><span data-stu-id="d7d69-129">Type</span></span>|<span data-ttu-id="d7d69-130">Opis</span><span class="sxs-lookup"><span data-stu-id="d7d69-130">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="d7d69-131">Head</span><span class="sxs-lookup"><span data-stu-id="d7d69-131">Head</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|<span data-ttu-id="d7d69-132">Pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="d7d69-132">The first element.</span></span>|
|[<span data-ttu-id="d7d69-133">Ciągiem</span><span class="sxs-lookup"><span data-stu-id="d7d69-133">Empty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|<span data-ttu-id="d7d69-134">Właściwość statyczna zwracająca pustą listę odpowiedniego typu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-134">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="d7d69-135">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="d7d69-135">IsEmpty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|<span data-ttu-id="d7d69-136">`true` Jeśli lista nie zawiera żadnych elementów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-136">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="d7d69-137">Element</span><span class="sxs-lookup"><span data-stu-id="d7d69-137">Item</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|<span data-ttu-id="d7d69-138">Element o określonym indeksie (liczony od zera).</span><span class="sxs-lookup"><span data-stu-id="d7d69-138">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="d7d69-139">Długość</span><span class="sxs-lookup"><span data-stu-id="d7d69-139">Length</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|<span data-ttu-id="d7d69-140">Liczba elementów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-140">The number of elements.</span></span>|
|[<span data-ttu-id="d7d69-141">Tail</span><span class="sxs-lookup"><span data-stu-id="d7d69-141">Tail</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|<span data-ttu-id="d7d69-142">Lista bez pierwszego elementu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-142">The list without the first element.</span></span>|

<span data-ttu-id="d7d69-143">Poniżej przedstawiono kilka przykładów użycia tych właściwości.</span><span class="sxs-lookup"><span data-stu-id="d7d69-143">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="d7d69-144">Korzystanie z list</span><span class="sxs-lookup"><span data-stu-id="d7d69-144">Using Lists</span></span>

<span data-ttu-id="d7d69-145">Programowanie za pomocą list umożliwia wykonywanie złożonych operacji przy użyciu niewielkiej ilości kodu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-145">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="d7d69-146">W tej sekcji opisano typowe operacje na listach, które są ważne dla programowania funkcjonalnego.</span><span class="sxs-lookup"><span data-stu-id="d7d69-146">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="d7d69-147">Rekursja z listami</span><span class="sxs-lookup"><span data-stu-id="d7d69-147">Recursion with Lists</span></span>

<span data-ttu-id="d7d69-148">Listy są jednoznacznie dostosowane do technik programowania cyklicznego.</span><span class="sxs-lookup"><span data-stu-id="d7d69-148">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="d7d69-149">Należy wziąć pod uwagę operację, która musi zostać wykonana dla każdego elementu listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-149">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="d7d69-150">Można to zrobić cyklicznie, działając na początku listy, a następnie przekazując ogon listy, czyli mniejszą listę, która składa się z oryginalnej listy bez pierwszego elementu, z powrotem do następnego poziomu rekursji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-150">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="d7d69-151">Aby napisać taką funkcję cykliczną, należy użyć operatora wad ( `::` ) we wzorcu dopasowywania, który umożliwia rozdzielenie nagłówka listy od ogona.</span><span class="sxs-lookup"><span data-stu-id="d7d69-151">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="d7d69-152">Poniższy przykład kodu pokazuje, jak używać dopasowywania wzorców do implementowania funkcji cyklicznej, która wykonuje operacje na liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-152">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="d7d69-153">Poprzedni kod działa dobrze w przypadku małych list, ale dla większych list może przekroczyć stos.</span><span class="sxs-lookup"><span data-stu-id="d7d69-153">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="d7d69-154">Poniższy kod Ulepsza ten kod przy użyciu argumentu akumulowana, standardowej techniki pracy z funkcjami cyklicznymi.</span><span class="sxs-lookup"><span data-stu-id="d7d69-154">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="d7d69-155">Użycie argumentu akumulowana powoduje cykliczne zakończenie funkcji, która zapisuje przestrzeń stosu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-155">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="d7d69-156">Funkcja `RemoveAllMultiples` jest funkcją cykliczną, która przyjmuje dwie listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-156">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="d7d69-157">Pierwsza lista zawiera numery, których wielokrotność zostanie usunięta, a druga lista to lista, z której mają zostać usunięte liczby.</span><span class="sxs-lookup"><span data-stu-id="d7d69-157">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="d7d69-158">W poniższym przykładzie kod używa tej funkcji cyklicznej, aby wyeliminować wszystkie niepodstawowe numery z listy, pozostawiając w wyniku listę numerów pierwszych.</span><span class="sxs-lookup"><span data-stu-id="d7d69-158">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="d7d69-159">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-159">The output is as follows:</span></span>

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="d7d69-160">Funkcje modułu</span><span class="sxs-lookup"><span data-stu-id="d7d69-160">Module Functions</span></span>

<span data-ttu-id="d7d69-161">[Moduł list](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) zawiera funkcje, które uzyskują dostęp do elementów listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-161">The [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) provides functions that access the elements of a list.</span></span> <span data-ttu-id="d7d69-162">Element główny jest najszybszy i najłatwiejszy do uzyskania dostępu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-162">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="d7d69-163">Użyj właściwości [głównego](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) lub listy funkcji modułu [.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head)</span><span class="sxs-lookup"><span data-stu-id="d7d69-163">Use the property [Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) or the module function [List.head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span></span> <span data-ttu-id="d7d69-164">Można uzyskać dostęp do ogona listy za pomocą właściwości [tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) lub funkcji [list. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) .</span><span class="sxs-lookup"><span data-stu-id="d7d69-164">You can access the tail of a list by using the [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) property or the [List.tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) function.</span></span> <span data-ttu-id="d7d69-165">Aby znaleźć element według indeksu, użyj funkcji [list. n](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) .</span><span class="sxs-lookup"><span data-stu-id="d7d69-165">To find an element by index, use the [List.nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) function.</span></span> <span data-ttu-id="d7d69-166">`List.nth` przechodzi listę.</span><span class="sxs-lookup"><span data-stu-id="d7d69-166">`List.nth` traverses the list.</span></span> <span data-ttu-id="d7d69-167">W związku z tym to O (*n*).</span><span class="sxs-lookup"><span data-stu-id="d7d69-167">Therefore, it is O(*n*).</span></span> <span data-ttu-id="d7d69-168">Jeśli kod `List.nth` jest często używany, warto rozważyć użycie tablicy zamiast listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-168">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="d7d69-169">Dostęp do elementów w tablicach ma (1).</span><span class="sxs-lookup"><span data-stu-id="d7d69-169">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="d7d69-170">Operacje logiczne na listach</span><span class="sxs-lookup"><span data-stu-id="d7d69-170">Boolean Operations on Lists</span></span>

<span data-ttu-id="d7d69-171">Funkcja [list. IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) określa, czy lista zawiera dowolne elementy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-171">The [List.isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) function determines whether a list has any elements.</span></span>

<span data-ttu-id="d7d69-172">Funkcja [list. Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) stosuje test logiczny do elementów listy i zwraca, `true` Jeśli którykolwiek element spełnia testy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-172">The [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="d7d69-173">[List. exists2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) jest podobny, ale działa na kolejnych parach elementów na dwóch listach.</span><span class="sxs-lookup"><span data-stu-id="d7d69-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="d7d69-174">Poniższy kod ilustruje użycie `List.exists` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-174">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="d7d69-175">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-175">The output is as follows:</span></span>

```console
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="d7d69-176">Poniższy przykład ilustruje użycie `List.exists2` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-176">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="d7d69-177">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-177">The output is as follows:</span></span>

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="d7d69-178">Możesz użyć [list. ForAll](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) , jeśli chcesz sprawdzić, czy wszystkie elementy listy spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="d7d69-178">You can use [List.forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="d7d69-179">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-179">The output is as follows:</span></span>

```console
true
false
```

<span data-ttu-id="d7d69-180">Podobnie, [list. forall2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) określa, czy wszystkie elementy w odpowiednich pozycjach na dwóch listach spełniają wyrażenie logiczne, które obejmuje każdą parę elementów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-180">Similarly, [List.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="d7d69-181">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-181">The output is as follows:</span></span>

```console
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="d7d69-182">Operacje sortowania na listach</span><span class="sxs-lookup"><span data-stu-id="d7d69-182">Sort Operations on Lists</span></span>

<span data-ttu-id="d7d69-183">Listy sortowania list [. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [list. SortBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)oraz [list. sortWith —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) .</span><span class="sxs-lookup"><span data-stu-id="d7d69-183">The [List.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy), and [List.sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) functions sort lists.</span></span> <span data-ttu-id="d7d69-184">Funkcja sortowania określa, które z tych trzech funkcji mają być używane.</span><span class="sxs-lookup"><span data-stu-id="d7d69-184">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="d7d69-185">`List.sort` używa domyślnego porównania ogólnego.</span><span class="sxs-lookup"><span data-stu-id="d7d69-185">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="d7d69-186">Porównanie ogólne używa operatorów globalnych opartych na funkcji porównania generycznej do porównywania wartości.</span><span class="sxs-lookup"><span data-stu-id="d7d69-186">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="d7d69-187">Wydajnie współpracuje z szeroką gamą typów elementów, takimi jak proste typy liczbowe, krotki, rekordy, związki rozłączne, listy, tablice i dowolny typ, który implementuje `System.IComparable` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-187">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="d7d69-188">Dla typów, które implementują `System.IComparable` , porównanie ogólne używa `System.IComparable.CompareTo()` funkcji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-188">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="d7d69-189">Porównanie ogólne działa również z ciągami, ale używa niezależnej od kultury kolejności sortowania.</span><span class="sxs-lookup"><span data-stu-id="d7d69-189">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="d7d69-190">Porównania generycznego nie należy używać w przypadku nieobsługiwanych typów, takich jak typy funkcji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-190">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="d7d69-191">Ponadto wydajność domyślnego porównania ogólnego jest Najlepsza dla małych typów strukturalnych; w przypadku większych typów strukturalnych, które muszą być porównywane i sortowane często, należy rozważyć zaimplementowanie `System.IComparable` i zapewnienie wydajnej implementacji `System.IComparable.CompareTo()` metody.</span><span class="sxs-lookup"><span data-stu-id="d7d69-191">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="d7d69-192">`List.sortBy` przyjmuje funkcję zwracającą wartość, która jest używana jako kryterium sortowania i `List.sortWith` Pobiera funkcję porównania jako argument.</span><span class="sxs-lookup"><span data-stu-id="d7d69-192">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="d7d69-193">Te ostatnie dwie funkcje są przydatne podczas pracy z typami, które nie obsługują porównania, lub gdy porównanie wymaga bardziej złożonej semantyki porównania, tak jak w przypadku ciągów z obsługą kultury.</span><span class="sxs-lookup"><span data-stu-id="d7d69-193">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="d7d69-194">Poniższy przykład ilustruje użycie `List.sort` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-194">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="d7d69-195">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-195">The output is as follows:</span></span>

```console
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="d7d69-196">Poniższy przykład ilustruje użycie `List.sortBy` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-196">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="d7d69-197">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-197">The output is as follows:</span></span>

```console
[1; -2; 4; 5; 8]
```

<span data-ttu-id="d7d69-198">W następnym przykładzie pokazano użycie `List.sortWith` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-198">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="d7d69-199">W tym przykładzie funkcja porównywania niestandardowego `compareWidgets` służy do pierwszego porównania jednego pola typu niestandardowego, a następnie drugiego, gdy wartości pierwszego pola są równe.</span><span class="sxs-lookup"><span data-stu-id="d7d69-199">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="d7d69-200">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-200">The output is as follows:</span></span>

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="d7d69-201">Operacje wyszukiwania na listach</span><span class="sxs-lookup"><span data-stu-id="d7d69-201">Search Operations on Lists</span></span>

<span data-ttu-id="d7d69-202">Dla list są obsługiwane liczne operacje wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="d7d69-202">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="d7d69-203">Najprostszy, [list. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), umożliwia znalezienie pierwszego elementu, który jest zgodny z danym warunkiem.</span><span class="sxs-lookup"><span data-stu-id="d7d69-203">The simplest, [List.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="d7d69-204">Poniższy przykład kodu demonstruje użycie programu `List.find` w celu znalezienia pierwszego numeru, który jest podzielny przez 5 na liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-204">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="d7d69-205">Wynik to 5.</span><span class="sxs-lookup"><span data-stu-id="d7d69-205">The result is 5.</span></span>

<span data-ttu-id="d7d69-206">Jeśli elementy muszą zostać przekształcone w pierwszej kolejności, wywołaj [listę. pobranie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), która pobiera funkcję, która zwraca opcję, i szuka pierwszej wartości opcji, która jest `Some(x)` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-206">If the elements must be transformed first, call [List.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="d7d69-207">Zamiast zwracać element, `List.pick` zwraca wynik `x` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-207">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="d7d69-208">Jeśli nie zostanie znaleziony pasujący element, `List.pick` zgłosi `System.Collections.Generic.KeyNotFoundException` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-208">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="d7d69-209">Poniższy kod ilustruje użycie `List.pick` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-209">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="d7d69-210">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-210">The output is as follows:</span></span>

```console
"b"
```

<span data-ttu-id="d7d69-211">Inna grupa operacji wyszukiwania, [list. tryFind —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) i powiązanych funkcji, zwracają wartość opcji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-211">Another group of search operations, [List.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) and related functions, return an option value.</span></span> <span data-ttu-id="d7d69-212">`List.tryFind`Funkcja zwraca pierwszy element listy, który spełnia warunek, jeśli taki element istnieje, ale wartość opcji, `None` Jeśli nie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-212">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="d7d69-213">Lista wariacji [. tryFindIndex —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) zwraca indeks elementu, jeśli został znaleziony, a nie sam element.</span><span class="sxs-lookup"><span data-stu-id="d7d69-213">The variation [List.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="d7d69-214">Te funkcje są zilustrowane w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-214">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="d7d69-215">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-215">The output is as follows:</span></span>

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="d7d69-216">Operacje arytmetyczne na listach</span><span class="sxs-lookup"><span data-stu-id="d7d69-216">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="d7d69-217">Typowe operacje arytmetyczne, takie jak sum i Average, są wbudowane w [moduł listy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="d7d69-217">Common arithmetic operations such as sum and average are built into the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="d7d69-218">Aby można było korzystać z [list. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), typ elementu listy musi obsługiwać `+` operatora i mieć wartość zerową.</span><span class="sxs-lookup"><span data-stu-id="d7d69-218">To work with [List.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="d7d69-219">Wszystkie wbudowane typy arytmetyczne spełniają te warunki.</span><span class="sxs-lookup"><span data-stu-id="d7d69-219">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="d7d69-220">Aby można było korzystać z [listy. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), typ elementu musi obsługiwać dzielenie bez reszty, która wyklucza typy całkowite, ale pozwala na używanie zmiennoprzecinkowych typów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-220">To work with [List.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="d7d69-221">Funkcje [list. sumBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) i [list. averageBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) przyjmują funkcję jako parametr, a wyniki tej funkcji są używane do obliczania wartości sum lub średniej.</span><span class="sxs-lookup"><span data-stu-id="d7d69-221">The [List.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) and [List.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="d7d69-222">Poniższy kod ilustruje użycie `List.sum` , `List.sumBy` , i `List.average` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-222">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="d7d69-223">Wynik to `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="d7d69-223">The output is `1.000000`.</span></span>

<span data-ttu-id="d7d69-224">Poniższy kod ilustruje użycie `List.averageBy` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-224">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="d7d69-225">Wynik to `5.5`.</span><span class="sxs-lookup"><span data-stu-id="d7d69-225">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="d7d69-226">Listy i krotki</span><span class="sxs-lookup"><span data-stu-id="d7d69-226">Lists and Tuples</span></span>

<span data-ttu-id="d7d69-227">Listy zawierające krotki mogą być przetwarzane przy użyciu funkcji zip i rozpakowania.</span><span class="sxs-lookup"><span data-stu-id="d7d69-227">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="d7d69-228">Te funkcje łączą dwie listy pojedynczych wartości w jedną listę spójnych kolekcji lub dzielą jedną listę krotek na dwie listy pojedynczych wartości.</span><span class="sxs-lookup"><span data-stu-id="d7d69-228">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="d7d69-229">Najprostsza funkcja [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) pobiera dwie listy pojedynczych elementów i tworzy pojedynczą listę par krotek.</span><span class="sxs-lookup"><span data-stu-id="d7d69-229">The simplest [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="d7d69-230">Inna wersja, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), pobiera trzy listy pojedynczych elementów i tworzy pojedynczą listę krotek, które mają trzy elementy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-230">Another version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="d7d69-231">Poniższy przykład kodu demonstruje użycie `List.zip` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-231">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="d7d69-232">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-232">The output is as follows:</span></span>

```console
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="d7d69-233">Poniższy przykład kodu demonstruje użycie `List.zip3` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-233">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="d7d69-234">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-234">The output is as follows:</span></span>

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="d7d69-235">Odpowiednie wersje rozpakować, [list. rozpakować](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) i [list. unzip3 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), przyjmują listy krotek i listy zwracane w spójnej kolekcji, gdzie pierwsza lista zawiera wszystkie elementy, które wcześniej znajdowały się w każdej kolekcji, a druga lista zawiera drugi element każdej krotki itd.</span><span class="sxs-lookup"><span data-stu-id="d7d69-235">The corresponding unzip versions, [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) and [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="d7d69-236">Poniższy przykład kodu demonstruje użycie [list.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)rozpakowywanie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-236">The following code example demonstrates the use of [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="d7d69-237">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-237">The output is as follows:</span></span>

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="d7d69-238">Poniższy przykład kodu demonstruje użycie [list. unzip3 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3).</span><span class="sxs-lookup"><span data-stu-id="d7d69-238">The following code example demonstrates the use of [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="d7d69-239">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-239">The output is as follows:</span></span>

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="d7d69-240">Działa na elementach listy</span><span class="sxs-lookup"><span data-stu-id="d7d69-240">Operating on List Elements</span></span>

<span data-ttu-id="d7d69-241">Język F # obsługuje wiele operacji na elementach listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-241">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="d7d69-242">Najprostszą jest [Lista. ITER](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), która umożliwia wywoływanie funkcji dla każdego elementu listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-242">The simplest is [List.iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="d7d69-243">Wariacje obejmują [list. iter2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), które umożliwiają wykonywanie operacji na elementach dwóch list, [list. iteri —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), które przypominają, `List.iter` że indeks każdego elementu jest przenoszona jako argument do funkcji, która jest wywoływana dla każdego elementu, i [list. iteri2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), który jest kombinacją funkcji `List.iter2` i `List.iteri` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-243">Variations include [List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), which enables you to perform an operation on elements of two lists, [List.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="d7d69-244">Poniższy przykład kodu ilustruje te funkcje.</span><span class="sxs-lookup"><span data-stu-id="d7d69-244">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="d7d69-245">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-245">The output is as follows:</span></span>

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="d7d69-246">Inna często używana funkcja, która przekształca elementy listy to [list. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), która umożliwia zastosowanie funkcji do każdego elementu listy i umieszczenie wszystkich wyników w nowej liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-246">Another frequently used function that transforms list elements is [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="d7d69-247">[List. MAP2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) i [list. map3 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) są odmianami, które pobierają wiele list.</span><span class="sxs-lookup"><span data-stu-id="d7d69-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) and [List.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) are variations that take multiple lists.</span></span> <span data-ttu-id="d7d69-248">Można również użyć [list. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) i [list. mapi2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), jeśli oprócz elementu, funkcja musi zostać przeniesiona indeks każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-248">You can also use [List.mapi](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) and [List.mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="d7d69-249">Jedyną różnicą między `List.mapi2` i `List.mapi` jest to, że `List.mapi2` Program współpracuje z dwiema listami.</span><span class="sxs-lookup"><span data-stu-id="d7d69-249">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="d7d69-250">Poniższy przykład ilustruje [list. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span><span class="sxs-lookup"><span data-stu-id="d7d69-250">The following example illustrates [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="d7d69-251">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-251">The output is as follows:</span></span>

```console
[2; 3; 4]
```

<span data-ttu-id="d7d69-252">W poniższym przykładzie pokazano użycie `List.map2` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-252">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="d7d69-253">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-253">The output is as follows:</span></span>

```console
[5; 7; 9]
```

<span data-ttu-id="d7d69-254">W poniższym przykładzie pokazano użycie `List.map3` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-254">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="d7d69-255">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-255">The output is as follows:</span></span>

```console
[7; 10; 13]
```

<span data-ttu-id="d7d69-256">W poniższym przykładzie pokazano użycie `List.mapi` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-256">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="d7d69-257">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-257">The output is as follows:</span></span>

```console
[1; 3; 5]
```

<span data-ttu-id="d7d69-258">W poniższym przykładzie pokazano użycie `List.mapi2` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-258">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="d7d69-259">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-259">The output is as follows:</span></span>

```console
[0; 7; 18]
```

<span data-ttu-id="d7d69-260">[List. Collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) przypomina `List.map` , z tą różnicą, że każdy element tworzy listę i wszystkie te listy są łączone w ostateczną listę.</span><span class="sxs-lookup"><span data-stu-id="d7d69-260">[List.collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="d7d69-261">W poniższym kodzie każdy element listy generuje trzy liczby.</span><span class="sxs-lookup"><span data-stu-id="d7d69-261">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="d7d69-262">Wszystkie te dane są zbierane w jednej liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-262">These are all collected into one list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="d7d69-263">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-263">The output is as follows:</span></span>

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="d7d69-264">Można również użyć [list. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), który przyjmuje warunek logiczny i tworzy nową listę, która składa się tylko z elementów, które spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="d7d69-264">You can also use [List.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="d7d69-265">Lista wyników `[2; 4; 6]` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-265">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="d7d69-266">Kombinacja map i filtru, [list. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) umożliwia przekształcanie i zaznaczanie elementów w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-266">A combination of map and filter, [List.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="d7d69-267">`List.choose` stosuje funkcję, która zwraca opcję do każdego elementu listy i zwraca nową listę wyników dla elementów, gdy funkcja zwraca wartość opcji `Some` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-267">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="d7d69-268">Poniższy kod ilustruje użycie `List.choose` do zaznaczania wersalików wyrazów z listy wyrazów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-268">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="d7d69-269">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d7d69-269">The output is as follows:</span></span>

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="d7d69-270">Działa na wielu listach</span><span class="sxs-lookup"><span data-stu-id="d7d69-270">Operating on Multiple Lists</span></span>

<span data-ttu-id="d7d69-271">Listy można łączyć ze sobą.</span><span class="sxs-lookup"><span data-stu-id="d7d69-271">Lists can be joined together.</span></span> <span data-ttu-id="d7d69-272">Aby dołączyć dwie listy do jednej, użyj [list. Append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span><span class="sxs-lookup"><span data-stu-id="d7d69-272">To join two lists into one, use [List.append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span></span> <span data-ttu-id="d7d69-273">Aby dołączyć więcej niż dwie listy, użyj [list. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span><span class="sxs-lookup"><span data-stu-id="d7d69-273">To join more than two lists, use [List.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="d7d69-274">Operacje składania i skanowania</span><span class="sxs-lookup"><span data-stu-id="d7d69-274">Fold and Scan Operations</span></span>

<span data-ttu-id="d7d69-275">Niektóre operacje na listach obejmują wzajemne zależności między wszystkimi elementami listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-275">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="d7d69-276">Operacje składania i skanowania są podobne `List.iter` i `List.map` w przypadku wywołania funkcji dla każdego elementu, ale te operacje zapewniają dodatkowy parametr o nazwie *akumulowana* , który przenosi informacje za pomocą obliczeń.</span><span class="sxs-lookup"><span data-stu-id="d7d69-276">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="d7d69-277">Służy `List.fold` do wykonywania obliczeń na liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-277">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="d7d69-278">Poniższy przykład kodu demonstruje użycie [list. zgięcie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) do wykonywania różnych operacji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-278">The following code example demonstrates the use of [List.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) to perform various operations.</span></span>

<span data-ttu-id="d7d69-279">Lista jest przesunięta; akumulacja `acc` jest wartością, która jest przenoszona wraz z przeprowadzeniem obliczeń.</span><span class="sxs-lookup"><span data-stu-id="d7d69-279">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="d7d69-280">Pierwszy argument przyjmuje wartość akumulowana i element list i zwraca pośredni wynik obliczeń dla tego elementu listy.</span><span class="sxs-lookup"><span data-stu-id="d7d69-280">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="d7d69-281">Drugi argument jest początkową wartością akumulowana.</span><span class="sxs-lookup"><span data-stu-id="d7d69-281">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="d7d69-282">Wersje tych funkcji, które mają cyfrę w nazwie funkcji, działają na więcej niż jednej liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-282">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="d7d69-283">Na przykład, [list. fold2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) wykonuje obliczenia na dwóch listach.</span><span class="sxs-lookup"><span data-stu-id="d7d69-283">For example, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) performs computations on two lists.</span></span>

<span data-ttu-id="d7d69-284">Poniższy przykład ilustruje użycie `List.fold2` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-284">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="d7d69-285">`List.fold` and [list. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) różni się, która `List.fold` zwraca końcową wartość dodatkowego parametru, ale `List.scan` zwraca listę wartości pośrednich (wraz z wartością końcową) dodatkowego parametru.</span><span class="sxs-lookup"><span data-stu-id="d7d69-285">`List.fold` and [List.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="d7d69-286">Każda z tych funkcji zawiera odwrotną odmianę, na przykład [list. foldBack —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), która różni się w kolejności, w jakiej jest przesunięty listy, i kolejności argumentów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-286">Each of these functions includes a reverse variation, for example, [List.foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="d7d69-287">Ponadto `List.fold` i `List.foldBack` mają różne odmiany, [list. fold2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) i [list. foldBack2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), które pobierają dwie listy o równej długości.</span><span class="sxs-lookup"><span data-stu-id="d7d69-287">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) and [List.foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), that take two lists of equal length.</span></span> <span data-ttu-id="d7d69-288">Funkcja, która jest wykonywana dla każdego elementu, może użyć odpowiednich elementów obu list do wykonania pewnej akcji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-288">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="d7d69-289">Typy elementów dwóch list mogą być różne, jak w poniższym przykładzie, w którym jedna lista zawiera kwoty transakcji dla konta bankowego, a druga lista zawiera typ transakcji: kaucja lub wycofanie.</span><span class="sxs-lookup"><span data-stu-id="d7d69-289">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="d7d69-290">W przypadku obliczeń, takich jak suma `List.fold` i `List.foldBack` ma ten sam skutek, ponieważ wynik nie zależy od kolejności przechodzenia.</span><span class="sxs-lookup"><span data-stu-id="d7d69-290">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="d7d69-291">W poniższym przykładzie `List.foldBack` jest używany do dodawania elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="d7d69-291">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="d7d69-292">Poniższy przykład zwraca dane do przykładu konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="d7d69-292">The following example returns to the bank account example.</span></span> <span data-ttu-id="d7d69-293">Tym razem zostanie dodany nowy typ transakcji: Obliczanie odsetek.</span><span class="sxs-lookup"><span data-stu-id="d7d69-293">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="d7d69-294">Saldo końcowe jest teraz zależne od kolejności transakcji.</span><span class="sxs-lookup"><span data-stu-id="d7d69-294">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="d7d69-295">Lista funkcji [. Redukcja](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) jest nieco taka sama jak `List.fold` i `List.scan` , z tą różnicą, że zamiast przechodzenia do innego akumulowana, `List.reduce` przyjmuje funkcję, która przyjmuje dwa argumenty typu elementu zamiast tylko jednego, a jeden z tych argumentów pełni rolę akumulowana, co oznacza, że przechowuje wynik pośredni obliczenia.</span><span class="sxs-lookup"><span data-stu-id="d7d69-295">The function [List.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="d7d69-296">`List.reduce` zaczyna się od działania pierwszego z dwóch elementów listy, a następnie używa wyniku operacji wraz z następnym elementem.</span><span class="sxs-lookup"><span data-stu-id="d7d69-296">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="d7d69-297">Ponieważ nie istnieje oddzielny obiekt, który ma własny typ, może być używany zamiast tylko wtedy, gdy obiekt, który ma ten `List.reduce` `List.fold` sam typ i typ elementu.</span><span class="sxs-lookup"><span data-stu-id="d7d69-297">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="d7d69-298">Poniższy kod ilustruje użycie `List.reduce` .</span><span class="sxs-lookup"><span data-stu-id="d7d69-298">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="d7d69-299">`List.reduce` zgłasza wyjątek, jeśli podana lista nie zawiera żadnych elementów.</span><span class="sxs-lookup"><span data-stu-id="d7d69-299">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="d7d69-300">W poniższym kodzie, pierwsze wywołanie do wyrażenia lambda otrzymuje argumenty 2 i 4 i zwraca 6, a następne wywołanie otrzymuje argumenty 6 i 10, więc wynik wynosi 16.</span><span class="sxs-lookup"><span data-stu-id="d7d69-300">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="d7d69-301">Konwertowanie między listami i innymi typami kolekcji</span><span class="sxs-lookup"><span data-stu-id="d7d69-301">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="d7d69-302">`List`Moduł zawiera funkcje do konwersji do i z obu sekwencji i tablic.</span><span class="sxs-lookup"><span data-stu-id="d7d69-302">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="d7d69-303">Aby przekonwertować sekwencję na lub z sekwencji, użyj [list. toSeq —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) lub [list. ofSeq —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span><span class="sxs-lookup"><span data-stu-id="d7d69-303">To convert to or from a sequence, use [List.toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) or [List.ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span></span> <span data-ttu-id="d7d69-304">Aby przekonwertować na tablicę lub z niej, użyj [list. ToArray —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) lub [list. ofArray —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span><span class="sxs-lookup"><span data-stu-id="d7d69-304">To convert to or from an array, use [List.toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) or [List.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="d7d69-305">Dodatkowe operacje</span><span class="sxs-lookup"><span data-stu-id="d7d69-305">Additional Operations</span></span>

<span data-ttu-id="d7d69-306">Aby uzyskać informacje na temat dodatkowych operacji na listach, zobacz temat informacje o [bibliotece.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)</span><span class="sxs-lookup"><span data-stu-id="d7d69-306">For information about additional operations on lists, see the library reference topic [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7d69-307">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d7d69-307">See also</span></span>

- [<span data-ttu-id="d7d69-308">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="d7d69-308">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d7d69-309">Typy F#</span><span class="sxs-lookup"><span data-stu-id="d7d69-309">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="d7d69-310">Sekwencje</span><span class="sxs-lookup"><span data-stu-id="d7d69-310">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="d7d69-311">Tablice</span><span class="sxs-lookup"><span data-stu-id="d7d69-311">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="d7d69-312">Opcje</span><span class="sxs-lookup"><span data-stu-id="d7d69-312">Options</span></span>](options.md)
