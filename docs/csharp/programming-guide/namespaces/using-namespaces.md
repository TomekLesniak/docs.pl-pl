---
title: Korzystanie z przestrzeni nazw — Przewodnik programowania w języku C#
description: Dowiedz się, jak używać przestrzeni nazw w programowaniu języka C#, takich jak uzyskiwanie dostępu do przestrzeni nazw, aliasów przestrzeni nazw i używanie przestrzeni nazw do sterowania zakresem.
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 86892f50e059c16ee9c133d7ba9f2716e11a8e56
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381700"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="e46e1-103">Używanie przestrzeni nazw (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e46e1-103">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="e46e1-104">Przestrzenie nazw są intensywnie używane w programach C# na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="e46e1-104">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="e46e1-105">Po pierwsze klasy .NET używają przestrzeni nazw do organizowania wielu klas.</span><span class="sxs-lookup"><span data-stu-id="e46e1-105">Firstly, the .NET classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="e46e1-106">Po drugie, zadeklarowanie własnych przestrzeni nazw może pomóc w kontroli zakresu nazw klas i metod w większych projektach programistycznych.</span><span class="sxs-lookup"><span data-stu-id="e46e1-106">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="e46e1-107">Uzyskiwanie dostępu do przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="e46e1-107">Accessing namespaces</span></span>

 <span data-ttu-id="e46e1-108">Większość aplikacji C# zaczyna się od sekcji `using` dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="e46e1-108">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="e46e1-109">Ta sekcja zawiera listę przestrzeni nazw, których aplikacja będzie często używać, i zapisuje programistę w celu określenia w pełni kwalifikowanej nazwy za każdym razem, gdy używana jest metoda, która jest zawarta w.</span><span class="sxs-lookup"><span data-stu-id="e46e1-109">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="e46e1-110">Na przykład, dołączając wiersz:</span><span class="sxs-lookup"><span data-stu-id="e46e1-110">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="e46e1-111">Na początku programu programista może użyć kodu:</span><span class="sxs-lookup"><span data-stu-id="e46e1-111">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="e46e1-112">Zamiast:</span><span class="sxs-lookup"><span data-stu-id="e46e1-112">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="e46e1-113">Aliasy przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="e46e1-113">Namespace aliases</span></span>

 <span data-ttu-id="e46e1-114">Możesz również użyć [ `using` dyrektywy](../../language-reference/keywords/using-directive.md) , aby utworzyć alias dla przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e46e1-114">You can also use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="e46e1-115">Użyj [kwalifikatora `::` aliasu przestrzeni nazw](../../language-reference/operators/namespace-alias-qualifier.md) , aby uzyskać dostęp do elementów członkowskich aliasu przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e46e1-115">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="e46e1-116">Poniższy przykład przedstawia sposób tworzenia i używania aliasu przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="e46e1-116">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="e46e1-117">Używanie przestrzeni nazw do sterowania zakresem</span><span class="sxs-lookup"><span data-stu-id="e46e1-117">Using namespaces to control scope</span></span>

 <span data-ttu-id="e46e1-118">`namespace`Słowo kluczowe jest używane do deklarowania zakresu.</span><span class="sxs-lookup"><span data-stu-id="e46e1-118">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="e46e1-119">Możliwość tworzenia zakresów w projekcie pomaga organizować kod i umożliwia tworzenie typów unikatowych globalnie.</span><span class="sxs-lookup"><span data-stu-id="e46e1-119">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="e46e1-120">W poniższym przykładzie Klasa zatytułowana `SampleClass` jest zdefiniowana w dwóch przestrzeniach nazw, jedna zagnieżdżona w drugim.</span><span class="sxs-lookup"><span data-stu-id="e46e1-120">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="e46e1-121">[ `.` Token](../../language-reference/operators/member-access-operators.md#member-access-expression-) jest używany do odróżnienia metody wywoływanej.</span><span class="sxs-lookup"><span data-stu-id="e46e1-121">The [`.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="e46e1-122">W pełni kwalifikowane nazwy</span><span class="sxs-lookup"><span data-stu-id="e46e1-122">Fully qualified names</span></span>

 <span data-ttu-id="e46e1-123">Przestrzenie nazw i typy mają unikatowe tytuły opisane przez w pełni kwalifikowane nazwy wskazujące hierarchię logiczną.</span><span class="sxs-lookup"><span data-stu-id="e46e1-123">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="e46e1-124">Na przykład instrukcja oznacza, `A.B` że `A` jest nazwą przestrzeni nazw lub typem, i `B` jest zagnieżdżona wewnątrz niej.</span><span class="sxs-lookup"><span data-stu-id="e46e1-124">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="e46e1-125">W poniższym przykładzie istnieją zagnieżdżone klasy i przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="e46e1-125">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="e46e1-126">W pełni kwalifikowana nazwa jest wskazywana jako komentarz po każdej jednostce.</span><span class="sxs-lookup"><span data-stu-id="e46e1-126">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="e46e1-127">W poprzednim segmencie kodu:</span><span class="sxs-lookup"><span data-stu-id="e46e1-127">In the previous code segment:</span></span>  
  
- <span data-ttu-id="e46e1-128">Przestrzeń nazw `N1` jest członkiem globalnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e46e1-128">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="e46e1-129">Jego w pełni kwalifikowana nazwa jest `N1` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-129">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="e46e1-130">Przestrzeń nazw `N2` jest członkiem `N1` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-130">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="e46e1-131">Jego w pełni kwalifikowana nazwa jest `N1.N2` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-131">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="e46e1-132">Klasa `C1` jest członkiem `N1` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-132">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="e46e1-133">Jego w pełni kwalifikowana nazwa jest `N1.C1` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-133">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="e46e1-134">Nazwa klasy `C2` jest używana dwa razy w tym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e46e1-134">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="e46e1-135">Jednak w pełni kwalifikowane nazwy są unikatowe.</span><span class="sxs-lookup"><span data-stu-id="e46e1-135">However, the fully qualified names are unique.</span></span> <span data-ttu-id="e46e1-136">Pierwsze wystąpienie `C2` jest zadeklarowane wewnątrz `C1` ; w związku z tym jego w pełni kwalifikowana nazwa to: `N1.C1.C2` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-136">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="e46e1-137">Drugie wystąpienie `C2` jest zadeklarowane wewnątrz przestrzeni nazw `N2` ; w związku z tym jego w pełni kwalifikowana nazwa jest `N1.N2.C2` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-137">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="e46e1-138">Korzystając z poprzedniego segmentu kodu, można dodać nowy element członkowski klasy, `C3` , do przestrzeni nazw `N1.N2` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e46e1-138">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="e46e1-139">Ogólnie rzecz biorąc, użyj [kwalifikatora `::` aliasu przestrzeni nazw](../../language-reference/operators/namespace-alias-qualifier.md) , aby odwołać się do aliasu przestrzeni nazw lub `global::` odwoływać się do globalnej przestrzeni nazw oraz `.` do kwalifikowania typów lub członków.</span><span class="sxs-lookup"><span data-stu-id="e46e1-139">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="e46e1-140">Jest to błąd używany `::` z aliasem, który odwołuje się do typu zamiast przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e46e1-140">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="e46e1-141">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="e46e1-141">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="e46e1-142">Należy pamiętać, że słowo `global` nie jest wstępnie zdefiniowanym aliasem; w związku z tym nie `global.X` ma żadnych specjalnych znaczenia.</span><span class="sxs-lookup"><span data-stu-id="e46e1-142">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="e46e1-143">Uzyskuje specjalne znaczenie tylko wtedy, gdy jest używany z `::` .</span><span class="sxs-lookup"><span data-stu-id="e46e1-143">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="e46e1-144">Ostrzeżenie kompilatora CS0440 jest generowany, jeśli zdefiniujesz alias o nazwie Global, ponieważ `global::` zawsze odwołuje się do globalnej przestrzeni nazw, a nie do aliasu.</span><span class="sxs-lookup"><span data-stu-id="e46e1-144">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="e46e1-145">Na przykład poniższy wiersz generuje ostrzeżenie:</span><span class="sxs-lookup"><span data-stu-id="e46e1-145">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="e46e1-146">Korzystanie `::` z aliasów jest dobrym pomysłem i chroni przed nieoczekiwanym wprowadzeniem dodatkowych typów.</span><span class="sxs-lookup"><span data-stu-id="e46e1-146">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="e46e1-147">Rozważmy na przykład ten przykład:</span><span class="sxs-lookup"><span data-stu-id="e46e1-147">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="e46e1-148">To działa, ale jeśli typ nazwany `Alias` miał zostać później wprowadzony, `Alias.` zostałby powiązać z tym typem.</span><span class="sxs-lookup"><span data-stu-id="e46e1-148">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="e46e1-149">Użycie `Alias::Exception` gwarantuje, że `Alias` jest traktowany jako alias przestrzeni nazw i nie zostanie pomylony z typem.</span><span class="sxs-lookup"><span data-stu-id="e46e1-149">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e46e1-150">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e46e1-150">See also</span></span>

- [<span data-ttu-id="e46e1-151">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e46e1-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e46e1-152">Przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="e46e1-152">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="e46e1-153">Wyrażenie dostępu do składowej</span><span class="sxs-lookup"><span data-stu-id="e46e1-153">Member access expression</span></span>](../../language-reference/operators/member-access-operators.md#member-access-expression-)
- [<span data-ttu-id="e46e1-154">:: — Operator</span><span class="sxs-lookup"><span data-stu-id="e46e1-154">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="e46e1-155">alias zewnętrzny</span><span class="sxs-lookup"><span data-stu-id="e46e1-155">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
