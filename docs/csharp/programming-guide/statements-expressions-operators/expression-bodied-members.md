---
title: Elementy członkowskie w postaci wyrażeń — Przewodnik programowania w języku C#
description: Dowiedz się więcej o elementach składowych wyrażeń. Zobacz przykłady kodu, które używają definicji treści wyrażenia dla właściwości, konstruktorów, finalizatorów i innych.
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: e68e96e4aa3ff6a64590459a7197da1833e1a275
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381661"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="7569b-104">Elementy członkowskie z wyrażeniami (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="7569b-104">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="7569b-105">Definicje treści wyrażenia pozwalają zapewnić implementację elementu członkowskiego w bardzo zwięzłej, czytelnej postaci.</span><span class="sxs-lookup"><span data-stu-id="7569b-105">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="7569b-106">Można użyć definicji treści wyrażenia za każdym razem, gdy logika dowolnego obsługiwanego elementu członkowskiego, takiego jak metoda lub właściwość, składa się z jednego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7569b-106">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="7569b-107">Definicja treści wyrażenia ma następującą składnię ogólną:</span><span class="sxs-lookup"><span data-stu-id="7569b-107">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="7569b-108">*wyrażenie* WHERE jest prawidłowym wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="7569b-108">where *expression* is a valid expression.</span></span>

<span data-ttu-id="7569b-109">Obsługa definicji treści wyrażenia została wprowadzona dla metod i właściwości tylko do odczytu w języku C# 6 i została rozwinięta w języku C# 7,0.</span><span class="sxs-lookup"><span data-stu-id="7569b-109">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="7569b-110">Definicje treści wyrażenia mogą być używane z elementami członkowskimi typu wymienionymi w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="7569b-110">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="7569b-111">Członek</span><span class="sxs-lookup"><span data-stu-id="7569b-111">Member</span></span>  |<span data-ttu-id="7569b-112">Obsługiwane przez...</span><span class="sxs-lookup"><span data-stu-id="7569b-112">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="7569b-113">Metoda</span><span class="sxs-lookup"><span data-stu-id="7569b-113">Method</span></span>](#methods)  |<span data-ttu-id="7569b-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="7569b-114">C# 6</span></span> |
|[<span data-ttu-id="7569b-115">Właściwość tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7569b-115">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="7569b-116">C# 6</span><span class="sxs-lookup"><span data-stu-id="7569b-116">C# 6</span></span>  |
|[<span data-ttu-id="7569b-117">Właściwość</span><span class="sxs-lookup"><span data-stu-id="7569b-117">Property</span></span>](#properties)  |<span data-ttu-id="7569b-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="7569b-118">C# 7.0</span></span> |
|[<span data-ttu-id="7569b-119">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="7569b-119">Constructor</span></span>](#constructors)   |<span data-ttu-id="7569b-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="7569b-120">C# 7.0</span></span> |
|[<span data-ttu-id="7569b-121">Finalizator</span><span class="sxs-lookup"><span data-stu-id="7569b-121">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="7569b-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="7569b-122">C# 7.0</span></span> |
|[<span data-ttu-id="7569b-123">Indeksator</span><span class="sxs-lookup"><span data-stu-id="7569b-123">Indexer</span></span>](#indexers)       |<span data-ttu-id="7569b-124">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="7569b-124">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="7569b-125">Metody</span><span class="sxs-lookup"><span data-stu-id="7569b-125">Methods</span></span>

<span data-ttu-id="7569b-126">Metoda zabudowana wyrażenia składa się z pojedynczego wyrażenia, które zwraca wartość, której typ pasuje do typu zwracanego metody lub dla metod zwracających `void` , które wykonują pewne operacje.</span><span class="sxs-lookup"><span data-stu-id="7569b-126">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="7569b-127">Na przykład typy, które zastępują <xref:System.Object.ToString%2A> metodę, zazwyczaj obejmują pojedyncze wyrażenie, które zwraca reprezentację ciągu bieżącego obiektu.</span><span class="sxs-lookup"><span data-stu-id="7569b-127">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="7569b-128">W poniższym przykładzie zdefiniowano `Person` klasę, która zastępuje <xref:System.Object.ToString%2A> metodę z definicją treści wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7569b-128">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="7569b-129">Definiuje także `DisplayName` metodę, która wyświetla nazwę konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="7569b-129">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="7569b-130">Należy zauważyć, że `return` słowo kluczowe nie jest używane w `ToString` definicji treści wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7569b-130">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="7569b-131">Aby uzyskać więcej informacji, zobacz [metody (Przewodnik programowania w języku C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="7569b-131">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="7569b-132">Właściwości tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7569b-132">Read-only properties</span></span>

<span data-ttu-id="7569b-133">Począwszy od języka C# 6, można użyć definicji treści wyrażenia, aby zaimplementować właściwość tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="7569b-133">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="7569b-134">W tym celu należy użyć następującej składni:</span><span class="sxs-lookup"><span data-stu-id="7569b-134">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="7569b-135">W poniższym przykładzie zdefiniowano `Location` klasę, której właściwość tylko do odczytu `Name` jest zaimplementowana jako definicja treści wyrażenia, która zwraca wartość `locationName` pola prywatnego:</span><span class="sxs-lookup"><span data-stu-id="7569b-135">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="7569b-136">Aby uzyskać więcej informacji na temat właściwości, zobacz [właściwości (Przewodnik programowania w języku C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="7569b-136">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="7569b-137">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7569b-137">Properties</span></span>

<span data-ttu-id="7569b-138">Począwszy od języka C# 7,0, można użyć definicji treści wyrażenia do implementowania właściwości `get` i `set` metod dostępu.</span><span class="sxs-lookup"><span data-stu-id="7569b-138">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="7569b-139">Poniższy przykład ilustruje, jak to zrobić:</span><span class="sxs-lookup"><span data-stu-id="7569b-139">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="7569b-140">Aby uzyskać więcej informacji na temat właściwości, zobacz [właściwości (Przewodnik programowania w języku C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="7569b-140">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="7569b-141">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="7569b-141">Constructors</span></span>

<span data-ttu-id="7569b-142">Definicja treści wyrażenia dla konstruktora zwykle składa się z pojedynczego wyrażenia przypisania lub wywołania metody, które obsługuje argumenty konstruktora lub inicjuje stan wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="7569b-142">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="7569b-143">W poniższym przykładzie zdefiniowano `Location` klasę, której Konstruktor ma jeden parametr ciągu o nazwie *name*.</span><span class="sxs-lookup"><span data-stu-id="7569b-143">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="7569b-144">Definicja treści wyrażenia przypisuje argument do `Name` właściwości.</span><span class="sxs-lookup"><span data-stu-id="7569b-144">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="7569b-145">Aby uzyskać więcej informacji, zobacz [konstruktory (Przewodnik programowania w języku C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7569b-145">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="7569b-146">Finalizatory</span><span class="sxs-lookup"><span data-stu-id="7569b-146">Finalizers</span></span>

<span data-ttu-id="7569b-147">Definicja treści wyrażenia dla finalizatora zwykle zawiera instrukcje czyszczenia, takie jak instrukcje zwalniania niezarządzanych zasobów.</span><span class="sxs-lookup"><span data-stu-id="7569b-147">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="7569b-148">W poniższym przykładzie zdefiniowano finalizator, który używa definicji treści wyrażenia, aby wskazać, że finalizator został wywołany.</span><span class="sxs-lookup"><span data-stu-id="7569b-148">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="7569b-149">Aby uzyskać więcej informacji, zobacz [finalizatory (Przewodnik programowania w języku C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="7569b-149">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="7569b-150">Indexers (Indeksatory)</span><span class="sxs-lookup"><span data-stu-id="7569b-150">Indexers</span></span>

<span data-ttu-id="7569b-151">Podobnie jak w przypadku właściwości, indeksator i Akcesory `get` `set` składają się z definicji treści wyrażenia, jeśli `get` metoda dostępu składa się z jednego wyrażenia, które zwraca wartość lub `set` metoda dostępu wykonuje proste przypisanie.</span><span class="sxs-lookup"><span data-stu-id="7569b-151">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="7569b-152">W poniższym przykładzie zdefiniowano klasę o nazwie `Sports` , która zawiera <xref:System.String> tablicę wewnętrzną, która zawiera nazwy wielu sportowych.</span><span class="sxs-lookup"><span data-stu-id="7569b-152">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="7569b-153">Zarówno indeksator `get` , jak i metody `set` dostępu są zaimplementowane jako definicje treści wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7569b-153">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="7569b-154">Aby uzyskać więcej informacji, zobacz [indeksatory (Przewodnik programowania w języku C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="7569b-154">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
