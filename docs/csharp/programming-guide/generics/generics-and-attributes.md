---
title: Typy ogólne i atrybuty — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat stosowania atrybutów do typów ogólnych. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 17556af2e1bc2963de953cea242d7000509acbcd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299880"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="e3813-104">Typy ogólne i atrybuty (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e3813-104">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="e3813-105">Atrybuty mogą być stosowane do typów ogólnych w taki sam sposób jak typy nieogólne.</span><span class="sxs-lookup"><span data-stu-id="e3813-105">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="e3813-106">Aby uzyskać więcej informacji na temat stosowania atrybutów, zobacz [atrybuty](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="e3813-106">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="e3813-107">Atrybuty niestandardowe są dozwolone tylko w celu odwoływania się do otwartych typów ogólnych, które są typami ogólnymi, dla których nie są dostarczane żadne argumenty typu, i zamknięto skonstruowane typy ogólne, które dostarczają argumentów dla wszystkich parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="e3813-107">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="e3813-108">W poniższych przykładach użyto tego atrybutu niestandardowego:</span><span class="sxs-lookup"><span data-stu-id="e3813-108">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="e3813-109">Atrybut może odwoływać się do otwartego typu ogólnego:</span><span class="sxs-lookup"><span data-stu-id="e3813-109">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="e3813-110">Określ wiele parametrów typu przy użyciu odpowiedniej liczby przecinków.</span><span class="sxs-lookup"><span data-stu-id="e3813-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="e3813-111">W tym przykładzie `GenericClass2` ma dwa parametry typu:</span><span class="sxs-lookup"><span data-stu-id="e3813-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="e3813-112">Atrybut może odwoływać się do zamkniętego skonstruowanego typu ogólnego:</span><span class="sxs-lookup"><span data-stu-id="e3813-112">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="e3813-113">Atrybut, który odwołuje się do parametru typu ogólnego, spowoduje błąd czasu kompilacji:</span><span class="sxs-lookup"><span data-stu-id="e3813-113">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="e3813-114">Typ ogólny nie może dziedziczyć po elemencie <xref:System.Attribute> :</span><span class="sxs-lookup"><span data-stu-id="e3813-114">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="e3813-115">Aby uzyskać informacje o typie ogólnym lub parametrze typu w czasie wykonywania, można użyć metod <xref:System.Reflection> .</span><span class="sxs-lookup"><span data-stu-id="e3813-115">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="e3813-116">Aby uzyskać więcej informacji, zobacz [Ogólne i odbicie](./generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="e3813-116">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3813-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3813-117">See also</span></span>

- [<span data-ttu-id="e3813-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e3813-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e3813-119">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="e3813-119">Generics</span></span>](./index.md)
- [<span data-ttu-id="e3813-120">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e3813-120">Attributes</span></span>](../../../standard/attributes/index.md)
