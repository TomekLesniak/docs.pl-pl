---
title: Rekordy
description: 'Dowiedz się, w jaki sposób rekordy F # reprezentują proste agregowanie nazwanych wartości, opcjonalnie z elementami członkowskimi.'
ms.date: 08/15/2020
ms.openlocfilehash: 182b2e83c3940c866197052af102787a96e49c54
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559053"
---
# <a name="records"></a><span data-ttu-id="0d738-103">Rekordy</span><span class="sxs-lookup"><span data-stu-id="0d738-103">Records</span></span>

<span data-ttu-id="0d738-104">Rekordy reprezentują proste Agregowanie wartości nazwanych, opcjonalnie z elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="0d738-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="0d738-105">Mogą to być struktury lub typy referencyjne.</span><span class="sxs-lookup"><span data-stu-id="0d738-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="0d738-106">Domyślnie są to typy odwołań.</span><span class="sxs-lookup"><span data-stu-id="0d738-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d738-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="0d738-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="0d738-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0d738-108">Remarks</span></span>

<span data-ttu-id="0d738-109">W poprzedniej składni, *TypeName* jest nazwą typu rekordu, *Label1* i *etykiety 2* są nazwami wartości, zwanymi *etykietami*, a *Type1* i *Type2* są typami tych wartości.</span><span class="sxs-lookup"><span data-stu-id="0d738-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="0d738-110">*Lista elementów członkowskich* jest opcjonalną listą elementów członkowskich typu.</span><span class="sxs-lookup"><span data-stu-id="0d738-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="0d738-111">Możesz użyć atrybutu, `[<Struct>]` Aby utworzyć rekord struktury, a nie rekord, który jest typem referencyjnym.</span><span class="sxs-lookup"><span data-stu-id="0d738-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="0d738-112">Poniżej przedstawiono kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="0d738-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="0d738-113">Gdy każda etykieta znajduje się w osobnym wierszu, średnik jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="0d738-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="0d738-114">Można ustawić wartości w wyrażeniach nazywanych *wyrażeniami rekordów*.</span><span class="sxs-lookup"><span data-stu-id="0d738-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="0d738-115">Kompilator wnioskuje typ z użytych etykiet (Jeśli etykiety są wystarczająco odrębne od tych z innych typów rekordów).</span><span class="sxs-lookup"><span data-stu-id="0d738-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="0d738-116">Nawiasy klamrowe ({}) otaczają wyrażenie rekordu.</span><span class="sxs-lookup"><span data-stu-id="0d738-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="0d738-117">Poniższy kod przedstawia wyrażenie rekordu, które inicjuje rekord z trzema elementami zmiennoprzecinkowymi z etykietami `x` `y` i `z` .</span><span class="sxs-lookup"><span data-stu-id="0d738-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="0d738-118">Nie używaj skróconej formy, jeśli może istnieć inny typ, który ma również te same etykiety.</span><span class="sxs-lookup"><span data-stu-id="0d738-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="0d738-119">Etykiety ostatnio zadeklarowanego typu mają pierwszeństwo przed poprzednimi zadeklarowanymi typem, więc w poprzednim przykładzie `mypoint3D` jest wywnioskowane `Point3D` .</span><span class="sxs-lookup"><span data-stu-id="0d738-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="0d738-120">Można jawnie określić typ rekordu, jak w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="0d738-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="0d738-121">Metody można definiować dla typów rekordów, tak jak w przypadku typów klas.</span><span class="sxs-lookup"><span data-stu-id="0d738-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="0d738-122">Tworzenie rekordów przy użyciu wyrażeń rekordu</span><span class="sxs-lookup"><span data-stu-id="0d738-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="0d738-123">Rekordy można inicjować przy użyciu etykiet, które są zdefiniowane w rekordzie.</span><span class="sxs-lookup"><span data-stu-id="0d738-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="0d738-124">Wyrażenie, które jest nazywane *wyrażeniem rekordu*.</span><span class="sxs-lookup"><span data-stu-id="0d738-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="0d738-125">Użyj nawiasów klamrowych, aby ująć wyrażenie rekordu i użyć średnika jako ogranicznika.</span><span class="sxs-lookup"><span data-stu-id="0d738-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="0d738-126">Poniższy przykład pokazuje, jak utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="0d738-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="0d738-127">Średniki po ostatnim polu w wyrażeniu rekordu i w definicji typu są opcjonalne, bez względu na to, czy wszystkie pola znajdują się w jednym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0d738-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="0d738-128">Podczas tworzenia rekordu należy podać wartości dla każdego pola.</span><span class="sxs-lookup"><span data-stu-id="0d738-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="0d738-129">Nie można odwołać się do wartości innych pól w wyrażeniu inicjalizacji dla każdego pola.</span><span class="sxs-lookup"><span data-stu-id="0d738-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="0d738-130">W poniższym kodzie typ `myRecord2` jest wywnioskowany na podstawie nazw pól.</span><span class="sxs-lookup"><span data-stu-id="0d738-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="0d738-131">Opcjonalnie można jawnie określić nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="0d738-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="0d738-132">Inna forma konstruowania rekordów może być przydatna, gdy trzeba skopiować istniejący rekord i ewentualnie zmienić niektóre wartości pól.</span><span class="sxs-lookup"><span data-stu-id="0d738-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="0d738-133">Ilustruje to poniższy wiersz kodu.</span><span class="sxs-lookup"><span data-stu-id="0d738-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="0d738-134">Ta forma wyrażenia rekordu jest nazywana *wyrażeniem Copy i Update Record*.</span><span class="sxs-lookup"><span data-stu-id="0d738-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="0d738-135">Rekordy są domyślnie niezmienne; można jednak łatwo tworzyć zmodyfikowane rekordy przy użyciu wyrażenia Copy i Update.</span><span class="sxs-lookup"><span data-stu-id="0d738-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="0d738-136">Można również jawnie określić pole modyfikowalne.</span><span class="sxs-lookup"><span data-stu-id="0d738-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="0d738-137">Nie używaj atrybutu DefaultValue z polami rekordów.</span><span class="sxs-lookup"><span data-stu-id="0d738-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="0d738-138">Lepszym rozwiązaniem jest zdefiniowanie domyślnych wystąpień rekordów z polami, które są inicjowane do wartości domyślnych, a następnie użycie wyrażenia Kopiuj i Aktualizuj rekord, aby ustawić wszystkie pola, które różnią się od wartości domyślnych.</span><span class="sxs-lookup"><span data-stu-id="0d738-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="0d738-139">Tworzenie wzajemnie rekurencyjnych rekordów</span><span class="sxs-lookup"><span data-stu-id="0d738-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="0d738-140">Czasami podczas tworzenia rekordu można zależeć od innego typu, który ma zostać zdefiniowany później.</span><span class="sxs-lookup"><span data-stu-id="0d738-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="0d738-141">Jest to błąd kompilacji, chyba że zostanie zdefiniowany typ rekordu, który ma być wzajemnie cykliczne.</span><span class="sxs-lookup"><span data-stu-id="0d738-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="0d738-142">Definiowanie wzajemnie cyklicznych rekordów odbywa się za pomocą `and` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="0d738-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="0d738-143">Dzięki temu można połączyć 2 lub więcej typów rekordów jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="0d738-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="0d738-144">Na przykład poniższy kod definiuje a `Person` i `Address` Typ jako wzajemnie cyklicznie:</span><span class="sxs-lookup"><span data-stu-id="0d738-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

<span data-ttu-id="0d738-145">Jeśli zdefiniowano poprzedni przykład bez `and` słowa kluczowego, nie zostanie on skompilowany.</span><span class="sxs-lookup"><span data-stu-id="0d738-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="0d738-146">`and`Słowo kluczowe jest wymagane dla wzajemnie cyklicznych definicji.</span><span class="sxs-lookup"><span data-stu-id="0d738-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="0d738-147">Dopasowanie wzorca z rekordami</span><span class="sxs-lookup"><span data-stu-id="0d738-147">Pattern Matching with Records</span></span>

<span data-ttu-id="0d738-148">Rekordy mogą być używane z dopasowywaniem do wzorca.</span><span class="sxs-lookup"><span data-stu-id="0d738-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="0d738-149">Niektóre pola można określić jawnie i podać zmienne dla innych pól, które będą przypisywane w przypadku wystąpienia dopasowania.</span><span class="sxs-lookup"><span data-stu-id="0d738-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="0d738-150">Pokazano to w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="0d738-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="0d738-151">Dane wyjściowe tego kodu są następujące.</span><span class="sxs-lookup"><span data-stu-id="0d738-151">The output of this code is as follows.</span></span>

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="records-and-members"></a><span data-ttu-id="0d738-152">Rekordy i elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="0d738-152">Records and members</span></span>

<span data-ttu-id="0d738-153">Możesz określić elementy członkowskie dla rekordów, tak jak w przypadku klas.</span><span class="sxs-lookup"><span data-stu-id="0d738-153">You can specify members on records much like you can with classes.</span></span> <span data-ttu-id="0d738-154">Nie ma obsługi dla pól.</span><span class="sxs-lookup"><span data-stu-id="0d738-154">There is no support for fields.</span></span> <span data-ttu-id="0d738-155">Typowym podejściem jest zdefiniowanie `Default` statycznej składowej w celu łatwego konstruowania rekordów:</span><span class="sxs-lookup"><span data-stu-id="0d738-155">A common approach is to define a `Default` static member for easy record construction:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    static member Default =
        { Name = "Phillip"
          Age = 12
          Address = "123 happy fun street" }

let defaultPerson = Person.Default
```

<span data-ttu-id="0d738-156">Jeśli używasz samego identyfikatora, identyfikator ten odnosi się do wystąpienia rekordu, którego Członek jest wywoływany:</span><span class="sxs-lookup"><span data-stu-id="0d738-156">If you use a self identifier, that identifier refers to the instance of the record whose member is called:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    member this.WeirdToString() =
        this.Name + this.Address + string this.Age

let p = { Name = "a"; Age = 12; Address = "abc123 }
let weirdString = p.WeirdToString()
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="0d738-157">Różnice między rekordami i klasami</span><span class="sxs-lookup"><span data-stu-id="0d738-157">Differences Between Records and Classes</span></span>

<span data-ttu-id="0d738-158">Pola rekordów różnią się od klas, które są automatycznie uwidaczniane jako właściwości i są używane podczas tworzenia i kopiowania rekordów.</span><span class="sxs-lookup"><span data-stu-id="0d738-158">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="0d738-159">Konstrukcja rekordu różni się także od konstrukcji klasy.</span><span class="sxs-lookup"><span data-stu-id="0d738-159">Record construction also differs from class construction.</span></span> <span data-ttu-id="0d738-160">W typie rekordu nie można zdefiniować konstruktora.</span><span class="sxs-lookup"><span data-stu-id="0d738-160">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="0d738-161">Zamiast tego stosuje się składnię konstrukcyjną opisaną w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="0d738-161">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="0d738-162">Klasy nie mają bezpośredniej relacji między parametrami konstruktora, polami i właściwościami.</span><span class="sxs-lookup"><span data-stu-id="0d738-162">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="0d738-163">Podobnie jak w przypadku typów Unii i struktury, rekordy mają semantykę równości strukturalnej.</span><span class="sxs-lookup"><span data-stu-id="0d738-163">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="0d738-164">Klasy mają semantykę równości odwołań.</span><span class="sxs-lookup"><span data-stu-id="0d738-164">Classes have reference equality semantics.</span></span> <span data-ttu-id="0d738-165">Poniższy przykład kodu demonstruje ten sposób.</span><span class="sxs-lookup"><span data-stu-id="0d738-165">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="0d738-166">Dane wyjściowe tego kodu są następujące:</span><span class="sxs-lookup"><span data-stu-id="0d738-166">The output of this code is as follows:</span></span>

```console
The records are equal.
```

<span data-ttu-id="0d738-167">Jeśli piszesz ten sam kod z klasami, obiekty obu klas byłyby nierówne, ponieważ dwie wartości przedstawiają dwa obiekty na stercie i porównywane są tylko te adresy (chyba że typ klasy zastępuje `System.Object.Equals` metodę).</span><span class="sxs-lookup"><span data-stu-id="0d738-167">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="0d738-168">Jeśli potrzebujesz równości odwołań dla rekordów, Dodaj atrybut `[<ReferenceEquality>]` powyżej rekordu.</span><span class="sxs-lookup"><span data-stu-id="0d738-168">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d738-169">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d738-169">See also</span></span>

- [<span data-ttu-id="0d738-170">Typy F#</span><span class="sxs-lookup"><span data-stu-id="0d738-170">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="0d738-171">Klasy</span><span class="sxs-lookup"><span data-stu-id="0d738-171">Classes</span></span>](classes.md)
- [<span data-ttu-id="0d738-172">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="0d738-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0d738-173">Odwołanie — równość</span><span class="sxs-lookup"><span data-stu-id="0d738-173">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="0d738-174">Dopasowanie wzorca</span><span class="sxs-lookup"><span data-stu-id="0d738-174">Pattern Matching</span></span>](pattern-matching.md)
