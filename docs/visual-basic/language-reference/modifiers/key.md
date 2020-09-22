---
title: Klucz
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 582ed5bb67b9c7504e736710aa4649cffb12ef45
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867995"
---
# <a name="key-visual-basic"></a><span data-ttu-id="ff2fc-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff2fc-102">Key (Visual Basic)</span></span>

<span data-ttu-id="ff2fc-103">`Key`Słowo kluczowe umożliwia określenie zachowania właściwości typów anonimowych.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="ff2fc-104">Tylko właściwości, które należy wyznaczyć jako właściwości klucza, uczestniczą w testach równości między wystąpieniami typu anonimowego lub obliczeń wartości kodów skrótu.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="ff2fc-105">Nie można zmienić wartości właściwości klucza.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="ff2fc-106">Właściwość typu anonimowego należy wyznaczyć jako właściwość klucza poprzez umieszczenie słowa kluczowego `Key` przed deklaracją na liście inicjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="ff2fc-107">W poniższym przykładzie `Airline` i `FlightNo` są właściwościami klucza, ale `Gate` nie jest.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="ff2fc-108">Po utworzeniu nowego typu anonimowego dziedziczy on bezpośrednio z <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="ff2fc-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="ff2fc-109">Kompilator przesłania trzy dziedziczone elementy członkowskie: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> , i <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="ff2fc-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="ff2fc-110">Kod przesłonięcia, który jest tworzony dla <xref:System.Object.Equals%2A> i <xref:System.Object.GetHashCode%2A> jest oparty na właściwościach klucza.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="ff2fc-111">Jeśli w typie nie ma właściwości klucza <xref:System.Object.GetHashCode%2A> i <xref:System.Object.Equals%2A> nie są one zastępowane.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="ff2fc-112">Równość</span><span class="sxs-lookup"><span data-stu-id="ff2fc-112">Equality</span></span>  

 <span data-ttu-id="ff2fc-113">Dwa wystąpienia typu anonimowego są równe, jeśli są wystąpieniami tego samego typu, a wartości ich właściwości klucza są równe.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="ff2fc-114">W poniższych przykładach `flight2` jest równe `flight1` z poprzedniego przykładu, ponieważ są wystąpieniami tego samego typu anonimowego i mają pasujące wartości właściwości klucza.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="ff2fc-115">Jednak `flight3` nie jest równe, `flight1` ponieważ ma inną wartość właściwości klucza `FlightNo` .</span><span class="sxs-lookup"><span data-stu-id="ff2fc-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="ff2fc-116">Wystąpienie `flight4` nie jest tego samego typu, `flight1` ponieważ wyznaczy różne właściwości jako właściwości klucza.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="ff2fc-117">Jeśli dwa wystąpienia są zadeklarowane tylko z właściwościami niebędącymi kluczowymi, takimi jak nazwa, typ, kolejność i wartość, dwa wystąpienia nie są równe.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="ff2fc-118">Wystąpienie bez właściwości klucza jest równe tylko dla siebie.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="ff2fc-119">Aby uzyskać więcej informacji na temat warunków, w których dwa wystąpienia typu anonimowego są wystąpieniami tego samego typu anonimowego, zobacz [Typy anonimowe](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ff2fc-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="ff2fc-120">Obliczanie kodu skrótu</span><span class="sxs-lookup"><span data-stu-id="ff2fc-120">Hash Code Calculation</span></span>  

 <span data-ttu-id="ff2fc-121">Podobnie jak <xref:System.Object.Equals%2A> Funkcja skrótu zdefiniowana w <xref:System.Object.GetHashCode%2A> dla typu anonimowego jest oparta na właściwościach klucza typu.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="ff2fc-122">W poniższych przykładach przedstawiono interakcje między właściwościami klucza i wartościami kodu skrótu.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="ff2fc-123">Wystąpienia typu anonimowego, które mają takie same wartości dla wszystkich właściwości klucza mają tę samą wartość kodu skrótu, nawet jeśli właściwości nieklucza nie mają pasujących wartości.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="ff2fc-124">Poniższa instrukcja zwraca wartość `True` .</span><span class="sxs-lookup"><span data-stu-id="ff2fc-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="ff2fc-125">Wystąpienia typu anonimowego, które mają różne wartości dla co najmniej jednej właściwości klucza mają różne wartości kodu skrótu.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="ff2fc-126">Poniższa instrukcja zwraca wartość `False` .</span><span class="sxs-lookup"><span data-stu-id="ff2fc-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="ff2fc-127">Wystąpienia typów anonimowych, które wyznaczają różne właściwości jako właściwości klucza, nie są wystąpieniami tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="ff2fc-128">Mają różne wartości kodu skrótu, nawet gdy nazwy i wartości wszystkich właściwości są takie same.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="ff2fc-129">Poniższa instrukcja zwraca wartość `False` .</span><span class="sxs-lookup"><span data-stu-id="ff2fc-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="ff2fc-130">Wartości tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ff2fc-130">Read-Only Values</span></span>  

 <span data-ttu-id="ff2fc-131">Nie można zmienić wartości właściwości klucza.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="ff2fc-132">Na przykład w `flight1` poprzednich przykładach `Airline` i `FlightNo` pola są tylko do odczytu, ale `Gate` można je zmienić.</span><span class="sxs-lookup"><span data-stu-id="ff2fc-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="ff2fc-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff2fc-133">See also</span></span>

- [<span data-ttu-id="ff2fc-134">Definicja typu anonimowego</span><span class="sxs-lookup"><span data-stu-id="ff2fc-134">Anonymous Type Definition</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="ff2fc-135">Instrukcje: wnioskowanie nazw właściwości i typów w deklaracjach typu anonimowego</span><span class="sxs-lookup"><span data-stu-id="ff2fc-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="ff2fc-136">Typy anonimowe</span><span class="sxs-lookup"><span data-stu-id="ff2fc-136">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
