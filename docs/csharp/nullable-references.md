---
title: Typy referencyjne dopuszczające wartość null
description: Ten artykuł zawiera omówienie typów referencyjnych dopuszczających wartość null, które dodano w języku C# 8,0. Dowiesz się, jak funkcja zapewnia bezpieczeństwo przed wyjątkami odwołania o wartości null dla nowych i istniejących projektów.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: b4906987ee23f458c1da9754ed7b402621169f63
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099347"
---
# <a name="nullable-reference-types"></a><span data-ttu-id="8746b-104">Typy referencyjne dopuszczające wartość null</span><span class="sxs-lookup"><span data-stu-id="8746b-104">Nullable reference types</span></span>

<span data-ttu-id="8746b-105">W języku C# 8,0 wprowadzono **wartości null typów referencyjnych** i **niedopuszczających wartości null** , które umożliwiają wykonywanie ważnych instrukcji dotyczących właściwości dla zmiennych typu odwołania:</span><span class="sxs-lookup"><span data-stu-id="8746b-105">C# 8.0 introduces **nullable reference types** and **non-nullable reference types** that enable you to make important statements about the properties for reference type variables:</span></span>

- <span data-ttu-id="8746b-106">**Odwołanie nie powinno mieć wartości null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-106">**A reference isn't supposed to be null**.</span></span> <span data-ttu-id="8746b-107">Gdy zmienne nie powinny mieć wartości null, kompilator wymusza reguły, które zapewnią bezpieczne odtworzenie odwołania do tych zmiennych bez uprzedniego sprawdzenia, czy nie ma on wartości null:</span><span class="sxs-lookup"><span data-stu-id="8746b-107">When variables aren't supposed to be null, the compiler enforces rules that ensure it's safe to dereference these variables without first checking that it isn't null:</span></span>
  - <span data-ttu-id="8746b-108">Zmienna musi być zainicjowana do wartości innej niż null.</span><span class="sxs-lookup"><span data-stu-id="8746b-108">The variable must be initialized to a non-null value.</span></span>
  - <span data-ttu-id="8746b-109">Do zmiennej nigdy nie można przypisać wartości `null` .</span><span class="sxs-lookup"><span data-stu-id="8746b-109">The variable can never be assigned the value `null`.</span></span>
- <span data-ttu-id="8746b-110">**Odwołanie może mieć wartość null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-110">**A reference may be null**.</span></span> <span data-ttu-id="8746b-111">Gdy zmienne mogą mieć wartość null, kompilator wymusza różne reguły, aby upewnić się, że prawidłowo sprawdzono odwołanie o wartości null:</span><span class="sxs-lookup"><span data-stu-id="8746b-111">When variables may be null, the compiler enforces different rules to ensure that you've correctly checked for a null reference:</span></span>
  - <span data-ttu-id="8746b-112">Zmienna może zostać wykorzystana tylko wtedy, gdy kompilator może zagwarantować, że wartość nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-112">The variable may only be dereferenced when the compiler can guarantee that the value isn't null.</span></span>
  - <span data-ttu-id="8746b-113">Te zmienne mogą być inicjowane z `null` wartością domyślną i mogą mieć przypisaną wartość `null` w innym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8746b-113">These variables may be initialized with the default `null` value and may be assigned the value `null` in other code.</span></span>

<span data-ttu-id="8746b-114">Ta nowa funkcja zapewnia znaczne korzyści w porównaniu z obsługą zmiennych referencyjnych we wcześniejszych wersjach języka C#, w których nie można ustalić zamiaru projektowania na podstawie deklaracji zmiennej.</span><span class="sxs-lookup"><span data-stu-id="8746b-114">This new feature provides significant benefits over the handling of reference variables in earlier versions of C# where the design intent can't be determined from the variable declaration.</span></span> <span data-ttu-id="8746b-115">Kompilator nie zapewniał bezpieczeństwa przed wyjątkami odwołania o wartości null dla typów referencyjnych:</span><span class="sxs-lookup"><span data-stu-id="8746b-115">The compiler didn't provide safety against null reference exceptions for reference types:</span></span>

- <span data-ttu-id="8746b-116">**Odwołanie może mieć wartość null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-116">**A reference can be null**.</span></span> <span data-ttu-id="8746b-117">Kompilator nie wydaje ostrzeżeń, gdy zmienna typu odwołania jest zainicjowana do `null` lub później przypisany `null` .</span><span class="sxs-lookup"><span data-stu-id="8746b-117">The compiler doesn't issue warnings when a reference-type variable is initialized to `null`, or later assigned `null`.</span></span> <span data-ttu-id="8746b-118">Kompilator wystawia ostrzeżenia, gdy te zmienne są wywołujące bez sprawdzania wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-118">The compiler issues warnings when these variables are dereferenced without null checks.</span></span>
- <span data-ttu-id="8746b-119">**Przyjęto, że odwołanie nie ma wartości null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-119">**A reference is assumed to be not null**.</span></span> <span data-ttu-id="8746b-120">Kompilator nie wystawia żadnych ostrzeżeń, gdy odwołania do typów odwołań.</span><span class="sxs-lookup"><span data-stu-id="8746b-120">The compiler doesn't issue any warnings when reference types are dereferenced.</span></span> <span data-ttu-id="8746b-121">Kompilator wystawia ostrzeżenia, jeśli zmienna jest ustawiona na wyrażenie, które może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-121">The compiler issues warnings if a variable is set to an expression that may be null.</span></span>

<span data-ttu-id="8746b-122">Te ostrzeżenia są emitowane w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="8746b-122">These warnings are emitted at compile time.</span></span> <span data-ttu-id="8746b-123">Kompilator nie dodaje żadnych kontroli wartości null ani innych konstrukcji środowiska uruchomieniowego w kontekście dopuszczającym wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-123">The compiler doesn't add any null checks or other runtime constructs in a nullable context.</span></span> <span data-ttu-id="8746b-124">W czasie wykonywania, odwołanie do wartości null i odwołanie niedopuszczające wartości null są równoważne.</span><span class="sxs-lookup"><span data-stu-id="8746b-124">At runtime, a nullable reference and a non-nullable reference are equivalent.</span></span>

<span data-ttu-id="8746b-125">Przy dodawaniu typów odwołań do wartości null można zadeklarować cel dokładniej.</span><span class="sxs-lookup"><span data-stu-id="8746b-125">With the addition of nullable reference types, you can declare your intent more clearly.</span></span> <span data-ttu-id="8746b-126">`null`Wartość jest poprawnym sposobem reprezentowania, że zmienna nie odwołuje się do wartości.</span><span class="sxs-lookup"><span data-stu-id="8746b-126">The `null` value is the correct way to represent that a variable doesn't refer to a value.</span></span> <span data-ttu-id="8746b-127">Nie używaj tej funkcji, aby usunąć wszystkie `null` wartości z Twojego kodu.</span><span class="sxs-lookup"><span data-stu-id="8746b-127">Don't use this feature to remove all `null` values from your code.</span></span> <span data-ttu-id="8746b-128">Zamiast tego należy zadeklarować intencję do kompilatora i innych deweloperów, które odczytują swój kod.</span><span class="sxs-lookup"><span data-stu-id="8746b-128">Rather, you should declare your intent to the compiler and other developers that read your code.</span></span> <span data-ttu-id="8746b-129">Deklarując swój intencję, kompilator informuje, gdy piszesz kod, który jest niespójny z tym zamiarem.</span><span class="sxs-lookup"><span data-stu-id="8746b-129">By declaring your intent, the compiler informs you when you write code that is inconsistent with that intent.</span></span>

<span data-ttu-id="8746b-130">**Typ referencyjny dopuszczający wartość null** jest zanotowany przy użyciu tej samej składni co [typy wartości null](language-reference/builtin-types/nullable-value-types.md): a `?` jest dołączany do typu zmiennej.</span><span class="sxs-lookup"><span data-stu-id="8746b-130">A **nullable reference type** is noted using the same syntax as [nullable value types](language-reference/builtin-types/nullable-value-types.md): a `?` is appended to the type of the variable.</span></span> <span data-ttu-id="8746b-131">Na przykład następująca deklaracja zmiennej reprezentuje zmienną ciągu null, `name` :</span><span class="sxs-lookup"><span data-stu-id="8746b-131">For example, the following variable declaration represents a nullable string variable, `name`:</span></span>

```csharp
string? name;
```

<span data-ttu-id="8746b-132">Każda zmienna, w której `?` nie jest dołączana do nazwy typu, jest **typem referencyjnym, który nie dopuszcza wartości null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-132">Any variable where the `?` isn't appended to the type name is a **non-nullable reference type**.</span></span> <span data-ttu-id="8746b-133">Zawiera wszystkie zmienne typu referencyjnego w istniejącym kodzie po włączeniu tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8746b-133">That includes all reference type variables in existing code when you've enabled this feature.</span></span>

<span data-ttu-id="8746b-134">Kompilator używa statycznej analizy do ustalenia, czy odwołanie dopuszczające wartość null jest znane jako inne niż null.</span><span class="sxs-lookup"><span data-stu-id="8746b-134">The compiler uses static analysis to determine if a nullable reference is known to be non-null.</span></span> <span data-ttu-id="8746b-135">Kompilator ostrzega o tym, jeśli odwołujesz się do odwołania do wartości null, jeśli może to mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-135">The compiler warns you if you dereference a nullable reference when it may be null.</span></span> <span data-ttu-id="8746b-136">Zachowanie to można zastąpić za pomocą [operatora null-łagodniejszej](language-reference/operators/null-forgiving.md) `!` po nazwie zmiennej.</span><span class="sxs-lookup"><span data-stu-id="8746b-136">You can override this behavior by using the [null-forgiving operator](language-reference/operators/null-forgiving.md) `!` following a variable name.</span></span> <span data-ttu-id="8746b-137">Jeśli na przykład wiadomo, że `name` zmienna nie ma wartości null, ale kompilator generuje ostrzeżenie, można napisać następujący kod, aby zastąpić analizę kompilatora:</span><span class="sxs-lookup"><span data-stu-id="8746b-137">For example, if you know the `name` variable isn't null but the compiler issues a warning, you can write the following code to override the compiler's analysis:</span></span>

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a><span data-ttu-id="8746b-138">Wartość zerowa typów</span><span class="sxs-lookup"><span data-stu-id="8746b-138">Nullability of types</span></span>

<span data-ttu-id="8746b-139">Każdy typ referencyjny może mieć jeden z czterech *nullabilities*, który opisuje, kiedy generowane są ostrzeżenia:</span><span class="sxs-lookup"><span data-stu-id="8746b-139">Any reference type can have one of four *nullabilities*, which describes when warnings are generated:</span></span>

- <span data-ttu-id="8746b-140">*Niedopuszczający wartości null*: nie można przypisać wartości null do zmiennych tego typu.</span><span class="sxs-lookup"><span data-stu-id="8746b-140">*Nonnullable*: Null can't be assigned to variables of this type.</span></span> <span data-ttu-id="8746b-141">Przed usunięciem odwołania zmienne tego typu nie muszą mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-141">Variables of this type don't need to be null-checked before dereferencing.</span></span>
- <span data-ttu-id="8746b-142">*Nullable*: wartość null może być przypisana do zmiennych tego typu.</span><span class="sxs-lookup"><span data-stu-id="8746b-142">*Nullable*: Null can be assigned to variables of this type.</span></span> <span data-ttu-id="8746b-143">Odwołujące się do zmiennych tego typu bez uprzedniego sprawdzenia `null` powoduje ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="8746b-143">Dereferencing variables of this type without first checking for `null` causes a warning.</span></span>
- <span data-ttu-id="8746b-144">*Oblivious*: Oblivious jest stanem sprzed C # 8,0.</span><span class="sxs-lookup"><span data-stu-id="8746b-144">*Oblivious*: Oblivious is the pre-C# 8.0 state.</span></span> <span data-ttu-id="8746b-145">Zmienne tego typu mogą być wywoływane lub przypisane bez ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="8746b-145">Variables of this type can be dereferenced or assigned without warnings.</span></span>
- <span data-ttu-id="8746b-146">*Nieznany*: nieznany jest zazwyczaj dla parametrów typu, w których ograniczenia nie informują kompilatora, że typ musi *dopuszczać wartości null* lub nie *dopuszczać wartości null*.</span><span class="sxs-lookup"><span data-stu-id="8746b-146">*Unknown*: Unknown is generally for type parameters where constraints don't tell the compiler that the type must be *nullable* or *nonnullable*.</span></span>

<span data-ttu-id="8746b-147">Wartość null typu w deklaracji zmiennej jest kontrolowana przez *kontekst dopuszczający wartość* null, w którym zmienna jest zadeklarowana.</span><span class="sxs-lookup"><span data-stu-id="8746b-147">The nullability of a type in a variable declaration is controlled by the *nullable context* in which the variable is declared.</span></span>

## <a name="nullable-contexts"></a><span data-ttu-id="8746b-148">Konteksty dopuszczające wartość null</span><span class="sxs-lookup"><span data-stu-id="8746b-148">Nullable contexts</span></span>

<span data-ttu-id="8746b-149">Konteksty dopuszczające wartość null umożliwiają precyzyjne kontrolowanie, w jaki sposób kompilator interpretuje zmienne typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="8746b-149">Nullable contexts enable fine-grained control for how the compiler interprets reference type variables.</span></span> <span data-ttu-id="8746b-150">**Kontekst adnotacji dopuszczający wartość null** w dowolnym wierszu źródłowym jest włączony lub wyłączony.</span><span class="sxs-lookup"><span data-stu-id="8746b-150">The **nullable annotation context** of any given source line is either enabled or disabled.</span></span> <span data-ttu-id="8746b-151">Można traktować kompilator pre-C # 8,0 jako Kompilowanie całego kodu w wyłączonym kontekście dopuszczania wartości null: dowolny typ referencyjny może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-151">You can think of the pre-C# 8.0 compiler as compiling all your code in a disabled nullable context: any reference type may be null.</span></span> <span data-ttu-id="8746b-152">**Kontekst ostrzeżeń dopuszczających wartość null** może być również włączony lub wyłączony.</span><span class="sxs-lookup"><span data-stu-id="8746b-152">The **nullable warnings context** may also be enabled or disabled.</span></span> <span data-ttu-id="8746b-153">Kontekst ostrzeżeń dopuszczających wartość null określa ostrzeżenia generowane przez kompilator przy użyciu analizy przepływu.</span><span class="sxs-lookup"><span data-stu-id="8746b-153">The nullable warnings context specifies the warnings generated by the compiler using its flow analysis.</span></span>

<span data-ttu-id="8746b-154">Kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia dopuszczający wartość null można ustawić dla projektu przy użyciu `Nullable` elementu w pliku *. csproj* .</span><span class="sxs-lookup"><span data-stu-id="8746b-154">The nullable annotation context and nullable warning context can be set for a project using the `Nullable` element in your *.csproj* file.</span></span> <span data-ttu-id="8746b-155">Ten element określa, w jaki sposób kompilator interpretuje wartość null typów i jakie ostrzeżenia są generowane.</span><span class="sxs-lookup"><span data-stu-id="8746b-155">This element configures how the compiler interprets the nullability of types and what warnings are generated.</span></span> <span data-ttu-id="8746b-156">Prawidłowe ustawienia to:</span><span class="sxs-lookup"><span data-stu-id="8746b-156">Valid settings are:</span></span>

- <span data-ttu-id="8746b-157">`enable`: Kontekst adnotacji z dopuszczaniem wartości null jest **włączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-157">`enable`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="8746b-158">Kontekst ostrzegawczy dopuszczający wartość null jest **włączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-158">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="8746b-159">Zmienne typu referencyjnego, `string` na przykład, nie dopuszczają wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-159">Variables of a reference type, `string` for example, are non-nullable.</span></span>  <span data-ttu-id="8746b-160">Wszystkie ostrzeżenia o wartości null są włączone.</span><span class="sxs-lookup"><span data-stu-id="8746b-160">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="8746b-161">`warnings`: Kontekst adnotacji dopuszczający wartość null jest **wyłączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-161">`warnings`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="8746b-162">Kontekst ostrzegawczy dopuszczający wartość null jest **włączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-162">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="8746b-163">Zmienne typu referencyjnego to Oblivious.</span><span class="sxs-lookup"><span data-stu-id="8746b-163">Variables of a reference type are oblivious.</span></span> <span data-ttu-id="8746b-164">Wszystkie ostrzeżenia o wartości null są włączone.</span><span class="sxs-lookup"><span data-stu-id="8746b-164">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="8746b-165">`annotations`: Kontekst adnotacji z dopuszczaniem wartości null jest **włączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-165">`annotations`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="8746b-166">Kontekst ostrzegawczy dopuszczający wartość null jest **wyłączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-166">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="8746b-167">Zmienne typu referencyjnego, ciąg na przykład, nie dopuszczają wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-167">Variables of a reference type, string for example, are non-nullable.</span></span> <span data-ttu-id="8746b-168">Wszystkie ostrzeżenia o wartości null są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="8746b-168">All nullability warnings are disabled.</span></span>
- <span data-ttu-id="8746b-169">`disable`: Kontekst adnotacji dopuszczający wartość null jest **wyłączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-169">`disable`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="8746b-170">Kontekst ostrzegawczy dopuszczający wartość null jest **wyłączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-170">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="8746b-171">Zmienne typu referencyjnego to Oblivious, podobnie jak w przypadku wcześniejszych wersji języka C#.</span><span class="sxs-lookup"><span data-stu-id="8746b-171">Variables of a reference type are oblivious, just like earlier versions of C#.</span></span> <span data-ttu-id="8746b-172">Wszystkie ostrzeżenia o wartości null są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="8746b-172">All nullability warnings are disabled.</span></span>

<span data-ttu-id="8746b-173">**Przykład**:</span><span class="sxs-lookup"><span data-stu-id="8746b-173">**Example**:</span></span>

```xml
<Nullable>enable</Nullable>
```

<span data-ttu-id="8746b-174">Możesz również użyć dyrektyw, aby ustawić te same konteksty w dowolnym miejscu w projekcie:</span><span class="sxs-lookup"><span data-stu-id="8746b-174">You can also use directives to set these same contexts anywhere in your project:</span></span>

- <span data-ttu-id="8746b-175">`#nullable enable`: Ustawia kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia nullable do **włączenia**.</span><span class="sxs-lookup"><span data-stu-id="8746b-175">`#nullable enable`: Sets the nullable annotation context and nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="8746b-176">`#nullable disable`: Ustawia kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia dopuszczający wartość **null.**</span><span class="sxs-lookup"><span data-stu-id="8746b-176">`#nullable disable`: Sets the nullable annotation context and nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="8746b-177">`#nullable restore`: Przywraca kontekst adnotacji dopuszczający wartość null i kontekst ostrzeżenia do wartości null w ustawieniach projektu.</span><span class="sxs-lookup"><span data-stu-id="8746b-177">`#nullable restore`: Restores the nullable annotation context and nullable warning context to the project settings.</span></span>
- <span data-ttu-id="8746b-178">`#nullable disable warnings`: Ustaw dla kontekstu ostrzeżenia o wartości null wartość **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="8746b-178">`#nullable disable warnings`: Set the nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="8746b-179">`#nullable enable warnings`: Ustaw kontekst ostrzegawczy dopuszczający wartość **null.**</span><span class="sxs-lookup"><span data-stu-id="8746b-179">`#nullable enable warnings`: Set the nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="8746b-180">`#nullable restore warnings`: Przywraca kontekst ostrzegawczy dopuszczający wartość null do ustawień projektu.</span><span class="sxs-lookup"><span data-stu-id="8746b-180">`#nullable restore warnings`: Restores the nullable warning context to the project settings.</span></span>
- <span data-ttu-id="8746b-181">`#nullable disable annotations`: Ustaw dla kontekstu adnotacji wartości null wartość **wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="8746b-181">`#nullable disable annotations`: Set the nullable annotation context to **disabled**.</span></span>
- <span data-ttu-id="8746b-182">`#nullable enable annotations`: Ustaw dla kontekstu adnotacji nullable wartość **włączone**.</span><span class="sxs-lookup"><span data-stu-id="8746b-182">`#nullable enable annotations`: Set the nullable annotation context to **enabled**.</span></span>
- <span data-ttu-id="8746b-183">`#nullable restore annotations`: Przywraca kontekst ostrzeżenia adnotacji do ustawień projektu.</span><span class="sxs-lookup"><span data-stu-id="8746b-183">`#nullable restore annotations`: Restores the annotation warning context to the project settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8746b-184">Globalny kontekst dopuszczający wartość null nie ma zastosowania do wygenerowanych plików kodu.</span><span class="sxs-lookup"><span data-stu-id="8746b-184">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="8746b-185">W ramach którejkolwiek z tych strategii kontekst dopuszczający wartość null jest *wyłączony* dla każdego pliku źródłowego oznaczonego jako wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="8746b-185">Under either strategy, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="8746b-186">Oznacza to, że wszystkie interfejsy API w wygenerowanych plikach nie są adnotacjami.</span><span class="sxs-lookup"><span data-stu-id="8746b-186">This means any APIs in generated files are not annotated.</span></span> <span data-ttu-id="8746b-187">Istnieją cztery sposoby, aby plik został oznaczony jako wygenerowany:</span><span class="sxs-lookup"><span data-stu-id="8746b-187">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="8746b-188">W pliku. editorconfig Określ `generated_code = true` w sekcji, która odnosi się do tego plik.</span><span class="sxs-lookup"><span data-stu-id="8746b-188">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="8746b-189">Umieść `<auto-generated>` lub `<auto-generated/>` w komentarzu w górnej części pliku.</span><span class="sxs-lookup"><span data-stu-id="8746b-189">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="8746b-190">Może znajdować się w dowolnym wierszu tego komentarza, ale blok komentarza musi być pierwszym elementem w pliku.</span><span class="sxs-lookup"><span data-stu-id="8746b-190">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="8746b-191">Uruchom nazwę pliku z *TemporaryGeneratedFile_*</span><span class="sxs-lookup"><span data-stu-id="8746b-191">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="8746b-192">Zakończ nazwę pliku z rozszerzeniem *. Designer.cs*, *. generated.cs*, *. g.cs* lub *. g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="8746b-192">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="8746b-193">Generatory mogą wyrazić zgodę na użycie [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) dyrektywy preprocesora.</span><span class="sxs-lookup"><span data-stu-id="8746b-193">Generators can opt-in using the [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

<span data-ttu-id="8746b-194">Domyślnie adnotacja null i konteksty ostrzeżeń są **wyłączone**, w tym nowych projektów.</span><span class="sxs-lookup"><span data-stu-id="8746b-194">By default, nullable annotation and warning contexts are **disabled**, including new projects.</span></span> <span data-ttu-id="8746b-195">Oznacza to, że istniejący kod kompiluje się bez zmian i nie generuje żadnych nowych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="8746b-195">That means that your existing code compiles without changes and without generating any new warnings.</span></span>

<span data-ttu-id="8746b-196">Te opcje zapewniają dwie odrębne strategie [aktualizowania istniejącej bazy kodu](nullable-migration-strategies.md) w celu użycia typów referencyjnych dopuszczających wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-196">These options provide two distinct strategies to [update an existing codebase](nullable-migration-strategies.md) to use nullable reference types.</span></span>

## <a name="nullable-annotation-context"></a><span data-ttu-id="8746b-197">Kontekst adnotacji dopuszczający wartość null</span><span class="sxs-lookup"><span data-stu-id="8746b-197">Nullable annotation context</span></span>

<span data-ttu-id="8746b-198">Kompilator używa następujących reguł w wyłączonym kontekście adnotacji nullable:</span><span class="sxs-lookup"><span data-stu-id="8746b-198">The compiler uses the following rules in a disabled nullable annotation context:</span></span>

- <span data-ttu-id="8746b-199">Nie można zadeklarować odwołań do wartości null w wyłączonym kontekście.</span><span class="sxs-lookup"><span data-stu-id="8746b-199">You can't declare nullable references in a disabled context.</span></span>
- <span data-ttu-id="8746b-200">Wszystkie zmienne odwołania mogą mieć przypisaną wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-200">All reference variables may be assigned a value of null.</span></span>
- <span data-ttu-id="8746b-201">Nie są generowane żadne ostrzeżenia, gdy zmienna typu odwołania jest wykorzystana.</span><span class="sxs-lookup"><span data-stu-id="8746b-201">No warnings are generated when a variable of a reference type is dereferenced.</span></span>
- <span data-ttu-id="8746b-202">Operatora null-łagodniejszej nie można używać w wyłączonym kontekście.</span><span class="sxs-lookup"><span data-stu-id="8746b-202">The null-forgiving operator may not be used in a disabled context.</span></span>

<span data-ttu-id="8746b-203">Zachowanie jest takie samo jak w poprzednich wersjach języka C#.</span><span class="sxs-lookup"><span data-stu-id="8746b-203">The behavior is the same as previous versions of C#.</span></span>

<span data-ttu-id="8746b-204">Kompilator używa następujących reguł w włączonym kontekście adnotacji dopuszczających wartość null:</span><span class="sxs-lookup"><span data-stu-id="8746b-204">The compiler uses the following rules in an enabled nullable annotation context:</span></span>

- <span data-ttu-id="8746b-205">Dowolna zmienna typu referencyjnego jest **odwołaniem niedopuszczanym do wartości null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-205">Any variable of a reference type is a **non-nullable reference**.</span></span>
- <span data-ttu-id="8746b-206">Wszystkie odwołania niedopuszczające wartości null mogą być bezpiecznie wywoływać.</span><span class="sxs-lookup"><span data-stu-id="8746b-206">Any non-nullable reference may be dereferenced safely.</span></span>
- <span data-ttu-id="8746b-207">Dowolny typ referencyjny dopuszczający wartość null (zanotowany przez `?` po typie w deklaracji zmiennej) może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-207">Any nullable reference type (noted by `?` after the type in the variable declaration) may be null.</span></span> <span data-ttu-id="8746b-208">Analiza statyczna określa, czy wartość jest znana jako inna niż null, gdy jest ona wywoływać.</span><span class="sxs-lookup"><span data-stu-id="8746b-208">Static analysis determines if the value is known to be non-null when it's dereferenced.</span></span> <span data-ttu-id="8746b-209">W przeciwnym razie kompilator wyświetli ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="8746b-209">If not, the compiler warns you.</span></span>
- <span data-ttu-id="8746b-210">Można użyć operatora null-łagodniejszej, aby zadeklarować, że odwołanie dopuszczające wartość null nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-210">You can use the null-forgiving operator to declare that a nullable reference isn't null.</span></span>

<span data-ttu-id="8746b-211">W włączonym kontekście dopuszczającym wartość null, `?` znak dołączony do typu referencyjnego deklaruje **typ referencyjny dopuszczający wartość null**.</span><span class="sxs-lookup"><span data-stu-id="8746b-211">In an enabled nullable annotation context, the `?` character appended to a reference type declares a **nullable reference type**.</span></span> <span data-ttu-id="8746b-212">**Operator null-łagodniejszej** `!` może być dołączany do wyrażenia, aby zadeklarować, że wyrażenie nie ma wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-212">The **null-forgiving operator** `!` may be appended to an expression to declare that the expression isn't null.</span></span>

## <a name="nullable-warning-context"></a><span data-ttu-id="8746b-213">Kontekst ostrzegawczy dopuszczający wartość null</span><span class="sxs-lookup"><span data-stu-id="8746b-213">Nullable warning context</span></span>

<span data-ttu-id="8746b-214">Kontekst ostrzeżenia dopuszczający wartość null jest różny od kontekstu adnotacji dopuszczającej wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-214">The nullable warning context is distinct from the nullable annotation context.</span></span> <span data-ttu-id="8746b-215">Ostrzeżenia można włączyć nawet wtedy, gdy nowe adnotacje są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="8746b-215">Warnings can be enabled even when the new annotations are disabled.</span></span> <span data-ttu-id="8746b-216">Kompilator używa statycznej analizy przepływu do określenia **stanu null** dowolnych odwołań.</span><span class="sxs-lookup"><span data-stu-id="8746b-216">The compiler uses static flow analysis to determine the **null state** of any reference.</span></span> <span data-ttu-id="8746b-217">Stan o wartości null **nie ma wartości null** lub **może mieć wartość null** , jeśli *kontekst ostrzeżenia o wartości null* nie jest **wyłączony**.</span><span class="sxs-lookup"><span data-stu-id="8746b-217">The null state is either **not null** or **maybe null** when the *nullable warning context* isn't **disabled**.</span></span> <span data-ttu-id="8746b-218">Jeśli odwołujesz się do odwołania, gdy kompilator ustalił, że **może mieć wartość null**, kompilator wyświetli ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="8746b-218">If you dereference a reference when the compiler has determined it's **maybe null**, the compiler warns you.</span></span> <span data-ttu-id="8746b-219">Stan odwołania może **mieć wartość null** , chyba że kompilator może określić jeden z dwóch warunków:</span><span class="sxs-lookup"><span data-stu-id="8746b-219">The state of a reference is **maybe null** unless the compiler can determine one of two conditions:</span></span>

1. <span data-ttu-id="8746b-220">Zmienna ma w nieskończoność przypisaną wartość różną od null.</span><span class="sxs-lookup"><span data-stu-id="8746b-220">The variable has been definitely assigned a non-null value.</span></span>
1. <span data-ttu-id="8746b-221">Zmienna lub wyrażenie zostało sprawdzone pod kątem wartości null przed usunięciem odwołania do niego.</span><span class="sxs-lookup"><span data-stu-id="8746b-221">The variable or expression has been checked against null before de-referencing it.</span></span>

<span data-ttu-id="8746b-222">Kompilator generuje ostrzeżenia, gdy zostanie wykorzystana zmienna lub wyrażenie, które **może mieć wartość null** w kontekście ostrzeżenia o wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-222">The compiler generates warnings when you dereference a variable or expression that is **maybe null** in a nullable warning context.</span></span> <span data-ttu-id="8746b-223">Co więcej, kompilator generuje ostrzeżenia, gdy zmienna typu odwołania, która nie ma wartości null, **może mieć zmienną null** lub wyrażenie w włączonym kontekście adnotacji nullable.</span><span class="sxs-lookup"><span data-stu-id="8746b-223">Furthermore, the compiler generates warnings when a nonnullable reference-type variable is assigned a **maybe null** variable or expression in an enabled nullable annotation context.</span></span>

## <a name="attributes-describe-apis"></a><span data-ttu-id="8746b-224">Opisy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8746b-224">Attributes describe APIs</span></span>

<span data-ttu-id="8746b-225">Dodaj atrybuty do interfejsów API, które udostępniają kompilatorowi więcej informacji na temat sytuacji, gdy argumenty lub wartości zwracane mogą lub nie mogą mieć wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-225">You add attributes to APIs that provide the compiler more information about when arguments or return values can or can't be null.</span></span> <span data-ttu-id="8746b-226">Więcej informacji o tych atrybutach można znaleźć w naszym artykule w dokumentacji języka obejmującej [atrybuty dopuszczające wartość null](language-reference/attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="8746b-226">You can learn more about these attributes in our article in the language reference covering the [nullable attributes](language-reference/attributes/nullable-analysis.md).</span></span> <span data-ttu-id="8746b-227">Te atrybuty są dodawane do bibliotek .NET za pośrednictwem bieżących i przyszłych wersji.</span><span class="sxs-lookup"><span data-stu-id="8746b-227">These attributes are being added to .NET libraries over current and upcoming releases.</span></span> <span data-ttu-id="8746b-228">Najczęściej używane interfejsy API są aktualizowane jako pierwsze.</span><span class="sxs-lookup"><span data-stu-id="8746b-228">The most commonly used APIs are being updated first.</span></span>

## <a name="known-pitfalls"></a><span data-ttu-id="8746b-229">Znane pułapek</span><span class="sxs-lookup"><span data-stu-id="8746b-229">Known pitfalls</span></span>

<span data-ttu-id="8746b-230">Tablice i struktury, które zawierają typy odwołań, są znane pułapek w funkcji typów referencyjnych dopuszczających wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-230">Arrays and structs that contain reference types are known pitfalls in nullable reference types feature.</span></span>

### <a name="structs"></a><span data-ttu-id="8746b-231">Struktury</span><span class="sxs-lookup"><span data-stu-id="8746b-231">Structs</span></span>

<span data-ttu-id="8746b-232">Struktura, która zawiera typy odwołań niedopuszczających wartości null, umożliwia przypisanie `default` do niego bez żadnych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="8746b-232">A struct that contains non-nullable reference types allows assigning `default` for it without any warnings.</span></span> <span data-ttu-id="8746b-233">Rozpatrzmy następujący przykład:</span><span class="sxs-lookup"><span data-stu-id="8746b-233">Consider the following example:</span></span>

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

<span data-ttu-id="8746b-234">W powyższym przykładzie nie ma żadnego ostrzeżenia w `PrintStudent(default)` czasie, gdy typy odwołań niedopuszczających wartości null `FirstName` i `LastName` mają wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-234">In the preceding example, there is no warning in `PrintStudent(default)` while the non-nullable reference types `FirstName` and `LastName` are null.</span></span>

<span data-ttu-id="8746b-235">Innym często spotykanym przypadkiem jest to, że należy zająć się ogólnymi strukturami.</span><span class="sxs-lookup"><span data-stu-id="8746b-235">Another more common case is when you deal with generic structs.</span></span> <span data-ttu-id="8746b-236">Rozpatrzmy następujący przykład:</span><span class="sxs-lookup"><span data-stu-id="8746b-236">Consider the following example:</span></span>

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

<span data-ttu-id="8746b-237">W poprzednim przykładzie właściwość `Bar` ma być `null` w czasie wykonywania i jest przypisywana do niedopuszczających wartości null ciągów bez żadnych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="8746b-237">In the preceding example, the property `Bar` is going to be `null` at runtime, and it's assigned to non-nullable string without any warnings.</span></span>

### <a name="arrays"></a><span data-ttu-id="8746b-238">Tablice</span><span class="sxs-lookup"><span data-stu-id="8746b-238">Arrays</span></span>

<span data-ttu-id="8746b-239">Tablice są również znanymi Pitfall w typach referencyjnych dopuszczających wartość null.</span><span class="sxs-lookup"><span data-stu-id="8746b-239">Arrays are also a known pitfall in nullable reference types.</span></span> <span data-ttu-id="8746b-240">Rozważmy następujący przykład, który nie wygenerował żadnych ostrzeżeń:</span><span class="sxs-lookup"><span data-stu-id="8746b-240">Consider the following example which doesn't produce any warnings:</span></span>

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

<span data-ttu-id="8746b-241">W poprzednim przykładzie deklaracja tablicy pokazuje, że zawiera ciągi niedopuszczające wartości null, podczas gdy jego elementy są zainicjowane do wartości null.</span><span class="sxs-lookup"><span data-stu-id="8746b-241">In the preceding example, the declaration of the array shows it holds non-nullable strings, while its elements are all initialized to null.</span></span> <span data-ttu-id="8746b-242">Następnie zmienna `s` ma przypisaną wartość null (pierwszy element tablicy).</span><span class="sxs-lookup"><span data-stu-id="8746b-242">Then, the variable `s` is assigned a null value (the first element of the array).</span></span> <span data-ttu-id="8746b-243">Na koniec zmienna jest usuwana z `s` powodu wyjątku czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="8746b-243">Finally, the variable `s` is dereferenced causing a runtime exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="8746b-244">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8746b-244">See also</span></span>

- [<span data-ttu-id="8746b-245">Specyfikacja typu referencyjnego dopuszczająca wartość null</span><span class="sxs-lookup"><span data-stu-id="8746b-245">Draft nullable reference types specification</span></span>](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)
- [<span data-ttu-id="8746b-246">Samouczek wprowadzający do odwołań do wartości null</span><span class="sxs-lookup"><span data-stu-id="8746b-246">Intro to nullable references tutorial</span></span>](tutorials/nullable-reference-types.md)
- [<span data-ttu-id="8746b-247">Migrowanie istniejącej bazy kodu do odwołań do wartości null</span><span class="sxs-lookup"><span data-stu-id="8746b-247">Migrate an existing codebase to nullable references</span></span>](tutorials/upgrade-to-nullable-references.md)
- [<span data-ttu-id="8746b-248">-Nullable (opcja kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="8746b-248">-nullable (C# Compiler option)</span></span>](language-reference/compiler-options/nullable-compiler-option.md)
