---
title: 'Deklaracje importowania: open — Słowo kluczowe'
description: 'Dowiedz się więcej o deklaracjach importu F # i sposobach określania modułu lub przestrzeni nazw, których elementy można odwołać bez użycia w pełni kwalifikowanej nazwy.'
ms.date: 04/04/2019
ms.openlocfilehash: 2b88427ca92212fb4a7598447dd1a5e12061093a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855091"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="2b86b-103">Deklaracje importu: `open` słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="2b86b-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="2b86b-104">*Deklaracja importu* określa moduł lub przestrzeń nazw, których elementy można odwoływać bez używania w pełni kwalifikowanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="2b86b-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b86b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2b86b-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="2b86b-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2b86b-106">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="2b86b-107">Dokumentacja interfejsu API docs.microsoft.com dla języka F # nie została ukończona.</span><span class="sxs-lookup"><span data-stu-id="2b86b-107">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="2b86b-108">Jeśli wystąpią jakieś przerwane linki, należy odwołać się do [dokumentacji podstawowej biblioteki języka F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="2b86b-108">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

<span data-ttu-id="2b86b-109">Odwoływanie się do kodu przy użyciu w pełni kwalifikowanej przestrzeni nazw lub ścieżki modułu za każdym razem, gdy program może utworzyć kod, który jest trudno pisać, czytać i konserwować.</span><span class="sxs-lookup"><span data-stu-id="2b86b-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="2b86b-110">Zamiast tego można użyć `open` słowa kluczowego dla często używanych modułów i przestrzeni nazw, aby podczas odwoływania się do elementu członkowskiego tego modułu lub przestrzeni nazw można użyć krótkiej formy nazwy zamiast w pełni kwalifikowanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="2b86b-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="2b86b-111">To słowo kluczowe jest podobne do `using` słowa kluczowego w języku C#, `using namespace` w Visual C++ i `Imports` w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2b86b-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="2b86b-112">Dostarczony moduł lub przestrzeń nazw muszą znajdować się w tym samym projekcie lub w przywoływanym projekcie lub zestawie.</span><span class="sxs-lookup"><span data-stu-id="2b86b-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="2b86b-113">Jeśli tak nie jest, można dodać odwołanie do projektu lub użyć `-reference` opcji wiersza polecenia (lub jego skrótu `-r` ).</span><span class="sxs-lookup"><span data-stu-id="2b86b-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="2b86b-114">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="2b86b-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="2b86b-115">Deklaracja importu udostępnia nazwy dostępne w kodzie, który następuje po deklaracji, do końca otaczającej przestrzeni nazw, modułu lub pliku.</span><span class="sxs-lookup"><span data-stu-id="2b86b-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="2b86b-116">Jeśli używasz wielu deklaracji importu, powinny one pojawiać się w osobnych wierszach.</span><span class="sxs-lookup"><span data-stu-id="2b86b-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="2b86b-117">Poniższy kod ilustruje użycie `open` słowa kluczowego w celu uproszczenia kodu.</span><span class="sxs-lookup"><span data-stu-id="2b86b-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="2b86b-118">Kompilator F # nie emituje błędu lub ostrzeżenia, gdy niejasności występuje, gdy ta sama nazwa wystąpi w więcej niż jednym otwartym module lub przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2b86b-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="2b86b-119">Gdy wystąpi niejasności, język F # zapewnia preferencję dla ostatnio otwartego modułu lub przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2b86b-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="2b86b-120">Na przykład, w poniższym kodzie, oznacza, chociaż znajduje się `empty` `Seq.empty` `empty` zarówno w `List` module, jak i `Seq` .</span><span class="sxs-lookup"><span data-stu-id="2b86b-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="2b86b-121">W związku z tym należy zachować ostrożność podczas otwierania modułów lub przestrzeni nazw, takich jak `List` lub zawierających `Seq` składowe o identycznych nazwach. zamiast tego należy rozważyć użycie kwalifikowanych nazw.</span><span class="sxs-lookup"><span data-stu-id="2b86b-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="2b86b-122">Należy unikać każdej sytuacji, w której kod jest zależny od kolejności deklaracji importu.</span><span class="sxs-lookup"><span data-stu-id="2b86b-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="2b86b-123">Obszary nazw, które są domyślnie otwarte</span><span class="sxs-lookup"><span data-stu-id="2b86b-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="2b86b-124">Niektóre przestrzenie nazw są często używane w kodzie języka F #, które są otwierane niejawnie bez potrzeby jawnej deklaracji importu.</span><span class="sxs-lookup"><span data-stu-id="2b86b-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="2b86b-125">W poniższej tabeli przedstawiono obszary nazw, które są domyślnie otwarte.</span><span class="sxs-lookup"><span data-stu-id="2b86b-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="2b86b-126">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="2b86b-126">Namespace</span></span>|<span data-ttu-id="2b86b-127">Opis</span><span class="sxs-lookup"><span data-stu-id="2b86b-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="2b86b-128">Zawiera podstawowe definicje typu języka F # dla typów wbudowanych, takich jak `int` i `float` .</span><span class="sxs-lookup"><span data-stu-id="2b86b-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="2b86b-129">Zawiera podstawowe operacje arytmetyczne, takie jak `+` i `*` .</span><span class="sxs-lookup"><span data-stu-id="2b86b-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="2b86b-130">Zawiera niezmienne klasy kolekcji, takie jak `List` i `Array` .</span><span class="sxs-lookup"><span data-stu-id="2b86b-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="2b86b-131">Zawiera typy dla konstrukcji kontroli, takich jak Ocena z opóźnieniem i asynchroniczne przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="2b86b-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="2b86b-132">Zawiera funkcje dla sformatowanych operacji we/wy, takich jak `printf` Funkcja.</span><span class="sxs-lookup"><span data-stu-id="2b86b-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="2b86b-133">AutoOpen — atrybut</span><span class="sxs-lookup"><span data-stu-id="2b86b-133">AutoOpen Attribute</span></span>

<span data-ttu-id="2b86b-134">Można zastosować `AutoOpen` atrybut do zestawu, jeśli chcesz automatycznie otworzyć przestrzeń nazw lub moduł, gdy odwołanie do zestawu.</span><span class="sxs-lookup"><span data-stu-id="2b86b-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="2b86b-135">Można również zastosować `AutoOpen` atrybut do modułu, aby automatycznie otworzyć ten moduł po otwarciu modułu nadrzędnego lub przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2b86b-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="2b86b-136">Aby uzyskać więcej informacji, zobacz [Klasa Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="2b86b-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="2b86b-137">RequireQualifiedAccess — atrybut</span><span class="sxs-lookup"><span data-stu-id="2b86b-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="2b86b-138">Niektóre moduły, rekordy lub typy Unii mogą określać `RequireQualifiedAccess` atrybut.</span><span class="sxs-lookup"><span data-stu-id="2b86b-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="2b86b-139">Gdy odwołujesz się do elementów tych modułów, rekordów lub Unii, musisz użyć kwalifikowanej nazwy bez względu na to, czy dołączysz deklarację importu.</span><span class="sxs-lookup"><span data-stu-id="2b86b-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="2b86b-140">Jeśli ten atrybut jest używany strategicznie dla typów, które definiują często używane nazwy, można uniknąć kolizji nazw, a tym samym zwiększyć odporność kodu na zmiany w bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="2b86b-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="2b86b-141">Aby uzyskać więcej informacji, zobacz [Klasa Core. RequireQualifiedAccessAttribute —](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="2b86b-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b86b-142">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2b86b-142">See also</span></span>

- [<span data-ttu-id="2b86b-143">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="2b86b-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2b86b-144">Namespaces</span><span class="sxs-lookup"><span data-stu-id="2b86b-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="2b86b-145">Moduły</span><span class="sxs-lookup"><span data-stu-id="2b86b-145">Modules</span></span>](modules.md)
