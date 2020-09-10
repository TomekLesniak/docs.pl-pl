---
title: 'Atrybuty zastrzeżone języka C#: statycznej analizy dopuszczające wartość null'
ms.date: 04/14/2020
description: Te atrybuty są interpretowane przez kompilator w celu zapewnienia lepszej statycznej analizy dla typów odwołań dopuszczających wartości null i niedopuszczających wartości null.
ms.openlocfilehash: d2405162ece3df209111de65fdef54f70cc86d45
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656314"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a><span data-ttu-id="9fd52-103">Atrybuty zastrzeżone przyczyniają się do analizy statycznej stanu kompilatora o wartości null</span><span class="sxs-lookup"><span data-stu-id="9fd52-103">Reserved attributes contribute to the compiler's null state static analysis</span></span>

<span data-ttu-id="9fd52-104">W kontekście dopuszczającym wartość null kompilator wykonuje statyczną analizę kodu, aby określić stan null dla wszystkich zmiennych typu odwołania:</span><span class="sxs-lookup"><span data-stu-id="9fd52-104">In a nullable context, the compiler performs static analysis of code to determine the null state of all reference type variables:</span></span>

- <span data-ttu-id="9fd52-105">*nie null*: analiza statyczna ustaliła, że zmienna jest przypisana do wartości innej niż null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-105">*not null*: Static analysis determined that the variable is assigned to a non-null value.</span></span>
- <span data-ttu-id="9fd52-106">może *mieć wartość null*: analiza statyczna nie może określić, że zmienna ma przypisaną wartość różną od null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-106">*maybe null*: Static analysis cannot determine that a variable is assigned a non-null value.</span></span>

<span data-ttu-id="9fd52-107">Można zastosować wiele atrybutów, które dostarczają informacje dla kompilatora o semantyki interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="9fd52-107">You can apply a number of attributes that provide information to the compiler about the semantics of your APIs.</span></span> <span data-ttu-id="9fd52-108">Te informacje ułatwiają kompilatorowi wykonywanie analizy statycznej i określanie, kiedy zmienna nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-108">That information helps the compiler perform static analysis and determine when a variable is not null.</span></span> <span data-ttu-id="9fd52-109">W tym artykule przedstawiono krótki opis każdego z tych atrybutów oraz sposób ich używania.</span><span class="sxs-lookup"><span data-stu-id="9fd52-109">This article provides a brief description of each of those attributes and how to use them.</span></span> <span data-ttu-id="9fd52-110">We wszystkich przykładach przyjęto język C# 8,0 lub nowszy, a kod jest w kontekście dopuszczającym wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-110">All the examples assume C# 8.0 or newer, and the code is in a nullable context.</span></span>

<span data-ttu-id="9fd52-111">Zacznijmy od znanego przykładu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-111">Let's start with a familiar example.</span></span> <span data-ttu-id="9fd52-112">Wyobraź sobie, że biblioteka zawiera następujący interfejs API do pobrania ciągu zasobu:</span><span class="sxs-lookup"><span data-stu-id="9fd52-112">Imagine your library has the following API to retrieve a resource string:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="9fd52-113">Poprzedni przykład jest zgodny ze znajomym `Try*` wzorcem w programie .NET.</span><span class="sxs-lookup"><span data-stu-id="9fd52-113">The preceding example follows the familiar `Try*` pattern in .NET.</span></span> <span data-ttu-id="9fd52-114">Istnieją dwa argumenty odwołania dla tego interfejsu API: `key` i `message` parametru.</span><span class="sxs-lookup"><span data-stu-id="9fd52-114">There are two reference arguments for this API: the `key` and the `message` parameter.</span></span> <span data-ttu-id="9fd52-115">Ten interfejs API ma następujące reguły dotyczące wartości null tych argumentów:</span><span class="sxs-lookup"><span data-stu-id="9fd52-115">This API has the following rules relating to the nullness of these arguments:</span></span>

- <span data-ttu-id="9fd52-116">Obiekty wywołujące nie powinny być przekazywane `null` jako argument dla elementu `key` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-116">Callers shouldn't pass `null` as the argument for `key`.</span></span>
- <span data-ttu-id="9fd52-117">Obiekty wywołujące mogą przekazywać zmienną, której wartość jest `null` argumentem dla `message` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-117">Callers can pass a variable whose value is `null` as the argument for `message`.</span></span>
- <span data-ttu-id="9fd52-118">Jeśli `TryGetMessage` Metoda zwraca `true` , wartość `message` nie jest równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-118">If the `TryGetMessage` method returns `true`, the value of `message` isn't null.</span></span> <span data-ttu-id="9fd52-119">Jeśli wartość zwracana jest `false,` wartością parametru `message` (i jego stan zerowy) ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-119">If the return value is `false,` the value of `message` (and its null state) is null.</span></span>

<span data-ttu-id="9fd52-120">Reguła dla `key` może być wyrażona przez typ zmiennej: `key` powinien być typem referencyjnym, który nie dopuszcza wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-120">The rule for `key` can be expressed by the variable type: `key` should be a non-nullable reference type.</span></span> <span data-ttu-id="9fd52-121">`message`Parametr jest bardziej skomplikowany.</span><span class="sxs-lookup"><span data-stu-id="9fd52-121">The `message` parameter is more complex.</span></span> <span data-ttu-id="9fd52-122">Umożliwia `null` jako argument, ale gwarantuje, że w przypadku powodzenia ten `out` argument nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-122">It allows `null` as the argument, but guarantees that, on success, that `out` argument isn't null.</span></span> <span data-ttu-id="9fd52-123">W tych scenariuszach potrzebujesz bogatszego słownictwa do opisywania oczekiwań.</span><span class="sxs-lookup"><span data-stu-id="9fd52-123">For these scenarios, you need a richer vocabulary to describe the expectations.</span></span>

<span data-ttu-id="9fd52-124">Dodano kilka atrybutów w celu wyrażenia dodatkowych informacji o stanie null zmiennych.</span><span class="sxs-lookup"><span data-stu-id="9fd52-124">Several attributes have been added to express additional information about the null state of variables.</span></span> <span data-ttu-id="9fd52-125">Wszystkie kod, który zapisano przed C# 8 wprowadziły typy odwołań dopuszczających wartości null, miał *wartość null Oblivious*.</span><span class="sxs-lookup"><span data-stu-id="9fd52-125">All code you wrote before C# 8 introduced nullable reference types was *null oblivious*.</span></span> <span data-ttu-id="9fd52-126">Oznacza to, że jakakolwiek zmienna typu referencyjnego może mieć wartość null, ale sprawdzanie wartości null nie jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="9fd52-126">That means any reference type variable may be null, but null checks aren't required.</span></span> <span data-ttu-id="9fd52-127">Gdy kod *dopuszcza wartość null*, te reguły zostaną zmienione.</span><span class="sxs-lookup"><span data-stu-id="9fd52-127">Once your code is *nullable aware*, those rules change.</span></span> <span data-ttu-id="9fd52-128">Typy odwołań nigdy nie powinny być `null` wartościami, a typy referencyjne dopuszczające wartość null muszą zostać sprawdzone przed `null` usunięciem odwołania.</span><span class="sxs-lookup"><span data-stu-id="9fd52-128">Reference types should never be the `null` value, and nullable reference types must be checked against `null` before being dereferenced.</span></span>

<span data-ttu-id="9fd52-129">Reguły interfejsów API mogą być bardziej skomplikowane, jak pokazano w `TryGetValue` scenariuszu interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="9fd52-129">The rules for your APIs are likely more complicated, as you saw with the `TryGetValue` API scenario.</span></span> <span data-ttu-id="9fd52-130">Wiele interfejsów API ma bardziej złożone reguły dla sytuacji, gdy zmienne mogą być lub niemożliwe `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-130">Many of your APIs have more complex rules for when variables can or can't be `null`.</span></span> <span data-ttu-id="9fd52-131">W takich przypadkach użyjesz jednego z następujących atrybutów, aby przedstawić te reguły:</span><span class="sxs-lookup"><span data-stu-id="9fd52-131">In these cases, you'll use one of the following attributes to express those rules:</span></span>

- <span data-ttu-id="9fd52-132">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Argument wejściowy niedopuszczający wartości null może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-132">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable input argument may be null.</span></span>
- <span data-ttu-id="9fd52-133">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Argument wejściowy dopuszczający wartość null nigdy nie powinien mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-133">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable input argument should never be null.</span></span>
- <span data-ttu-id="9fd52-134">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): wartość zwracana niedopuszczający wartości null może być równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-134">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="9fd52-135">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): wartość zwracana do wartości null nigdy nie będzie równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-135">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>
- <span data-ttu-id="9fd52-136">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Argument wejściowy, który nie dopuszcza wartości null, może mieć wartość null, gdy metoda zwraca określoną `bool` wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-136">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable input argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="9fd52-137">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Argument wejściowy do wartości null nie będzie miał wartości null, gdy metoda zwróci określoną `bool` wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-137">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable input argument will not be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="9fd52-138">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): wartość zwracana nie ma wartości null, jeśli argument dla określonego parametru nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-138">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the argument for the specified parameter isn't null.</span></span>
- <span data-ttu-id="9fd52-139">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): Metoda nigdy nie zwraca.</span><span class="sxs-lookup"><span data-stu-id="9fd52-139">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): A method never returns.</span></span> <span data-ttu-id="9fd52-140">Innymi słowy, zawsze zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9fd52-140">In other words, it always throws an exception.</span></span>
- <span data-ttu-id="9fd52-141">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): Ta metoda nigdy nie zwraca, czy skojarzony `bool` parametr ma określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-141">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): This method never returns if the associated `bool` parameter has the specified value.</span></span>

<span data-ttu-id="9fd52-142">Powyższe opisy stanowią krótkie informacje o tym, co robi każdy atrybut.</span><span class="sxs-lookup"><span data-stu-id="9fd52-142">The preceding descriptions are a quick reference to what each attribute does.</span></span> <span data-ttu-id="9fd52-143">W poniższych sekcjach opisano zachowanie i ich znaczenie.</span><span class="sxs-lookup"><span data-stu-id="9fd52-143">Each following section describes the behavior and meaning more thoroughly.</span></span>

<span data-ttu-id="9fd52-144">Dodanie tych atrybutów zapewnia kompilatorowi więcej informacji na temat reguł dla interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="9fd52-144">Adding these attributes gives the compiler more information about the rules for your API.</span></span> <span data-ttu-id="9fd52-145">Gdy Wywoływanie kodu jest kompilowane w kontekście włączonego wartości null, kompilator ostrzega wywoływania, gdy narusza te reguły.</span><span class="sxs-lookup"><span data-stu-id="9fd52-145">When calling code is compiled in a nullable enabled context, the compiler will warn callers when they violate those rules.</span></span> <span data-ttu-id="9fd52-146">Te atrybuty nie umożliwiają wykonywania dodatkowych operacji sprawdzania w implementacji.</span><span class="sxs-lookup"><span data-stu-id="9fd52-146">These attributes don't enable additional checks on your implementation.</span></span>

## <a name="specify-preconditions-allownull-and-disallownull"></a><span data-ttu-id="9fd52-147">Określ warunki wstępne: `AllowNull` i `DisallowNull`</span><span class="sxs-lookup"><span data-stu-id="9fd52-147">Specify preconditions: `AllowNull` and `DisallowNull`</span></span>

<span data-ttu-id="9fd52-148">Rozważ użycie właściwości do odczytu/zapisu, która nigdy nie zwraca, `null` ponieważ ma ona rozsądną wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="9fd52-148">Consider a read/write property that never returns `null` because it has a reasonable default value.</span></span> <span data-ttu-id="9fd52-149">Obiekty wywołujące przejdą `null` do zestawu metod dostępu podczas ustawiania tej wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="9fd52-149">Callers pass `null` to the set accessor when setting it to that default value.</span></span> <span data-ttu-id="9fd52-150">Rozważmy na przykład system obsługi komunikatów, który prosi o podanie nazwy ekranu w pokoju rozmowy.</span><span class="sxs-lookup"><span data-stu-id="9fd52-150">For example, consider a messaging system that asks for a screen name in a chat room.</span></span> <span data-ttu-id="9fd52-151">Jeśli żaden nie jest podany, system generuje nazwę losową:</span><span class="sxs-lookup"><span data-stu-id="9fd52-151">If none is provided, the system generates a random name:</span></span>

```csharp
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName;
```

<span data-ttu-id="9fd52-152">Gdy kompilujesz poprzedni kod w kontekście dopuszczającym wartość null, wszystko jest bardzo precyzyjne.</span><span class="sxs-lookup"><span data-stu-id="9fd52-152">When you compile the preceding code in a nullable oblivious context, everything is fine.</span></span> <span data-ttu-id="9fd52-153">Po włączeniu typów referencyjnych dopuszczających wartość null, `ScreenName` Właściwość ta będzie odwołaniem niedopuszczanym do wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-153">Once you enable nullable reference types, the `ScreenName` property becomes a non-nullable reference.</span></span> <span data-ttu-id="9fd52-154">Jest to poprawne dla `get` metody dostępu: nigdy nie zwraca `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-154">That's correct for the `get` accessor: it never returns `null`.</span></span> <span data-ttu-id="9fd52-155">Obiekty wywołujące nie muszą sprawdzać zwracanej właściwości dla elementu `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-155">Callers don't need to check the returned property for `null`.</span></span> <span data-ttu-id="9fd52-156">Ale teraz ustawienie właściwości w celu `null` wygenerowania ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="9fd52-156">But now setting the property to `null` generates a warning.</span></span> <span data-ttu-id="9fd52-157">Aby kontynuować obsługę tego typu kodu, Dodaj <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> atrybut do właściwości, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="9fd52-157">In order to continue to support this type of code, you add the <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> attribute to the property, as shown in the following code:</span></span>

```csharp
[AllowNull]
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName = GenerateRandomScreenName();
```

<span data-ttu-id="9fd52-158">Może być konieczne dodanie dyrektywy do programu `using` <xref:System.Diagnostics.CodeAnalysis> w celu użycia tego i innych atrybutów omówionych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="9fd52-158">You may need to add a `using` directive for <xref:System.Diagnostics.CodeAnalysis> to use this and other attributes discussed in this article.</span></span> <span data-ttu-id="9fd52-159">Ten atrybut jest stosowany do właściwości, a nie do `set` metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-159">The attribute is applied to the property, not the `set` accessor.</span></span> <span data-ttu-id="9fd52-160">`AllowNull`Atrybut określa *warunki wstępne*i ma zastosowanie tylko do danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="9fd52-160">The `AllowNull` attribute specifies *pre-conditions*, and only applies to inputs.</span></span> <span data-ttu-id="9fd52-161">`get`Metoda dostępu ma wartość zwracaną, ale nie ma argumentów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="9fd52-161">The `get` accessor has a return value, but no input arguments.</span></span> <span data-ttu-id="9fd52-162">W związku z tym `AllowNull` atrybut ma zastosowanie tylko do `set` metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-162">Therefore, the `AllowNull` attribute only applies to the `set` accessor.</span></span>

<span data-ttu-id="9fd52-163">W poprzednim przykładzie pokazano, co należy szukać podczas dodawania `AllowNull` atrybutu do argumentu:</span><span class="sxs-lookup"><span data-stu-id="9fd52-163">The preceding example demonstrates what to look for when adding the `AllowNull` attribute on an argument:</span></span>

1. <span data-ttu-id="9fd52-164">Ogólną umową dla tej zmiennej jest to, że nie powinna ona być `null` , więc potrzebujesz typu referencyjnego, który nie dopuszcza wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-164">The general contract for that variable is that it shouldn't be `null`, so you want a non-nullable reference type.</span></span>
1. <span data-ttu-id="9fd52-165">Istnieją scenariusze dla zmiennej wejściowej `null` , chociaż nie są one najczęstszym użyciem.</span><span class="sxs-lookup"><span data-stu-id="9fd52-165">There are scenarios for the input variable to be `null`, though they aren't the most common usage.</span></span>

<span data-ttu-id="9fd52-166">Najczęściej ten atrybut jest potrzebny dla właściwości,, `in` `out` i `ref` argumentów.</span><span class="sxs-lookup"><span data-stu-id="9fd52-166">Most often you'll need this attribute for properties, or `in`, `out`, and `ref` arguments.</span></span> <span data-ttu-id="9fd52-167">Ten `AllowNull` atrybut jest najlepszym wyborem, gdy zmienna jest zwykle inna niż null, ale musisz zezwolić `null` jako warunek wstępny.</span><span class="sxs-lookup"><span data-stu-id="9fd52-167">The `AllowNull` attribute is the best choice when a variable is typically non-null, but you need to allow `null` as a precondition.</span></span>

<span data-ttu-id="9fd52-168">Przeciwieństwo do użycia `DisallowNull` : ten atrybut służy do określenia, że zmienna wejściowa typu referencyjnego nullable nie powinna być `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-168">Contrast that with scenarios for using `DisallowNull`: You use this attribute to specify that an input variable of a nullable reference type shouldn't be `null`.</span></span> <span data-ttu-id="9fd52-169">Rozważmy Właściwość `null` , gdzie jest wartością domyślną, ale klienci mogą ustawić ją tylko na wartość różną od null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-169">Consider a property where `null` is the default value, but clients can only set it to a non-null value.</span></span> <span data-ttu-id="9fd52-170">Spójrzmy na poniższy kod:</span><span class="sxs-lookup"><span data-stu-id="9fd52-170">Consider the following code:</span></span>

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

<span data-ttu-id="9fd52-171">Poprzedni kod jest najlepszym sposobem, aby wyrazić projekt `ReviewComment` , który może być `null` , ale nie może być ustawiony na `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-171">The preceding code is the best way to express your design that the `ReviewComment` could be `null`, but can't be set to `null`.</span></span> <span data-ttu-id="9fd52-172">Gdy ten kod dopuszcza wartość null, można jawnie wyrazić takie koncepcje dla wywołujących przy użyciu <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="9fd52-172">Once this code is nullable aware, you can express this concept more clearly to callers using the <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>:</span></span>

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

<span data-ttu-id="9fd52-173">W kontekście dopuszczającym wartość null `ReviewComment` `get` metoda dostępu może zwrócić wartość domyślną `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-173">In a nullable context, the `ReviewComment` `get` accessor could return the default value of `null`.</span></span> <span data-ttu-id="9fd52-174">Kompilator ostrzega o tym, że musi zostać sprawdzony przed dostępem.</span><span class="sxs-lookup"><span data-stu-id="9fd52-174">The compiler warns that it must be checked before access.</span></span> <span data-ttu-id="9fd52-175">Ponadto ostrzega wywołujących, że mimo że może się to zdarzyć `null` , obiekty wywołujące nie powinny jawnie ustawiać `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-175">Furthermore, it warns callers that, even though it could be `null`, callers shouldn't explicitly set it to `null`.</span></span> <span data-ttu-id="9fd52-176">`DisallowNull`Atrybut określa również *warunek wstępny*, nie ma wpływu na `get` metodę dostępu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-176">The `DisallowNull` attribute also specifies a *pre-condition*, it does not affect the `get` accessor.</span></span> <span data-ttu-id="9fd52-177">Ten atrybut jest używany `DisallowNull` podczas przestrzegania następujących cech:</span><span class="sxs-lookup"><span data-stu-id="9fd52-177">You use the `DisallowNull` attribute when you observe these characteristics about:</span></span>

1. <span data-ttu-id="9fd52-178">Zmienna może być `null` w scenariuszach podstawowych, często podczas pierwszego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="9fd52-178">The variable could be `null` in core scenarios, often when first instantiated.</span></span>
1. <span data-ttu-id="9fd52-179">Zmienna nie powinna być jawnie ustawiona na wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-179">The variable shouldn't be explicitly set to `null`.</span></span>

<span data-ttu-id="9fd52-180">Te sytuacje często występują w kodzie, który pierwotnie miał *wartość null Oblivious*.</span><span class="sxs-lookup"><span data-stu-id="9fd52-180">These situations are common in code that was originally *null oblivious*.</span></span> <span data-ttu-id="9fd52-181">Może być to, że właściwości obiektu są ustawiane w dwóch odrębnych operacjach inicjalizacji.</span><span class="sxs-lookup"><span data-stu-id="9fd52-181">It may be that object properties are set in two distinct initialization operations.</span></span> <span data-ttu-id="9fd52-182">Niektóre właściwości mogą być ustawione tylko po zakończeniu pewnej asynchronicznej pracy.</span><span class="sxs-lookup"><span data-stu-id="9fd52-182">It may be that some properties are set only after some asynchronous work has completed.</span></span>

<span data-ttu-id="9fd52-183">`AllowNull`Atrybuty i `DisallowNull` umożliwiają określenie, że warunki wstępne dla zmiennych mogą nie pasować do adnotacji dopuszczających wartości null w tych zmiennych.</span><span class="sxs-lookup"><span data-stu-id="9fd52-183">The `AllowNull` and `DisallowNull` attributes enable you to specify that preconditions on variables may not match the nullable annotations on those variables.</span></span> <span data-ttu-id="9fd52-184">Zapewniają one więcej szczegółowych informacji o cechach interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="9fd52-184">These provide more detail about the characteristics of your API.</span></span> <span data-ttu-id="9fd52-185">Te dodatkowe informacje ułatwiają wywoływanie interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="9fd52-185">This additional information helps callers use your API correctly.</span></span> <span data-ttu-id="9fd52-186">Należy pamiętać o określeniu warunków wstępnych przy użyciu następujących atrybutów:</span><span class="sxs-lookup"><span data-stu-id="9fd52-186">Remember you specify preconditions using the following attributes:</span></span>

- <span data-ttu-id="9fd52-187">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Argument wejściowy niedopuszczający wartości null może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-187">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable input argument may be null.</span></span>
- <span data-ttu-id="9fd52-188">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Argument wejściowy dopuszczający wartość null nigdy nie powinien mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-188">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable input argument should never be null.</span></span>

## <a name="specify-post-conditions-maybenull-and-notnull"></a><span data-ttu-id="9fd52-189">Określ warunki końcowe: `MaybeNull` i `NotNull`</span><span class="sxs-lookup"><span data-stu-id="9fd52-189">Specify post-conditions: `MaybeNull` and `NotNull`</span></span>

<span data-ttu-id="9fd52-190">Załóżmy, że masz metodę o następującej sygnaturze:</span><span class="sxs-lookup"><span data-stu-id="9fd52-190">Suppose you have a method with the following signature:</span></span>

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

<span data-ttu-id="9fd52-191">Prawdopodobnie Zapisano metodę podobną do tej, aby zwracała się `null` , gdy nie znaleziono nazwy.</span><span class="sxs-lookup"><span data-stu-id="9fd52-191">You've likely written a method like this to return `null` when the name sought wasn't found.</span></span> <span data-ttu-id="9fd52-192">`null`Jasno wskazuje, że rekord nie został znaleziony.</span><span class="sxs-lookup"><span data-stu-id="9fd52-192">The `null` clearly indicates that the record wasn't found.</span></span> <span data-ttu-id="9fd52-193">W tym przykładzie można zmienić typ zwracany z `Customer` na `Customer?` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-193">In this example, you'd likely change the return type from `Customer` to `Customer?`.</span></span> <span data-ttu-id="9fd52-194">Deklarowanie wartości zwracanej jako typ referencyjny dopuszczający wartość null Określa zamiar tego interfejsu API jasno.</span><span class="sxs-lookup"><span data-stu-id="9fd52-194">Declaring the return value as a nullable reference type specifies the intent of this API clearly.</span></span>

<span data-ttu-id="9fd52-195">Z przyczyn objętych [definicjami ogólnymi i wartością null](../../nullable-migration-strategies.md#generic-definitions-and-nullability) ta technika nie działa z metodami ogólnymi.</span><span class="sxs-lookup"><span data-stu-id="9fd52-195">For reasons covered under [Generic definitions and nullability](../../nullable-migration-strategies.md#generic-definitions-and-nullability) that technique does not work with generic methods.</span></span> <span data-ttu-id="9fd52-196">Może istnieć Metoda ogólna, która następuje po podobnym wzorcu:</span><span class="sxs-lookup"><span data-stu-id="9fd52-196">You may have a generic method that follows a similar pattern:</span></span>

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

<span data-ttu-id="9fd52-197">Nie można określić, że wartość zwracana to `T?` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-197">You can't specify that the return value is `T?`.</span></span> <span data-ttu-id="9fd52-198">Metoda zwraca `null` , gdy nie znaleziono szukanego elementu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-198">The method returns `null` when the sought item isn't found.</span></span> <span data-ttu-id="9fd52-199">Ponieważ nie można zadeklarować `T?` zwracanego typu, należy dodać `MaybeNull` adnotację do zwracanej metody:</span><span class="sxs-lookup"><span data-stu-id="9fd52-199">Since you can't declare a `T?` return type, you add the `MaybeNull` annotation to the method return:</span></span>

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

<span data-ttu-id="9fd52-200">Poprzedni kod informuje wywołujących, że kontrakt implikuje typ niedopuszczający wartości null, ale zwracana wartość *może* być równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-200">The preceding code informs callers that the contract implies a non-nullable type, but the return value *may* actually be null.</span></span>  <span data-ttu-id="9fd52-201">Użyj `MaybeNull` atrybutu, gdy interfejs API powinien być typu niedopuszczający wartości null, zazwyczaj parametru typu ogólnego, ale mogą występować wystąpienia, w których `null` zostałyby zwrócone.</span><span class="sxs-lookup"><span data-stu-id="9fd52-201">Use the `MaybeNull` attribute when your API should be a non-nullable type, typically a generic type parameter, but there may be instances where `null` would be returned.</span></span>

<span data-ttu-id="9fd52-202">Można również określić, że wartość zwracana lub `out` argument or nie mają wartości null, mimo że `ref` Typ jest typem referencyjnym dopuszczającym wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-202">You can also specify that a return value or an `out` or `ref` argument isn't null even though the type is a nullable reference type.</span></span> <span data-ttu-id="9fd52-203">Rozważmy metodę, która zapewnia, że tablica jest wystarczająco duża, aby pomieścić liczbę elementów.</span><span class="sxs-lookup"><span data-stu-id="9fd52-203">Consider a method that ensures an array is large enough to hold a number of elements.</span></span> <span data-ttu-id="9fd52-204">Jeśli argument wejściowy nie ma pojemności, procedura przydzieli nową tablicę i skopiuje do niej wszystkie istniejące elementy.</span><span class="sxs-lookup"><span data-stu-id="9fd52-204">If the input argument doesn't have capacity, the routine would allocate a new array and copy all the existing elements into it.</span></span> <span data-ttu-id="9fd52-205">Jeśli argumentem wejściowym jest `null` , procedura przydzieli nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="9fd52-205">If the input argument is `null`, the routine would allocate new storage.</span></span> <span data-ttu-id="9fd52-206">W przypadku wystarczającej pojemności procedura nie wykonuje żadnych czynności:</span><span class="sxs-lookup"><span data-stu-id="9fd52-206">If there's sufficient capacity, the routine does nothing:</span></span>

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

<span data-ttu-id="9fd52-207">Tę procedurę można wywołać w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9fd52-207">You could call this routine as follows:</span></span>

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

<span data-ttu-id="9fd52-208">Po włączeniu typów odwołań o wartości null, należy upewnić się, że poprzedni kod kompiluje bez ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="9fd52-208">After enabling null reference types, you want to ensure that the preceding code compiles without warnings.</span></span> <span data-ttu-id="9fd52-209">Gdy metoda zwraca, `storage` argument ma gwarantowaną wartość nie równą null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-209">When the method returns, the `storage` argument is guaranteed to be not null.</span></span> <span data-ttu-id="9fd52-210">Jednak jest to możliwe do wywołania `EnsureCapacity` z odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-210">However, it's acceptable to call `EnsureCapacity` with a null reference.</span></span> <span data-ttu-id="9fd52-211">Można wprowadzić `storage` typ referencyjny dopuszczający wartość null i dodać `NotNull` warunek post do deklaracji parametru:</span><span class="sxs-lookup"><span data-stu-id="9fd52-211">You can make `storage` a nullable reference type, and add the `NotNull` post-condition to the parameter declaration:</span></span>

```csharp
public void EnsureCapacity<T>([NotNull] ref T[]? storage, int size)
```

<span data-ttu-id="9fd52-212">Poprzedni kod wyraża istniejący kontrakt jasno: obiekty wywołujące mogą przekazać zmienną o `null` wartości, ale wartość zwracana jest gwarantowana, aby nigdy nie była równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-212">The preceding code expresses the existing contract clearly: Callers can pass a variable with the `null` value, but the return value is guaranteed to never be null.</span></span> <span data-ttu-id="9fd52-213">Ten `NotNull` atrybut jest najbardziej przydatny `ref` dla `out` argumentów i `null` , gdzie mogą być przekazane jako argument, ale ten argument jest gwarantowany, że nie ma wartości null, gdy metoda zwraca.</span><span class="sxs-lookup"><span data-stu-id="9fd52-213">The `NotNull` attribute is most useful for `ref` and `out` arguments where `null` may be passed as an argument, but that argument is guaranteed to be not null when the method returns.</span></span>

<span data-ttu-id="9fd52-214">Należy określić warunki końcowe bezwarunkowe, korzystając z następujących atrybutów:</span><span class="sxs-lookup"><span data-stu-id="9fd52-214">You specify unconditional postconditions using the following attributes:</span></span>

- <span data-ttu-id="9fd52-215">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): wartość zwracana niedopuszczający wartości null może być równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-215">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="9fd52-216">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): wartość zwracana do wartości null nigdy nie będzie równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-216">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a><span data-ttu-id="9fd52-217">Określ warunkowe warunki końcowe: `NotNullWhen` , `MaybeNullWhen` i `NotNullIfNotNull`</span><span class="sxs-lookup"><span data-stu-id="9fd52-217">Specify conditional post-conditions: `NotNullWhen`, `MaybeNullWhen`, and `NotNullIfNotNull`</span></span>

<span data-ttu-id="9fd52-218">Najkorzystniej znasz `string` metodę <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9fd52-218">You're likely familiar with the `string` method <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>.</span></span> <span data-ttu-id="9fd52-219">Ta metoda zwraca `true` , gdy argument ma wartość null lub jest pustym ciągiem.</span><span class="sxs-lookup"><span data-stu-id="9fd52-219">This method returns `true` when the argument is null or an empty string.</span></span> <span data-ttu-id="9fd52-220">Jest to forma sprawdzania wartości null: obiekty wywołujące nie muszą mieć wartości null — Sprawdź argument, jeśli metoda zwraca wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-220">It's a form of null-check: Callers don't need to null-check the argument if the method returns `false`.</span></span> <span data-ttu-id="9fd52-221">Aby określić metodę, taką jak ta, która dopuszcza wartość null, należy ustawić argument na typ referencyjny dopuszczający wartość null i dodać `NotNullWhen` atrybut:</span><span class="sxs-lookup"><span data-stu-id="9fd52-221">To make a method like this nullable aware, you'd set the argument to a nullable reference type, and add the `NotNullWhen` attribute:</span></span>

```csharp
bool IsNullOrEmpty([NotNullWhen(false)] string? value);
```

<span data-ttu-id="9fd52-222">Informuje kompilator, że żaden kod, w którym nie jest wymagana wartość zwracana, `false` nie może mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-222">That informs the compiler that any code where the return value is `false` need not be null-checked.</span></span> <span data-ttu-id="9fd52-223">Dodanie atrybutu informuje analizę statyczną kompilatora, która `IsNullOrEmpty` wykonuje niezbędne sprawdzanie wartości null: gdy zwraca `false` , argument wejściowy nie jest `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-223">The addition of the attribute informs the compiler's static analysis that `IsNullOrEmpty` performs the necessary null check: when it returns `false`, the input argument is not `null`.</span></span>

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

<span data-ttu-id="9fd52-224"><xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>Metoda zostanie umieszczona w adnotacji, jak pokazano powyżej dla programu .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="9fd52-224">The <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> method will be annotated as shown above for .NET Core 3.0.</span></span> <span data-ttu-id="9fd52-225">W bazie kodu mogą znajdować się podobne metody, które sprawdzają stan obiektów dla wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-225">You may have similar methods in your codebase that check the state of objects for null values.</span></span> <span data-ttu-id="9fd52-226">Kompilator nie rozpoznaje niestandardowych metod sprawdzania wartości null i należy samodzielnie dodać adnotacje.</span><span class="sxs-lookup"><span data-stu-id="9fd52-226">The compiler won't recognize custom null check methods, and you'll need to add the annotations yourself.</span></span> <span data-ttu-id="9fd52-227">Po dodaniu atrybutu analiza statyczna kompilatora wie, kiedy sprawdzona zmienna ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-227">When you add the attribute, the compiler's static analysis knows when the tested variable has been null checked.</span></span>

<span data-ttu-id="9fd52-228">Innym zastosowaniem dla tych atrybutów jest `Try*` wzorzec.</span><span class="sxs-lookup"><span data-stu-id="9fd52-228">Another use for these attributes is the `Try*` pattern.</span></span> <span data-ttu-id="9fd52-229">Warunki końcowe dla `ref` i `out` zmienne są przekazywane przez wartość zwracaną.</span><span class="sxs-lookup"><span data-stu-id="9fd52-229">The postconditions for `ref` and `out` variables are communicated through the return value.</span></span> <span data-ttu-id="9fd52-230">Rozważmy tę metodę pokazaną wcześniej:</span><span class="sxs-lookup"><span data-stu-id="9fd52-230">Consider this method shown earlier:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="9fd52-231">Poprzednia metoda jest zgodna z typowym środowiskiem .NET idiom: wartość zwracana wskazuje `message` , czy została ustawiona na znalezioną wartość, czy nie zostanie znaleziony komunikat do wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="9fd52-231">The preceding method follows a typical .NET idiom: the return value indicates if `message` was set to the found value or, if no message is found, to the default value.</span></span> <span data-ttu-id="9fd52-232">Jeśli metoda zwraca `true` , wartość `message` nie jest równa null; w przeciwnym razie metoda jest ustawiana `message` na wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-232">If the method returns `true`, the value of `message` isn't null; otherwise, the method sets `message` to null.</span></span>

<span data-ttu-id="9fd52-233">Można komunikować się z idiom przy użyciu `NotNullWhen` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-233">You can communicate that idiom using the `NotNullWhen` attribute.</span></span> <span data-ttu-id="9fd52-234">W przypadku aktualizowania sygnatury dla typów referencyjnych dopuszczających wartość null wprowadź `message` `string?` i Dodaj atrybut:</span><span class="sxs-lookup"><span data-stu-id="9fd52-234">When you update the signature for nullable reference types, make `message` a `string?` and add an attribute:</span></span>

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

<span data-ttu-id="9fd52-235">W poprzednim przykładzie wartość `message` jest znana od null, gdy `TryGetMessage` zwraca `true` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-235">In the preceding example, the value of `message` is known to be not null when `TryGetMessage` returns `true`.</span></span> <span data-ttu-id="9fd52-236">Należy dodać adnotacje do podobnych metod w bazie kodu w taki sam sposób: argumenty mogą być `null` i nie mieć wartości null, gdy metoda zwraca `true` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-236">You should annotate similar methods in your codebase in the same way: the arguments could be `null`, and are known to be not null when the method returns `true`.</span></span>

<span data-ttu-id="9fd52-237">Istnieje również jeden atrybut końcowy.</span><span class="sxs-lookup"><span data-stu-id="9fd52-237">There's one final attribute you may also need.</span></span> <span data-ttu-id="9fd52-238">Czasami stan null wartości zwracanej zależy od stanu zerowego co najmniej jednego argumentu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="9fd52-238">Sometimes the null state of a return value depends on the null state of one or more input arguments.</span></span> <span data-ttu-id="9fd52-239">Metody te zwracają wartość różną od null, gdy nie ma określonych argumentów wejściowych `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-239">These methods will return a non-null value whenever certain input arguments aren't `null`.</span></span> <span data-ttu-id="9fd52-240">Aby poprawnie dodać adnotację do tych metod, należy użyć `NotNullIfNotNull` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9fd52-240">To correctly annotate these methods, you use the `NotNullIfNotNull` attribute.</span></span> <span data-ttu-id="9fd52-241">Weź pod uwagę następującą metodę:</span><span class="sxs-lookup"><span data-stu-id="9fd52-241">Consider the following method:</span></span>

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

<span data-ttu-id="9fd52-242">Jeśli `url` argument nie ma wartości null, dane wyjściowe nie są `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-242">If the `url` argument isn't null, the output isn't `null`.</span></span> <span data-ttu-id="9fd52-243">Po włączeniu odwołań do wartości null ten podpis działa prawidłowo, pod warunkiem, że interfejs API nigdy nie akceptuje danych wejściowych o wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-243">Once nullable references are enabled, that signature works correctly, provided your API never accepts a null input.</span></span> <span data-ttu-id="9fd52-244">Jeśli jednak dane wejściowe mogą mieć wartość null, wówczas wartość zwracana może być również wartością null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-244">However, if the input could be null, then return value could also be null.</span></span> <span data-ttu-id="9fd52-245">W związku z tym można zmienić sygnaturę na następujący kod:</span><span class="sxs-lookup"><span data-stu-id="9fd52-245">Therefore, you could change the signature to the following code:</span></span>

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

<span data-ttu-id="9fd52-246">To również działa, ale często zmusza wywołujących do wdrożenia dodatkowych `null` kontroli.</span><span class="sxs-lookup"><span data-stu-id="9fd52-246">That also works, but will often force callers to implement extra `null` checks.</span></span> <span data-ttu-id="9fd52-247">Kontrakt jest, że wartość zwracana będzie tylko wtedy, `null` gdy argument wejściowy `url` to `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-247">The contract is that the return value would be `null` only when the input argument `url` is `null`.</span></span> <span data-ttu-id="9fd52-248">Aby można było wyrazić ten kontrakt, należy dodać adnotację do tej metody, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="9fd52-248">To express that contract, you would annotate this method as shown in the following code:</span></span>

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

<span data-ttu-id="9fd52-249">Zwracana wartość i argument mają adnotację ze `?` wskazaniem, że może to być `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-249">The return value and the argument have both been annotated with the `?` indicating that either could be `null`.</span></span> <span data-ttu-id="9fd52-250">Ten atrybut dokładniej objaśnia, że wartość zwracana nie będzie zerowa, gdy `url` argument nie jest `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-250">The attribute further clarifies that the return value won't be null when the `url` argument isn't `null`.</span></span>

<span data-ttu-id="9fd52-251">Należy określić warunkowe warunki końcowe przy użyciu następujących atrybutów:</span><span class="sxs-lookup"><span data-stu-id="9fd52-251">You specify conditional postconditions using these attributes:</span></span>

- <span data-ttu-id="9fd52-252">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Argument wejściowy, który nie dopuszcza wartości null, może mieć wartość null, gdy metoda zwraca określoną `bool` wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-252">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable input argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="9fd52-253">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Argument wejściowy do wartości null nie będzie miał wartości null, gdy metoda zwróci określoną `bool` wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-253">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable input argument will not be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="9fd52-254">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): wartość zwracana nie ma wartości null, jeśli argument wejściowy dla określonego parametru nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-254">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the input argument for the specified parameter isn't null.</span></span>

## <a name="verify-unreachable-code"></a><span data-ttu-id="9fd52-255">Weryfikuj nieosiągalny kod</span><span class="sxs-lookup"><span data-stu-id="9fd52-255">Verify unreachable code</span></span>

<span data-ttu-id="9fd52-256">Niektóre metody, zazwyczaj pomocniki wyjątków lub inne metody narzędzi, zawsze opuszczają się, zwracając wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9fd52-256">Some methods, typically exception helpers or other utility methods, always exit by throwing an exception.</span></span> <span data-ttu-id="9fd52-257">Lub pomocnik może zgłosić wyjątek na podstawie wartości argumentu logicznego.</span><span class="sxs-lookup"><span data-stu-id="9fd52-257">Or, a helper may throw an exception based on the value of a Boolean argument.</span></span>

<span data-ttu-id="9fd52-258">W pierwszym przypadku można dodać `DoesNotReturn` atrybut do deklaracji metody.</span><span class="sxs-lookup"><span data-stu-id="9fd52-258">In the first case, you can add the `DoesNotReturn` attribute to the method declaration.</span></span> <span data-ttu-id="9fd52-259">Kompilator pozwala na trzy sposoby.</span><span class="sxs-lookup"><span data-stu-id="9fd52-259">The compiler helps you in three ways.</span></span> <span data-ttu-id="9fd52-260">Najpierw kompilator generuje ostrzeżenie, jeśli istnieje ścieżka, w której metoda może wyjść bez zgłaszania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9fd52-260">First, the compiler issues a warning if there is a path where the method can exit without throwing an exception.</span></span> <span data-ttu-id="9fd52-261">Po drugie, kompilator oznacza dowolny kod po wywołaniu tej metody jako *nieosiągalny*do czasu `catch` napotkania odpowiedniej klauzuli.</span><span class="sxs-lookup"><span data-stu-id="9fd52-261">Second, the compiler marks any code after a call to that method as *unreachable*, until an appropriate `catch` clause is encountered.</span></span> <span data-ttu-id="9fd52-262">Trzeci kod nieosiągalny nie wpłynie na żadne Stany null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-262">Third, the unreachable code won't affect any null states.</span></span> <span data-ttu-id="9fd52-263">Rozważmy tę metodę:</span><span class="sxs-lookup"><span data-stu-id="9fd52-263">Consider this method:</span></span>

```csharp
[DoesNotReturn]
private void FailFast()
{
    throw new InvalidOperationException();
}

public void SetState(object containedField)
{
    if (!isInitialized)
    {
        FailFast();
    }

    // unreachable code:
    _field = containedField;
}
```

<span data-ttu-id="9fd52-264">W drugim przypadku należy dodać `DoesNotReturnIf` atrybut do parametru Boolean metody.</span><span class="sxs-lookup"><span data-stu-id="9fd52-264">In the second case, you add the `DoesNotReturnIf` attribute to a Boolean parameter of the method.</span></span> <span data-ttu-id="9fd52-265">Poprzedni przykład można zmodyfikować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9fd52-265">You can modify the previous example as follows:</span></span>

```csharp
private void FailFast([DoesNotReturnIf(false)] bool isValid)
{
    if (!isValid)
    {
        throw new InvalidOperationException();
    }
}

public void SetState(object containedField)
{
    FailFast(isInitialized);

    // unreachable code when "isInitialized" is false:
    _field = containedField;
}
```

## <a name="summary"></a><span data-ttu-id="9fd52-266">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="9fd52-266">Summary</span></span>

[!INCLUDE [C# version alert](../../includes/csharp-version-alert.md)]

<span data-ttu-id="9fd52-267">Dodanie typów referencyjnych dopuszczających wartość null zapewnia wstępne słownictwo do opisywania oczekiwań interfejsów API dla zmiennych, które mogą być `null` .</span><span class="sxs-lookup"><span data-stu-id="9fd52-267">Adding nullable reference types provides an initial vocabulary to describe your APIs expectations for variables that could be `null`.</span></span> <span data-ttu-id="9fd52-268">Dodatkowe atrybuty zapewniają bogatszy słownictwo do opisania stanu wartości null zmiennych jako warunków wstępnych i warunki końcowe.</span><span class="sxs-lookup"><span data-stu-id="9fd52-268">The additional attributes provide a richer vocabulary to describe the null state of variables as preconditions and postconditions.</span></span> <span data-ttu-id="9fd52-269">Te atrybuty bardziej wyraźnie opisują oczekiwania i zapewniają lepszy komfort używania interfejsów API przez deweloperów.</span><span class="sxs-lookup"><span data-stu-id="9fd52-269">These attributes more clearly describe your expectations and provide a better experience for the developers using your APIs.</span></span>

<span data-ttu-id="9fd52-270">Podczas aktualizowania bibliotek dla kontekstu dopuszczającego wartość null należy dodać te atrybuty, aby ułatwić użytkownikom interfejsów API poprawne użycie.</span><span class="sxs-lookup"><span data-stu-id="9fd52-270">As you update libraries for a nullable context, add these attributes to guide users of your APIs to the correct usage.</span></span> <span data-ttu-id="9fd52-271">Te atrybuty pomagają w pełni opisać stan null argumentów wejściowych i zwracanych wartości:</span><span class="sxs-lookup"><span data-stu-id="9fd52-271">These attributes help you fully describe the null-state of input arguments and return values:</span></span>

- <span data-ttu-id="9fd52-272">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Argument wejściowy niedopuszczający wartości null może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-272">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable input argument may be null.</span></span>
- <span data-ttu-id="9fd52-273">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Argument wejściowy dopuszczający wartość null nigdy nie powinien mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-273">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable input argument should never be null.</span></span>
- <span data-ttu-id="9fd52-274">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): wartość zwracana niedopuszczający wartości null może być równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-274">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="9fd52-275">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): wartość zwracana do wartości null nigdy nie będzie równa null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-275">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>
- <span data-ttu-id="9fd52-276">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Argument wejściowy, który nie dopuszcza wartości null, może mieć wartość null, gdy metoda zwraca określoną `bool` wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-276">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable input argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="9fd52-277">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Argument wejściowy do wartości null nie będzie miał wartości null, gdy metoda zwróci określoną `bool` wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-277">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable input argument will not be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="9fd52-278">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): wartość zwracana nie ma wartości null, jeśli argument wejściowy dla określonego parametru nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="9fd52-278">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the input argument for the specified parameter isn't null.</span></span>
- <span data-ttu-id="9fd52-279">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): Metoda nigdy nie zwraca.</span><span class="sxs-lookup"><span data-stu-id="9fd52-279">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): A method never returns.</span></span> <span data-ttu-id="9fd52-280">Innymi słowy, zawsze zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9fd52-280">In other words, it always throws an exception.</span></span>
- <span data-ttu-id="9fd52-281">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): Ta metoda nigdy nie zwraca, czy skojarzony `bool` parametr ma określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd52-281">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): This method never returns if the associated `bool` parameter has the specified value.</span></span>
