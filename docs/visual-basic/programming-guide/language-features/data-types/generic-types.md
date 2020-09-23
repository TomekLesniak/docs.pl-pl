---
title: Typy ogólne
ms.date: 07/20/2015
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
ms.openlocfilehash: f9b343c664baaf316e5cd6df72da8dcf56222382
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090264"
---
# <a name="generic-types-in-visual-basic-visual-basic"></a><span data-ttu-id="57d92-102">Typy ogólne w Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57d92-102">Generic Types in Visual Basic (Visual Basic)</span></span>

<span data-ttu-id="57d92-103">*Typ ogólny* to pojedynczy element programistyczny, który dostosowuje się do wykonywania tych samych funkcji dla różnych typów danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-103">A *generic type* is a single programming element that adapts to perform the same functionality for a variety of data types.</span></span> <span data-ttu-id="57d92-104">Podczas definiowania ogólnej klasy lub procedury nie trzeba definiować oddzielnej wersji dla każdego typu danych, dla którego można wykonać tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="57d92-104">When you define a generic class or procedure, you do not have to define a separate version for each data type for which you might want to perform that functionality.</span></span>  
  
 <span data-ttu-id="57d92-105">Analogowa jest śrubokrętem ustawionym z wymiennymi głowicami.</span><span class="sxs-lookup"><span data-stu-id="57d92-105">An analogy is a screwdriver set with removable heads.</span></span> <span data-ttu-id="57d92-106">Należy sprawdzić, czy jest włączony, i wybrać odpowiednią pozycję dla tego gwintu (prosty, przekreślony, oznaczona gwiazdkami).</span><span class="sxs-lookup"><span data-stu-id="57d92-106">You inspect the screw you need to turn and select the correct head for that screw (slotted, crossed, starred).</span></span> <span data-ttu-id="57d92-107">Po wstawieniu poprawnej głowy w uchwycie śrubokrętu należy wykonać dokładną funkcję ze śrubokrętem, a mianowicie przekształceniem.</span><span class="sxs-lookup"><span data-stu-id="57d92-107">Once you insert the correct head in the screwdriver handle, you perform the exact same function with the screwdriver, namely turning the screw.</span></span>  
  
 ![Diagram zestawu śrubokrętów z różnymi nagłówkami.](./media/generic-types/generic-screwdriver-set.gif)  
  
 <span data-ttu-id="57d92-109">Podczas definiowania typu ogólnego należy Sparametryzuj go z co najmniej jednym typem danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-109">When you define a generic type, you parameterize it with one or more data types.</span></span> <span data-ttu-id="57d92-110">Pozwala to na użycie kodu do dopasowania typów danych do swoich wymagań.</span><span class="sxs-lookup"><span data-stu-id="57d92-110">This allows the using code to tailor the data types to its requirements.</span></span> <span data-ttu-id="57d92-111">Kod może zadeklarować kilka różnych elementów programistycznych z elementu ogólnego, każdy z nich działa na innym zestawie typów danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-111">Your code can declare several different programming elements from the generic element, each one acting on a different set of data types.</span></span> <span data-ttu-id="57d92-112">Jednak zadeklarowane elementy wszystkie wykonują identyczną logikę, niezależnie od tego, jakie typy danych są używane.</span><span class="sxs-lookup"><span data-stu-id="57d92-112">But the declared elements all perform the identical logic, no matter what data types they are using.</span></span>  
  
 <span data-ttu-id="57d92-113">Na przykład możesz chcieć utworzyć i użyć klasy kolejki, która działa na określonym typie danych, takim jak `String` .</span><span class="sxs-lookup"><span data-stu-id="57d92-113">For example, you might want to create and use a queue class that operates on a specific data type such as `String`.</span></span> <span data-ttu-id="57d92-114">Można zadeklarować takie klasy z <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="57d92-114">You can declare such a class from <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#1)]  
  
 <span data-ttu-id="57d92-115">Można teraz używać `stringQ` do pracy wyłącznie z `String` wartościami.</span><span class="sxs-lookup"><span data-stu-id="57d92-115">You can now use `stringQ` to work exclusively with `String` values.</span></span> <span data-ttu-id="57d92-116">Ponieważ `stringQ` jest specyficzny dla `String` , a nie uogólniony dla `Object` wartości, nie masz późnych powiązań ani konwersji typu.</span><span class="sxs-lookup"><span data-stu-id="57d92-116">Because `stringQ` is specific for `String` instead of being generalized for `Object` values, you do not have late binding or type conversion.</span></span> <span data-ttu-id="57d92-117">Pozwala to zaoszczędzić czas wykonywania i skraca błędy czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="57d92-117">This saves execution time and reduces run-time errors.</span></span>  
  
 <span data-ttu-id="57d92-118">Aby uzyskać więcej informacji na temat korzystania z typu ogólnego, zobacz [How to: use generyczn Class](how-to-use-a-generic-class.md).</span><span class="sxs-lookup"><span data-stu-id="57d92-118">For more information on using a generic type, see [How to: Use a Generic Class](how-to-use-a-generic-class.md).</span></span>  
  
## <a name="example-of-a-generic-class"></a><span data-ttu-id="57d92-119">Przykład klasy generycznej</span><span class="sxs-lookup"><span data-stu-id="57d92-119">Example of a Generic Class</span></span>  

 <span data-ttu-id="57d92-120">Poniższy przykład przedstawia definicję szkieletu klasy generycznej.</span><span class="sxs-lookup"><span data-stu-id="57d92-120">The following example shows a skeleton definition of a generic class.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#2)]  
  
 <span data-ttu-id="57d92-121">W poprzednim szkieletzie `t` jest *parametrem typu*, który jest symbolem zastępczym dla typu danych dostarczanym podczas deklarowania klasy.</span><span class="sxs-lookup"><span data-stu-id="57d92-121">In the preceding skeleton, `t` is a *type parameter*, that is, a placeholder for a data type that you supply when you declare the class.</span></span> <span data-ttu-id="57d92-122">W innym miejscu kodu można zadeklarować różne wersje programu, `classHolder` dostarczając różne typy danych dla `t` .</span><span class="sxs-lookup"><span data-stu-id="57d92-122">Elsewhere in your code, you can declare various versions of `classHolder` by supplying various data types for `t`.</span></span> <span data-ttu-id="57d92-123">Poniższy przykład pokazuje dwie takie deklaracje.</span><span class="sxs-lookup"><span data-stu-id="57d92-123">The following example shows two such declarations.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#3)]  
  
 <span data-ttu-id="57d92-124">Powyższe instrukcje deklarują *skonstruowane klasy*, w których określony typ zastępuje parametr typu.</span><span class="sxs-lookup"><span data-stu-id="57d92-124">The preceding statements declare *constructed classes*, in which a specific type replaces the type parameter.</span></span> <span data-ttu-id="57d92-125">Ten zamiennik jest propagowany w całym kodzie w ramach konstruowanej klasy.</span><span class="sxs-lookup"><span data-stu-id="57d92-125">This replacement is propagated throughout the code within the constructed class.</span></span> <span data-ttu-id="57d92-126">Poniższy przykład pokazuje, `processNewItem` jak wygląda ta procedura `integerClass` .</span><span class="sxs-lookup"><span data-stu-id="57d92-126">The following example shows what the `processNewItem` procedure looks like in `integerClass`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#4)]  
  
 <span data-ttu-id="57d92-127">Aby zapoznać się z bardziej kompletnym przykładem, zobacz [jak: Definiowanie klasy, która może zapewnić identyczną funkcjonalność dla różnych typów danych](how-to-define-a-class-that-can-provide-identical-functionality.md).</span><span class="sxs-lookup"><span data-stu-id="57d92-127">For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](how-to-define-a-class-that-can-provide-identical-functionality.md).</span></span>  
  
## <a name="eligible-programming-elements"></a><span data-ttu-id="57d92-128">Kwalifikujące się elementy programistyczne</span><span class="sxs-lookup"><span data-stu-id="57d92-128">Eligible Programming Elements</span></span>  

 <span data-ttu-id="57d92-129">Można definiować i używać klas ogólnych, struktur, interfejsów, procedur i delegatów.</span><span class="sxs-lookup"><span data-stu-id="57d92-129">You can define and use generic classes, structures, interfaces, procedures, and delegates.</span></span> <span data-ttu-id="57d92-130">Należy zauważyć, że .NET Framework definiuje kilka klas ogólnych, struktur i interfejsów, które reprezentują często używane elementy ogólne.</span><span class="sxs-lookup"><span data-stu-id="57d92-130">Note that the .NET Framework defines several generic classes, structures, and interfaces that represent commonly used generic elements.</span></span> <span data-ttu-id="57d92-131"><xref:System.Collections.Generic?displayProperty=nameWithType>Przestrzeń nazw zawiera słowniki, listy, kolejki i stosy.</span><span class="sxs-lookup"><span data-stu-id="57d92-131">The <xref:System.Collections.Generic?displayProperty=nameWithType> namespace provides dictionaries, lists, queues, and stacks.</span></span> <span data-ttu-id="57d92-132">Przed zdefiniowaniem własnego elementu generycznego, sprawdź, czy jest on już dostępny w programie <xref:System.Collections.Generic?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="57d92-132">Before defining your own generic element, see if it is already available in <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="57d92-133">Procedury nie są typami, ale można definiować i używać procedur ogólnych.</span><span class="sxs-lookup"><span data-stu-id="57d92-133">Procedures are not types, but you can define and use generic procedures.</span></span> <span data-ttu-id="57d92-134">Zapoznaj [się z procedurami ogólnymi w Visual Basic](generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="57d92-134">See [Generic Procedures in Visual Basic](generic-procedures.md).</span></span>  
  
## <a name="advantages-of-generic-types"></a><span data-ttu-id="57d92-135">Zalety typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="57d92-135">Advantages of Generic Types</span></span>  

 <span data-ttu-id="57d92-136">Typ ogólny służy jako podstawa do deklarowania kilku różnych elementów programistycznych, z których każdy działa na określonym typie danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-136">A generic type serves as a basis for declaring several different programming elements, each of which operates on a specific data type.</span></span> <span data-ttu-id="57d92-137">Alternatywy dla typu ogólnego są:</span><span class="sxs-lookup"><span data-stu-id="57d92-137">The alternatives to a generic type are:</span></span>  
  
1. <span data-ttu-id="57d92-138">Pojedynczy typ, który działa na `Object` typie danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-138">A single type operating on the `Object` data type.</span></span>  
  
2. <span data-ttu-id="57d92-139">Zestaw wersji typu *specyficznego dla typu* , każdej wersji osobno zakodowanej i działającej na jednym określonym typie danych, na przykład `String` , `Integer` lub typu zdefiniowanego przez użytkownika, takiego jak `customer` .</span><span class="sxs-lookup"><span data-stu-id="57d92-139">A set of *type-specific* versions of the type, each version individually coded and operating on one specific data type such as `String`, `Integer`, or a user-defined type such as `customer`.</span></span>  
  
 <span data-ttu-id="57d92-140">Typ ogólny ma następujące zalety w porównaniu z tymi alternatywami:</span><span class="sxs-lookup"><span data-stu-id="57d92-140">A generic type has the following advantages over these alternatives:</span></span>  
  
- <span data-ttu-id="57d92-141">**Bezpieczeństwo typu.**</span><span class="sxs-lookup"><span data-stu-id="57d92-141">**Type Safety.**</span></span> <span data-ttu-id="57d92-142">Typy ogólne wymuszają sprawdzanie typu w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="57d92-142">Generic types enforce compile-time type checking.</span></span> <span data-ttu-id="57d92-143">Typy na podstawie `Object` akceptowania dowolnego typu danych i należy napisać kod, aby sprawdzić, czy typ danych wejściowych jest akceptowalny.</span><span class="sxs-lookup"><span data-stu-id="57d92-143">Types based on `Object` accept any data type, and you must write code to check whether an input data type is acceptable.</span></span> <span data-ttu-id="57d92-144">W przypadku typów ogólnych kompilator może przechwytywać niezgodności typów przed uruchomieniem.</span><span class="sxs-lookup"><span data-stu-id="57d92-144">With generic types, the compiler can catch type mismatches before run time.</span></span>  
  
- <span data-ttu-id="57d92-145">**Skuteczności.**</span><span class="sxs-lookup"><span data-stu-id="57d92-145">**Performance.**</span></span> <span data-ttu-id="57d92-146">Typy ogólne nie mają *pola* i *Unbox* dane, ponieważ każdy z nich jest wyspecjalizowany dla jednego typu danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-146">Generic types do not have to *box* and *unbox* data, because each one is specialized for one data type.</span></span> <span data-ttu-id="57d92-147">Operacje oparte na `Object` typie danych wejściowej muszą mieć pole, aby przekonwertować je na `Object` i Unbox dane przeznaczone do danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="57d92-147">Operations based on `Object` must box input data types to convert them to `Object` and unbox data destined for output.</span></span> <span data-ttu-id="57d92-148">Wypakowywanie i rozpakowywanie zmniejszanie wydajności.</span><span class="sxs-lookup"><span data-stu-id="57d92-148">Boxing and unboxing reduce performance.</span></span>  
  
     <span data-ttu-id="57d92-149">Typy oparte na programie `Object` są również opóźnione, co oznacza, że dostęp do swoich elementów członkowskich wymaga dodatkowego kodu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="57d92-149">Types based on `Object` are also late-bound, which means that accessing their members requires extra code at run time.</span></span> <span data-ttu-id="57d92-150">Zmniejsza to również wydajność.</span><span class="sxs-lookup"><span data-stu-id="57d92-150">This also reduces performance.</span></span>  
  
- <span data-ttu-id="57d92-151">**Konsolidacja kodu.**</span><span class="sxs-lookup"><span data-stu-id="57d92-151">**Code Consolidation.**</span></span> <span data-ttu-id="57d92-152">Kod w typie ogólnym musi być zdefiniowany tylko raz.</span><span class="sxs-lookup"><span data-stu-id="57d92-152">The code in a generic type has to be defined only once.</span></span> <span data-ttu-id="57d92-153">Zestaw wersji typu specyficznego dla typu musi replikować ten sam kod w każdej wersji, z jedyną różnicą charakterystyczną dla konkretnego typu danych dla tej wersji.</span><span class="sxs-lookup"><span data-stu-id="57d92-153">A set of type-specific versions of a type must replicate the same code in each version, with the only difference being the specific data type for that version.</span></span> <span data-ttu-id="57d92-154">W przypadku typów ogólnych wersje specyficzne dla typu są generowane na podstawie oryginalnego typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="57d92-154">With generic types, the type-specific versions are all generated from the original generic type.</span></span>  
  
- <span data-ttu-id="57d92-155">**Ponowne użycie kodu.**</span><span class="sxs-lookup"><span data-stu-id="57d92-155">**Code Reuse.**</span></span> <span data-ttu-id="57d92-156">Kod, który nie zależy od określonego typu danych, może być ponownie używany z różnymi typami danych, jeśli jest ogólny.</span><span class="sxs-lookup"><span data-stu-id="57d92-156">Code that does not depend on a particular data type can be reused with various data types if it is generic.</span></span> <span data-ttu-id="57d92-157">Często można ponownie użyć tego elementu nawet z typem danych, który nie został pierwotnie przewidywalny.</span><span class="sxs-lookup"><span data-stu-id="57d92-157">You can often reuse it even with a data type that you did not originally predict.</span></span>  
  
- <span data-ttu-id="57d92-158">**Obsługa środowiska IDE.**</span><span class="sxs-lookup"><span data-stu-id="57d92-158">**IDE Support.**</span></span> <span data-ttu-id="57d92-159">Jeśli używasz złożonego typu zadeklarowanego z typu ogólnego, zintegrowane środowisko programistyczne (IDE) może zapewnić lepszą obsługę podczas tworzenia kodu.</span><span class="sxs-lookup"><span data-stu-id="57d92-159">When you use a constructed type declared from a generic type, the integrated development environment (IDE) can give you more support while you are developing your code.</span></span> <span data-ttu-id="57d92-160">Na przykład technologia IntelliSense może wyświetlić opcje specyficzne dla danego typu dla argumentu w konstruktorze lub metodzie.</span><span class="sxs-lookup"><span data-stu-id="57d92-160">For example, IntelliSense can show you the type-specific options for an argument to a constructor or method.</span></span>  
  
- <span data-ttu-id="57d92-161">**Algorytmy ogólne.**</span><span class="sxs-lookup"><span data-stu-id="57d92-161">**Generic Algorithms.**</span></span> <span data-ttu-id="57d92-162">Abstrakcyjne algorytmy, które są niezależne od typu, są dobrymi kandydatami dla typów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="57d92-162">Abstract algorithms that are type-independent are good candidates for generic types.</span></span> <span data-ttu-id="57d92-163">Na przykład ogólna procedura, która sortuje elementy przy użyciu <xref:System.IComparable> interfejsu, może być używana z dowolnym typem danych, który implementuje <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="57d92-163">For example, a generic procedure that sorts items using the <xref:System.IComparable> interface can be used with any data type that implements <xref:System.IComparable>.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="57d92-164">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="57d92-164">Constraints</span></span>  

 <span data-ttu-id="57d92-165">Chociaż kod w definicji typu ogólnego powinien być niezależny od typu, konieczne może być wymaganie pewnej możliwości dowolnego typu danych dostarczonego do typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="57d92-165">Although the code in a generic type definition should be as type-independent as possible, you might need to require a certain capability of any data type supplied to your generic type.</span></span> <span data-ttu-id="57d92-166">Na przykład jeśli chcesz porównać dwa elementy na potrzeby sortowania lub sortowania, ich typ danych musi implementować <xref:System.IComparable> interfejs.</span><span class="sxs-lookup"><span data-stu-id="57d92-166">For example, if you want to compare two items for the purpose of sorting or collating, their data type must implement the <xref:System.IComparable> interface.</span></span> <span data-ttu-id="57d92-167">To wymaganie można wymusić, dodając *ograniczenie* do parametru typu.</span><span class="sxs-lookup"><span data-stu-id="57d92-167">You can enforce this requirement by adding a *constraint* to the type parameter.</span></span>  
  
### <a name="example-of-a-constraint"></a><span data-ttu-id="57d92-168">Przykład ograniczenia</span><span class="sxs-lookup"><span data-stu-id="57d92-168">Example of a Constraint</span></span>  

 <span data-ttu-id="57d92-169">Poniższy przykład przedstawia definicję szkieletu klasy z ograniczeniami wymagającymi argumentu typu do zaimplementowania <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="57d92-169">The following example shows a skeleton definition of a class with a constraint that requires the type argument to implement <xref:System.IComparable>.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#5)]  
  
 <span data-ttu-id="57d92-170">Jeśli kolejny kod próbuje utworzyć klasę z `itemManager` dostarczania typu, który nie implementuje <xref:System.IComparable> , kompilator sygnalizuje błąd.</span><span class="sxs-lookup"><span data-stu-id="57d92-170">If subsequent code attempts to construct a class from `itemManager` supplying a type that does not implement <xref:System.IComparable>, the compiler signals an error.</span></span>  
  
### <a name="types-of-constraints"></a><span data-ttu-id="57d92-171">Typy ograniczeń</span><span class="sxs-lookup"><span data-stu-id="57d92-171">Types of Constraints</span></span>  

 <span data-ttu-id="57d92-172">Ograniczenie może określać następujące wymagania w dowolnej kombinacji:</span><span class="sxs-lookup"><span data-stu-id="57d92-172">Your constraint can specify the following requirements in any combination:</span></span>  
  
- <span data-ttu-id="57d92-173">Argument typu musi implementować jeden lub więcej interfejsów</span><span class="sxs-lookup"><span data-stu-id="57d92-173">The type argument must implement one or more interfaces</span></span>  
  
- <span data-ttu-id="57d92-174">Argument typu musi być typu lub dziedziczyć po, co najwyżej jedną klasę</span><span class="sxs-lookup"><span data-stu-id="57d92-174">The type argument must be of the type of, or inherit from, at most one class</span></span>  
  
- <span data-ttu-id="57d92-175">Argument typu musi ujawniać konstruktora bez parametrów dostępnego dla kodu, który tworzy obiekty z niego</span><span class="sxs-lookup"><span data-stu-id="57d92-175">The type argument must expose a parameterless constructor accessible to the code that creates objects from it</span></span>  
  
- <span data-ttu-id="57d92-176">Argument typu musi być *typem referencyjnym*lub musi być *typem wartości*</span><span class="sxs-lookup"><span data-stu-id="57d92-176">The type argument must be a *reference type*, or it must be a *value type*</span></span>  
  
 <span data-ttu-id="57d92-177">Jeśli konieczne jest nakładanie więcej niż jednego wymagania, należy użyć *listy ograniczeń* rozdzielanych przecinkami ( `{ }` ).</span><span class="sxs-lookup"><span data-stu-id="57d92-177">If you need to impose more than one requirement, you use a comma-separated *constraint list* inside braces (`{ }`).</span></span> <span data-ttu-id="57d92-178">Aby wymagać konstruktora dostępnego, na liście należy umieścić słowo kluczowe [New Operator](../../../language-reference/operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="57d92-178">To require an accessible constructor, you include the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the list.</span></span> <span data-ttu-id="57d92-179">Aby wymagać typu referencyjnego, należy dołączyć `Class` słowo kluczowe; aby wymagać typu wartości, należy dołączyć `Structure` słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="57d92-179">To require a reference type, you include the `Class` keyword; to require a value type, you include the `Structure` keyword.</span></span>  
  
 <span data-ttu-id="57d92-180">Aby uzyskać więcej informacji o ograniczeniach, zobacz [Type list](../../../language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="57d92-180">For more information on constraints, see [Type List](../../../language-reference/statements/type-list.md).</span></span>  
  
### <a name="example-of-multiple-constraints"></a><span data-ttu-id="57d92-181">Przykład wielu ograniczeń</span><span class="sxs-lookup"><span data-stu-id="57d92-181">Example of Multiple Constraints</span></span>  

 <span data-ttu-id="57d92-182">Poniższy przykład przedstawia definicję szkieletu klasy generycznej z listą ograniczeń w parametrze typu.</span><span class="sxs-lookup"><span data-stu-id="57d92-182">The following example shows a skeleton definition of a generic class with a constraint list on the type parameter.</span></span> <span data-ttu-id="57d92-183">W kodzie, który tworzy wystąpienie tej klasy, argument typu musi implementować zarówno <xref:System.IComparable> interfejsy, jak i <xref:System.IDisposable> , być typem referencyjnym i uwidaczniać dostępny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="57d92-183">In the code that creates an instance of this class, the type argument must implement both the <xref:System.IComparable> and <xref:System.IDisposable> interfaces, be a reference type, and expose an accessible parameterless constructor.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#6)]  
  
## <a name="important-terms"></a><span data-ttu-id="57d92-184">Ważne warunki</span><span class="sxs-lookup"><span data-stu-id="57d92-184">Important Terms</span></span>  

 <span data-ttu-id="57d92-185">Typy ogólne wprowadzają i korzystają z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="57d92-185">Generic types introduce and use the following terms:</span></span>  
  
- <span data-ttu-id="57d92-186">*Typ ogólny*.</span><span class="sxs-lookup"><span data-stu-id="57d92-186">*Generic Type*.</span></span> <span data-ttu-id="57d92-187">Definicja klasy, struktury, interfejsu, procedury lub delegata, dla którego podczas deklarowania należy podać co najmniej jeden typ danych.</span><span class="sxs-lookup"><span data-stu-id="57d92-187">A definition of a class, structure, interface, procedure, or delegate for which you supply at least one data type when you declare it.</span></span>  
  
- <span data-ttu-id="57d92-188">*Parametr typu*.</span><span class="sxs-lookup"><span data-stu-id="57d92-188">*Type Parameter*.</span></span> <span data-ttu-id="57d92-189">W definicji typu ogólnego, symbol zastępczy dla typu danych dostarczanego podczas deklarowania typu.</span><span class="sxs-lookup"><span data-stu-id="57d92-189">In a generic type definition, a placeholder for a data type you supply when you declare the type.</span></span>  
  
- <span data-ttu-id="57d92-190">*Typ argumentu*.</span><span class="sxs-lookup"><span data-stu-id="57d92-190">*Type Argument*.</span></span> <span data-ttu-id="57d92-191">Określony typ danych, który zastępuje parametr typu w przypadku deklarowania konstruowanego typu z typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="57d92-191">A specific data type that replaces a type parameter when you declare a constructed type from a generic type.</span></span>  
  
- <span data-ttu-id="57d92-192">*Ograniczenie*.</span><span class="sxs-lookup"><span data-stu-id="57d92-192">*Constraint*.</span></span> <span data-ttu-id="57d92-193">Warunek w parametrze typu, który ogranicza typ argumentu, który można dla niego podać.</span><span class="sxs-lookup"><span data-stu-id="57d92-193">A condition on a type parameter that restricts the type argument you can supply for it.</span></span> <span data-ttu-id="57d92-194">Ograniczenie może wymagać, aby argument typu musi implementować określony interfejs, być lub dziedziczyć z określonej klasy, mieć dostępny Konstruktor bez parametrów lub być typem referencyjnym lub typem wartości.</span><span class="sxs-lookup"><span data-stu-id="57d92-194">A constraint can require that the type argument must implement a particular interface, be or inherit from a particular class, have an accessible parameterless constructor, or be a reference type or a value type.</span></span> <span data-ttu-id="57d92-195">Można połączyć te ograniczenia, ale można określić co najwyżej jedną klasę.</span><span class="sxs-lookup"><span data-stu-id="57d92-195">You can combine these constraints, but you can specify at most one class.</span></span>  
  
- <span data-ttu-id="57d92-196">*Typ skonstruowany*.</span><span class="sxs-lookup"><span data-stu-id="57d92-196">*Constructed Type*.</span></span> <span data-ttu-id="57d92-197">Klasa, struktura, interfejs, procedura lub delegat zadeklarowany z typu ogólnego przez dostarczenie argumentów typu dla parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="57d92-197">A class, structure, interface, procedure, or delegate declared from a generic type by supplying type arguments for its type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d92-198">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="57d92-198">See also</span></span>

- [<span data-ttu-id="57d92-199">Typy danych</span><span class="sxs-lookup"><span data-stu-id="57d92-199">Data Types</span></span>](index.md)
- [<span data-ttu-id="57d92-200">Znaki typu</span><span class="sxs-lookup"><span data-stu-id="57d92-200">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="57d92-201">Typy wartości i odwołań</span><span class="sxs-lookup"><span data-stu-id="57d92-201">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="57d92-202">Konwersje plików w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57d92-202">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="57d92-203">Rozwiązywanie problemów związanych z typami danych</span><span class="sxs-lookup"><span data-stu-id="57d92-203">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="57d92-204">Typy danych</span><span class="sxs-lookup"><span data-stu-id="57d92-204">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="57d92-205">Z</span><span class="sxs-lookup"><span data-stu-id="57d92-205">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="57d92-206">Definicj</span><span class="sxs-lookup"><span data-stu-id="57d92-206">As</span></span>](../../../language-reference/statements/as-clause.md)
- [<span data-ttu-id="57d92-207">Object — typ danych</span><span class="sxs-lookup"><span data-stu-id="57d92-207">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="57d92-208">Kowariancja i kontrawariancja</span><span class="sxs-lookup"><span data-stu-id="57d92-208">Covariance and Contravariance</span></span>](../../concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="57d92-209">Iteratory</span><span class="sxs-lookup"><span data-stu-id="57d92-209">Iterators</span></span>](../../concepts/iterators.md)
