---
title: Parametry typu ogólnego — Przewodnik programowania w języku C#
description: Informacje o definicji typu ogólnego w języku C#, gdzie parametr typu jest symbolem zastępczym dla typu, który klient określa dla wystąpienia typu ogólnego.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: dc37029378ac1e9ec194d95b561787761d69a9fd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299256"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="679f4-103">Parametry typu ogólnego (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="679f4-103">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="679f4-104">W przypadku typu ogólnego lub definicji metody parametr typu jest symbolem zastępczym określonego typu, który klient określa podczas tworzenia wystąpienia typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="679f4-104">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="679f4-105">Klasa generyczna, taka jak `GenericList<T>` wymieniona w temacie [wprowadzenie do typów ogólnych](./index.md), nie może być używana jako-jest, ponieważ nie jest w rzeczywistości typem; jest to bardziej podobne do planu dla typu.</span><span class="sxs-lookup"><span data-stu-id="679f4-105">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="679f4-106">Aby użyć `GenericList<T>` kodu klienta, należy zadeklarować i utworzyć wystąpienie złożonego typu przez określenie argumentu typu wewnątrz nawiasów kątowych.</span><span class="sxs-lookup"><span data-stu-id="679f4-106">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="679f4-107">Argument typu dla tej konkretnej klasy może być dowolnym typem rozpoznawanym przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="679f4-107">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="679f4-108">Można utworzyć dowolną liczbę wystąpień typu złożonego, każdy z nich przy użyciu innego argumentu typu, w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="679f4-108">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="679f4-109">W każdym z tych wystąpień `GenericList<T>` , każde wystąpienie `T` w klasie jest zastępowane w czasie wykonywania z argumentem typu.</span><span class="sxs-lookup"><span data-stu-id="679f4-109">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="679f4-110">Zgodnie z tym podstawianiem zostały utworzone trzy osobne, bezpieczne obiekty typu za pomocą jednej definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="679f4-110">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="679f4-111">Aby uzyskać więcej informacji o tym, jak to podstawienie jest wykonywane przez środowisko CLR, zobacz [typy ogólne w czasie wykonywania](./generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="679f4-111">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="679f4-112">Wskazówki dotyczące nazewnictwa parametrów typu</span><span class="sxs-lookup"><span data-stu-id="679f4-112">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="679f4-113">**Należy** nazywać parametry typu ogólnego z nazwami opisowymi, chyba że nazwa pojedynczej litery nie jest całkowicie oczywista, a nazwa opisowa nie będzie dodawać wartości.</span><span class="sxs-lookup"><span data-stu-id="679f4-113">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="679f4-114">**Rozważ** użycie T jako nazwy parametru typu dla typów z jednym pojedynczym parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="679f4-114">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="679f4-115">**Wykonaj** prefiks nazwy parametrów typu opisowego z "T".</span><span class="sxs-lookup"><span data-stu-id="679f4-115">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="679f4-116">**Rozważ** wskazanie ograniczeń umieszczanych na parametrze typu w nazwie parametru.</span><span class="sxs-lookup"><span data-stu-id="679f4-116">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="679f4-117">Na przykład parametr ograniczony do `ISession` może być wywoływany `TSession` .</span><span class="sxs-lookup"><span data-stu-id="679f4-117">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="679f4-118">Reguły analizy kodu [CA1715](/visualstudio/code-quality/ca1715) można użyć, aby upewnić się, że parametry typu są odpowiednio nazwane.</span><span class="sxs-lookup"><span data-stu-id="679f4-118">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="679f4-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="679f4-119">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="679f4-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="679f4-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="679f4-121">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="679f4-121">Generics</span></span>](./index.md)
- [<span data-ttu-id="679f4-122">Różnice między szablonami C++ i typami ogólnymi C#</span><span class="sxs-lookup"><span data-stu-id="679f4-122">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
