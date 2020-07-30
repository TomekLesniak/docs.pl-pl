---
title: Interfejsy ogólne — Przewodnik programowania w języku C#
description: Dowiedz się więcej o używaniu interfejsów ogólnych w języku C#. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 43817a236e95b3ab8fd0ba94da98457eeec2396c
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301895"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="13c3f-104">Interfejsy ogólne (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="13c3f-104">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="13c3f-105">Często warto zdefiniować interfejsy dla klas kolekcji generycznej lub dla klas ogólnych, które reprezentują elementy w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="13c3f-105">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="13c3f-106">Preferencją dla klas ogólnych jest użycie interfejsów ogólnych, takich jak <xref:System.IComparable%601> zamiast <xref:System.IComparable> , aby uniknąć pakowania i rozpakowywania operacji na typach wartości.</span><span class="sxs-lookup"><span data-stu-id="13c3f-106">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="13c3f-107">Biblioteka klas .NET Framework definiuje kilka ogólnych interfejsów do użycia z klasami kolekcji w <xref:System.Collections.Generic> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="13c3f-107">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="13c3f-108">Gdy interfejs jest określony jako ograniczenie dla parametru typu, można użyć tylko typów, które implementują interfejs.</span><span class="sxs-lookup"><span data-stu-id="13c3f-108">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="13c3f-109">Poniższy przykład kodu pokazuje `SortedList<T>` klasę, która dziedziczy z `GenericList<T>` klasy.</span><span class="sxs-lookup"><span data-stu-id="13c3f-109">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="13c3f-110">Aby uzyskać więcej informacji, zobacz [wprowadzenie do typów ogólnych](./index.md).</span><span class="sxs-lookup"><span data-stu-id="13c3f-110">For more information, see [Introduction to Generics](./index.md).</span></span> <span data-ttu-id="13c3f-111">`SortedList<T>`dodaje ograniczenie `where T : IComparable<T>` .</span><span class="sxs-lookup"><span data-stu-id="13c3f-111">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="13c3f-112">Dzięki temu `BubbleSort` Metoda w programie `SortedList<T>` może używać metody ogólnej <xref:System.IComparable%601.CompareTo%2A> dla elementów listy.</span><span class="sxs-lookup"><span data-stu-id="13c3f-112">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="13c3f-113">W tym przykładzie elementy list są prostą klasą, `Person` która implementuje `IComparable<Person>` .</span><span class="sxs-lookup"><span data-stu-id="13c3f-113">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="13c3f-114">Można określić wiele interfejsów jako ograniczenia dotyczące pojedynczego typu w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="13c3f-114">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="13c3f-115">Interfejs może definiować więcej niż jeden parametr typu w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="13c3f-115">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="13c3f-116">Reguły dziedziczenia stosowane do klas dotyczą również interfejsów:</span><span class="sxs-lookup"><span data-stu-id="13c3f-116">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="13c3f-117">Interfejsy generyczne mogą dziedziczyć z interfejsów innych niż ogólne, jeśli interfejs generyczny jest kontrawariantne, co oznacza, że używa jego parametru typu jako wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="13c3f-117">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="13c3f-118">W bibliotece klas .NET Framework <xref:System.Collections.Generic.IEnumerable%601> dziedziczy z, <xref:System.Collections.IEnumerable> ponieważ <xref:System.Collections.Generic.IEnumerable%601> używa tylko `T` w wartości zwracanej i w metodzie <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> <xref:System.Collections.Generic.IEnumerator%601.Current%2A> pobierającej właściwości.</span><span class="sxs-lookup"><span data-stu-id="13c3f-118">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="13c3f-119">Konkretne klasy mogą zaimplementować zamknięte interfejsy skonstruowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="13c3f-119">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="13c3f-120">Klasy generyczne mogą implementować interfejsy ogólne lub zamknięte skonstruowane interfejsy, o ile lista parametrów klasy dostarcza wszystkie argumenty wymagane przez interfejs, w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="13c3f-120">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="13c3f-121">Reguły przeciążania metody kontrolującej są takie same dla metod w klasach ogólnych, strukturach ogólnych lub w interfejsach ogólnych.</span><span class="sxs-lookup"><span data-stu-id="13c3f-121">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="13c3f-122">Aby uzyskać więcej informacji, zobacz [metody ogólne](./generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="13c3f-122">For more information, see [Generic Methods](./generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c3f-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="13c3f-123">See also</span></span>

- [<span data-ttu-id="13c3f-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="13c3f-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="13c3f-125">Wprowadzenie do typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="13c3f-125">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="13c3f-126">interfejsu</span><span class="sxs-lookup"><span data-stu-id="13c3f-126">interface</span></span>](../../language-reference/keywords/interface.md)
- [<span data-ttu-id="13c3f-127">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="13c3f-127">Generics</span></span>](../../../standard/generics/index.md)
