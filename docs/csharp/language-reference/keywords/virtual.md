---
description: Dokumentacja wirtualnego języka C#
title: Dokumentacja wirtualnego języka C#
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 67bdfcf27bb108ca85e94ba7fdce208e4cd83b80
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141728"
---
# <a name="virtual-c-reference"></a><span data-ttu-id="716b9-103">virtual (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="716b9-103">virtual (C# Reference)</span></span>

<span data-ttu-id="716b9-104">`virtual`Słowo kluczowe jest używane do modyfikacji deklaracji metody, właściwości, indeksatora lub zdarzenia i umożliwia jej zastąpienie w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="716b9-104">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="716b9-105">Na przykład ta metoda może zostać przesłonięta przez dowolną klasę, która ją dziedziczy:</span><span class="sxs-lookup"><span data-stu-id="716b9-105">For example, this method can be overridden by any class that inherits it:</span></span>

```csharp
public virtual double Area()
{
    return x * y;
}
```

<span data-ttu-id="716b9-106">Implementację wirtualnego elementu członkowskiego można zmienić przez [zastępujący element członkowski](override.md) w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="716b9-106">The implementation of a virtual member can be changed by an [overriding member](override.md) in a derived class.</span></span> <span data-ttu-id="716b9-107">Aby uzyskać więcej informacji na temat sposobu używania `virtual` słowa kluczowego, zobacz [przechowywanie wersji z przesłonięciami i nowymi słowami kluczowymi](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) i [wiedzą, kiedy używać przesłonięć i nowych słów kluczowych](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="716b9-107">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="716b9-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="716b9-108">Remarks</span></span>

<span data-ttu-id="716b9-109">Gdy wywoływana jest metoda wirtualna, typ czasu wykonywania obiektu jest sprawdzany dla elementu członkowskiego, który jest zastępujący.</span><span class="sxs-lookup"><span data-stu-id="716b9-109">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="716b9-110">Nadrzędny element członkowski w najbardziej pochodnej klasie jest wywoływany, który może być pierwotną składową, jeśli żadna Klasa pochodna nie przesłoni elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="716b9-110">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>

<span data-ttu-id="716b9-111">Domyślnie metody nie są wirtualne.</span><span class="sxs-lookup"><span data-stu-id="716b9-111">By default, methods are non-virtual.</span></span> <span data-ttu-id="716b9-112">Nie można zastąpić metody innej niż wirtualna.</span><span class="sxs-lookup"><span data-stu-id="716b9-112">You cannot override a non-virtual method.</span></span>

<span data-ttu-id="716b9-113">Nie można użyć `virtual` modyfikatora z `static` `abstract` `private` modyfikatorami,,, lub `override` .</span><span class="sxs-lookup"><span data-stu-id="716b9-113">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="716b9-114">W poniższym przykładzie przedstawiono Właściwość wirtualną:</span><span class="sxs-lookup"><span data-stu-id="716b9-114">The following example shows a virtual property:</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="716b9-115">Właściwości wirtualne zachowują się jak metody wirtualne, z wyjątkiem różnic w składni deklaracji i wywołania.</span><span class="sxs-lookup"><span data-stu-id="716b9-115">Virtual properties behave like virtual methods, except for the differences in declaration and invocation syntax.</span></span>

- <span data-ttu-id="716b9-116">Wystąpił błąd podczas używania `virtual` modyfikatora dla właściwości statycznej.</span><span class="sxs-lookup"><span data-stu-id="716b9-116">It is an error to use the `virtual` modifier on a static property.</span></span>

- <span data-ttu-id="716b9-117">Wirtualną Właściwość dziedziczoną można zastąpić w klasie pochodnej przez dołączenie deklaracji właściwości, która używa `override` modyfikatora.</span><span class="sxs-lookup"><span data-stu-id="716b9-117">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>

## <a name="example"></a><span data-ttu-id="716b9-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="716b9-118">Example</span></span>

<span data-ttu-id="716b9-119">W tym przykładzie `Shape` Klasa zawiera dwie współrzędne `x` , `y` i `Area()` metodę wirtualną.</span><span class="sxs-lookup"><span data-stu-id="716b9-119">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="716b9-120">Różne klasy kształtu, takie jak `Circle` , `Cylinder` i `Sphere` dziedziczą `Shape` klasę, a obszar powierzchni jest obliczany dla każdego rysunku.</span><span class="sxs-lookup"><span data-stu-id="716b9-120">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="716b9-121">Każda klasa pochodna ma własną implementację zastępującą `Area()` .</span><span class="sxs-lookup"><span data-stu-id="716b9-121">Each derived class has its own override implementation of `Area()`.</span></span>

<span data-ttu-id="716b9-122">Zwróć uwagę, że dziedziczone klasy `Circle` , `Sphere` i `Cylinder` wszystkie używają konstruktorów, które inicjują klasę bazową, jak pokazano w poniższej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="716b9-122">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

<span data-ttu-id="716b9-123">Poniższy program oblicza i wyświetla odpowiedni obszar dla każdego rysunku przez wywoływanie odpowiedniej implementacji `Area()` metody, zgodnie z obiektem, który jest skojarzony z metodą.</span><span class="sxs-lookup"><span data-stu-id="716b9-123">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a><span data-ttu-id="716b9-124">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="716b9-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="716b9-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="716b9-125">See also</span></span>

- [<span data-ttu-id="716b9-126">Polimorfizm</span><span class="sxs-lookup"><span data-stu-id="716b9-126">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
- [<span data-ttu-id="716b9-127">streszczeń</span><span class="sxs-lookup"><span data-stu-id="716b9-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="716b9-128">override</span><span class="sxs-lookup"><span data-stu-id="716b9-128">override</span></span>](override.md)
- [<span data-ttu-id="716b9-129">New (modyfikator)</span><span class="sxs-lookup"><span data-stu-id="716b9-129">new (modifier)</span></span>](new-modifier.md)
