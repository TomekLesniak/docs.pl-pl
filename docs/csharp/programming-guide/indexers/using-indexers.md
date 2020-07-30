---
title: Korzystanie z indeksatorów — Przewodnik programowania w języku C#
description: Dowiedz się, jak zadeklarować indeksator i używać go dla klasy, struktury lub interfejsu w języku C#. Ten artykuł zawiera przykładowy kod.
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: a8a9e05c1d2e44841177a924c6ff51c6c9e6a05a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301869"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="ad73a-104">Używanie indeksatorów (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ad73a-104">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="ad73a-105">Indeksatory to wygoda składni, która umożliwia tworzenie [klasy](../../language-reference/keywords/class.md), [struktury](../../language-reference/builtin-types/struct.md)lub [interfejsu](../../language-reference/keywords/interface.md) , do którego aplikacje klienckie mogą uzyskiwać dostęp jako tablica.</span><span class="sxs-lookup"><span data-stu-id="ad73a-105">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="ad73a-106">Kompilator wygeneruje `Item` Właściwość (lub właściwość o nazwie Alternatywnie <xref:System.Runtime.CompilerServices.IndexerNameAttribute> , jeśli jest obecna) i odpowiednie metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="ad73a-106">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="ad73a-107">Indeksatory są najczęściej implementowane w typach, których głównym celem jest hermetyzacja wewnętrznej kolekcji lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="ad73a-107">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="ad73a-108">Załóżmy na przykład, że masz klasę `TempRecord` , która reprezentuje temperaturę w numerze Fahrenheita w ciągu 10 różnych razy w okresie 24 godzin.</span><span class="sxs-lookup"><span data-stu-id="ad73a-108">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="ad73a-109">Klasa zawiera `temps` tablicę typu `float[]` do przechowywania wartości temperatury.</span><span class="sxs-lookup"><span data-stu-id="ad73a-109">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="ad73a-110">Implementując indeksator w tej klasie, klienci mogą uzyskać dostęp do temperatury w `TempRecord` wystąpieniu jako `float temp = tempRecord[4]` zamiast `float temp = tempRecord.temps[4]` .</span><span class="sxs-lookup"><span data-stu-id="ad73a-110">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="ad73a-111">Notacja indeksatora nie tylko upraszcza składnię aplikacji klienckich; sprawia również, że Klasa i jej cel są bardziej intuicyjne dla innych deweloperów do zrozumienia.</span><span class="sxs-lookup"><span data-stu-id="ad73a-111">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="ad73a-112">Aby zadeklarować indeksator dla klasy lub struktury, użyj słowa kluczowego [this](../../language-reference/keywords/this.md) , jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="ad73a-112">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="ad73a-113">Deklarowanie indeksatora spowoduje automatyczne wygenerowanie właściwości o nazwie `Item` w obiekcie.</span><span class="sxs-lookup"><span data-stu-id="ad73a-113">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="ad73a-114">`Item`Właściwość nie jest bezpośrednio dostępna z [wyrażenia dostępu do elementu członkowskiego](../../language-reference/operators/member-access-operators.md#member-access-expression-)wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="ad73a-114">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="ad73a-115">Ponadto, jeśli dodasz własną `Item` Właściwość do obiektu za pomocą indeksatora, otrzymasz [błąd kompilatora CS0102](../../misc/cs0102.md).</span><span class="sxs-lookup"><span data-stu-id="ad73a-115">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="ad73a-116">Aby uniknąć tego błędu, użyj <xref:System.Runtime.CompilerServices.IndexerNameAttribute> nazwy indeksatora, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="ad73a-116">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad73a-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ad73a-117">Remarks</span></span>

<span data-ttu-id="ad73a-118">Typ indeksatora i typ jego parametrów muszą być co najmniej tak samo samo jak indeksator.</span><span class="sxs-lookup"><span data-stu-id="ad73a-118">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="ad73a-119">Aby uzyskać więcej informacji na temat poziomów ułatwień dostępu, zobacz [Modyfikatory dostępu](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ad73a-119">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="ad73a-120">Aby uzyskać więcej informacji na temat używania indeksatorów z interfejsem, zobacz [indeksatory interfejsów](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="ad73a-120">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="ad73a-121">Podpis indeksatora składa się z liczby i typów jego parametrów formalnych.</span><span class="sxs-lookup"><span data-stu-id="ad73a-121">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="ad73a-122">Nie zawiera typu indeksatora ani nazw parametrów formalnych.</span><span class="sxs-lookup"><span data-stu-id="ad73a-122">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="ad73a-123">Jeśli zadeklarujesz więcej niż jeden indeksator w tej samej klasie, muszą mieć różne podpisy.</span><span class="sxs-lookup"><span data-stu-id="ad73a-123">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="ad73a-124">Wartość indeksatora nie została sklasyfikowana jako zmienna; w związku z tym nie można przekazać wartości indeksatora jako parametru [ref](../../language-reference/keywords/ref.md) lub [out](../../language-reference/keywords/out-parameter-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="ad73a-124">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="ad73a-125">Aby podać indeksator przy użyciu nazwy, która może być używana przez inne języki, <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType> jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="ad73a-125">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="ad73a-126">Ten indeksator będzie miał nazwę `TheItem` , ponieważ jest zastępowany przez atrybut nazwy indeksatora.</span><span class="sxs-lookup"><span data-stu-id="ad73a-126">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="ad73a-127">Domyślnie nazwa indeksatora to `Item` .</span><span class="sxs-lookup"><span data-stu-id="ad73a-127">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="ad73a-128">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="ad73a-128">Example 1</span></span>

<span data-ttu-id="ad73a-129">Poniższy przykład pokazuje, jak zadeklarować pole tablicy prywatnej, `temps` i indeksator.</span><span class="sxs-lookup"><span data-stu-id="ad73a-129">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="ad73a-130">Indeksator umożliwia bezpośredni dostęp do wystąpienia `tempRecord[i]` .</span><span class="sxs-lookup"><span data-stu-id="ad73a-130">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="ad73a-131">Alternatywą dla korzystania z indeksatora jest zadeklarowanie tablicy jako [publicznego](../../language-reference/keywords/public.md) elementu członkowskiego i dostęp do jej członków, `tempRecord.temps[i]` bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="ad73a-131">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="ad73a-132">Należy zauważyć, że gdy jest oceniany dostęp indeksatora, na przykład w `Console.Write` instrukcji metoda dostępu [Get](../../language-reference/keywords/get.md) jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="ad73a-132">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="ad73a-133">W związku z tym, jeśli żadna `get` metoda dostępu nie istnieje, wystąpi błąd w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ad73a-133">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="ad73a-134">Indeksowanie przy użyciu innych wartości</span><span class="sxs-lookup"><span data-stu-id="ad73a-134">Indexing using other values</span></span>

<span data-ttu-id="ad73a-135">Język C# nie ogranicza typu parametru indeksatora do liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="ad73a-135">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="ad73a-136">Na przykład przydatne może być użycie ciągu z indeksatorem.</span><span class="sxs-lookup"><span data-stu-id="ad73a-136">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="ad73a-137">Takie indeksatory mogą być implementowane przez wyszukanie ciągu w kolekcji i zwrócenie odpowiedniej wartości.</span><span class="sxs-lookup"><span data-stu-id="ad73a-137">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="ad73a-138">Metody dostępu mogą być przeciążone, a wersje typu String i Integer mogą współistnieć.</span><span class="sxs-lookup"><span data-stu-id="ad73a-138">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="ad73a-139">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="ad73a-139">Example 2</span></span>

<span data-ttu-id="ad73a-140">Poniższy przykład deklaruje klasę, w której są przechowywane dni tygodnia.</span><span class="sxs-lookup"><span data-stu-id="ad73a-140">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="ad73a-141">`get`Metoda dostępu przyjmuje ciąg, nazwę dnia i zwraca odpowiednią liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="ad73a-141">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="ad73a-142">Na przykład "Niedziela" zwraca 0, "poniedziałek" zwraca 1 itd.</span><span class="sxs-lookup"><span data-stu-id="ad73a-142">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="ad73a-143">Przykład zużywający 2</span><span class="sxs-lookup"><span data-stu-id="ad73a-143">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="ad73a-144">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="ad73a-144">Example 3</span></span>

<span data-ttu-id="ad73a-145">Poniższy przykład deklaruje klasę, która przechowuje dni tygodnia przy użyciu <xref:System.DayOfWeek?displayProperty=fullName> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ad73a-145">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="ad73a-146">`get`Metoda dostępu przyjmuje `DayOfWeek` , wartość dnia i zwraca odpowiednią liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="ad73a-146">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="ad73a-147">Na przykład `DayOfWeek.Sunday` zwraca wartość 0, `DayOfWeek.Monday` zwraca wartość 1 i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="ad73a-147">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="ad73a-148">Przykład zużywający 3</span><span class="sxs-lookup"><span data-stu-id="ad73a-148">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="ad73a-149">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="ad73a-149">Robust programming</span></span>

<span data-ttu-id="ad73a-150">Istnieją dwa główne sposoby, w których można ulepszyć zabezpieczenia i niezawodność indeksatorów:</span><span class="sxs-lookup"><span data-stu-id="ad73a-150">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="ad73a-151">Należy pamiętać o uwzględnieniu niektórych typów strategii obsługi błędów, aby obsłużyć prawdopodobieństwo przekazania kodu klienta w nieprawidłowej wartości indeksu.</span><span class="sxs-lookup"><span data-stu-id="ad73a-151">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="ad73a-152">W pierwszym przykładzie wcześniej w tym temacie Klasa TempRecord zawiera właściwość length, która umożliwia zweryfikowanie danych wejściowych przed przekazaniem ich do indeksatora.</span><span class="sxs-lookup"><span data-stu-id="ad73a-152">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="ad73a-153">Można również umieścić kod obsługi błędu wewnątrz indeksatora.</span><span class="sxs-lookup"><span data-stu-id="ad73a-153">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="ad73a-154">Upewnij się, że dla użytkowników występują wyjątki, które można zgłosić w metodzie dostępu indeksatora.</span><span class="sxs-lookup"><span data-stu-id="ad73a-154">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="ad73a-155">Ustaw dostępność metod dostępu [Get](../../language-reference/keywords/get.md) i [Set](../../language-reference/keywords/set.md) tak, aby były tak restrykcyjne, jak to uzasadnione.</span><span class="sxs-lookup"><span data-stu-id="ad73a-155">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="ad73a-156">Jest to ważne w przypadku `set` metody dostępu w szczególności.</span><span class="sxs-lookup"><span data-stu-id="ad73a-156">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="ad73a-157">Aby uzyskać więcej informacji, zobacz [ograniczanie dostępności metody](../classes-and-structs/restricting-accessor-accessibility.md)dostępu.</span><span class="sxs-lookup"><span data-stu-id="ad73a-157">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad73a-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ad73a-158">See also</span></span>

- [<span data-ttu-id="ad73a-159">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ad73a-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ad73a-160">Indexers (Indeksatory)</span><span class="sxs-lookup"><span data-stu-id="ad73a-160">Indexers</span></span>](./index.md)
- [<span data-ttu-id="ad73a-161">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ad73a-161">Properties</span></span>](../classes-and-structs/properties.md)
