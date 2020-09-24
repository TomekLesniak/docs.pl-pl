---
title: Delegaty ogólne — Przewodnik programowania w języku C#
description: Dowiedz się więcej o używaniu delegatów ogólnych w języku C#. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: df417701feb77dc47cff1cdd68eb4c7405d15beb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157411"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="23e65-104">Delegaty ogólne (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="23e65-104">Generic Delegates (C# Programming Guide)</span></span>

<span data-ttu-id="23e65-105">[Delegat](../../language-reference/builtin-types/reference-types.md) może definiować własne parametry typu.</span><span class="sxs-lookup"><span data-stu-id="23e65-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="23e65-106">Kod, który odwołuje się do delegata generycznego, może określić argument typu, aby utworzyć zamknięty typ skonstruowany, podobnie jak podczas tworzenia wystąpienia klasy generycznej lub wywołania metody ogólnej, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="23e65-106">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="23e65-107">Język C# w wersji 2,0 ma nową funkcję o nazwie konwersja grup metod, która ma zastosowanie do konkretnych typów delegatów, i umożliwia zapisanie poprzedniego wiersza z tą uproszczoną składnią:</span><span class="sxs-lookup"><span data-stu-id="23e65-107">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="23e65-108">Delegaty zdefiniowane w klasie generycznej mogą używać parametrów typu klasy generycznej w taki sam sposób, jak metody klasy.</span><span class="sxs-lookup"><span data-stu-id="23e65-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="23e65-109">Kod odwołujący się do delegata musi określać argument typu klasy zawierającej w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="23e65-109">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="23e65-110">Delegaty ogólne są szczególnie przydatne w definiowaniu zdarzeń na podstawie typowego wzorca projektowego, ponieważ argument nadawcy może być silnie określony i nie musi być już rzutowany do i z <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="23e65-110">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="23e65-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="23e65-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="23e65-112">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="23e65-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="23e65-113">Wprowadzenie do typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="23e65-113">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="23e65-114">Metody ogólne</span><span class="sxs-lookup"><span data-stu-id="23e65-114">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="23e65-115">Klasy ogólne</span><span class="sxs-lookup"><span data-stu-id="23e65-115">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="23e65-116">Interfejsy ogólne</span><span class="sxs-lookup"><span data-stu-id="23e65-116">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="23e65-117">Delegaci</span><span class="sxs-lookup"><span data-stu-id="23e65-117">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="23e65-118">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="23e65-118">Generics</span></span>](../../../standard/generics/index.md)
