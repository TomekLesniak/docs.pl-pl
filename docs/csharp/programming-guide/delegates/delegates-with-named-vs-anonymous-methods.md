---
title: Delegaty z metodami nazwanymi i anonimowymi — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat delegatów z metodami nazwanymi i anonimowymi. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 940363b87e17b34feeffaff38ed498d6fcf6850a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302753"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="77e55-104">Delegaty z metodami nazwanymi lub anonimowymi (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="77e55-104">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="77e55-105">[Delegat](../../language-reference/builtin-types/reference-types.md) może być skojarzony z nazwaną metodą.</span><span class="sxs-lookup"><span data-stu-id="77e55-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can be associated with a named method.</span></span> <span data-ttu-id="77e55-106">Podczas tworzenia wystąpienia delegata przy użyciu nazwanej metody Metoda jest przenoszona jako parametr, na przykład:</span><span class="sxs-lookup"><span data-stu-id="77e55-106">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="77e55-107">Ta metoda jest wywoływana przy użyciu nazwanej metody.</span><span class="sxs-lookup"><span data-stu-id="77e55-107">This is called using a named method.</span></span> <span data-ttu-id="77e55-108">Obiekty delegowane skonstruowane przy użyciu nazwanej metody mogą hermetyzować metodę [statyczną](../../language-reference/keywords/static.md) lub metodę wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="77e55-108">Delegates constructed with a named method can encapsulate either a [static](../../language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="77e55-109">Nazwane metody są jedynym sposobem tworzenia wystąpienia delegata we wcześniejszych wersjach języka C#.</span><span class="sxs-lookup"><span data-stu-id="77e55-109">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="77e55-110">Jednak w sytuacji, w której Tworzenie nowej metody jest niepożądane, w języku C# można utworzyć wystąpienie delegata i od razu określić blok kodu, który zostanie przetworzony przez delegata po wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="77e55-110">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="77e55-111">Blok może zawierać wyrażenie lambda lub metodę anonimową.</span><span class="sxs-lookup"><span data-stu-id="77e55-111">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="77e55-112">Aby uzyskać więcej informacji, zobacz [funkcje anonimowe](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="77e55-112">For more information, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77e55-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="77e55-113">Remarks</span></span>  
 <span data-ttu-id="77e55-114">Metoda, która jest przekazywany jako parametr delegata, musi mieć taką samą sygnaturę jak Deklaracja delegata.</span><span class="sxs-lookup"><span data-stu-id="77e55-114">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="77e55-115">Wystąpienie delegata może hermetyzować wartość statyczną lub metodę wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="77e55-115">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="77e55-116">Chociaż delegat może korzystać z parametru [out](../../language-reference/keywords/out-parameter-modifier.md) , nie zalecamy jej używania z delegatami zdarzeń multiemisji, ponieważ nie można wiedzieć, który delegat zostanie wywołany.</span><span class="sxs-lookup"><span data-stu-id="77e55-116">Although the delegate can use an [out](../../language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="77e55-117">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="77e55-117">Example 1</span></span>  
 <span data-ttu-id="77e55-118">Poniżej przedstawiono prosty przykład deklarowania i używania delegata.</span><span class="sxs-lookup"><span data-stu-id="77e55-118">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="77e55-119">Zwróć uwagę, że zarówno delegat, `Del` , jak i skojarzona Metoda, `MultiplyNumbers` mają taką samą sygnaturę</span><span class="sxs-lookup"><span data-stu-id="77e55-119">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="77e55-120">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="77e55-120">Example 2</span></span>  
 <span data-ttu-id="77e55-121">W poniższym przykładzie jeden delegat jest mapowany na metody static i instance i zwraca określone informacje z każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="77e55-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="77e55-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="77e55-122">See also</span></span>

- [<span data-ttu-id="77e55-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="77e55-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="77e55-124">Delegaci</span><span class="sxs-lookup"><span data-stu-id="77e55-124">Delegates</span></span>](./index.md)
- [<span data-ttu-id="77e55-125">Jak łączyć delegatów (delegatów multiemisji)</span><span class="sxs-lookup"><span data-stu-id="77e55-125">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="77e55-126">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="77e55-126">Events</span></span>](../events/index.md)
