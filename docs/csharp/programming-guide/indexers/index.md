---
title: Indeksatory — Przewodnik programowania w języku C#
description: Indeksatory w języku C# zezwalają na indeksowanie wystąpień klasy lub struktury, takich jak tablice. Można ustawić lub pobrać wartość indeksowaną bez określenia typu lub elementu członkowskiego wystąpienia.
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: ea95eef7bb9ba232e4d59e3f833b82e98398fc33
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495307"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="11eef-104">Indeksatory (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="11eef-104">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="11eef-105">Indeksatory umożliwiają indeksowanie wystąpień klasy lub struktury tak samo jak w przypadku tablic.</span><span class="sxs-lookup"><span data-stu-id="11eef-105">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="11eef-106">Indeksowaną wartość można ustawić lub pobrać bez jawnego określenia typu lub elementu członkowskiego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="11eef-106">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="11eef-107">Indeksatory przypominają [Właściwości](../classes-and-structs/properties.md) , z tą różnicą, że ich metody dostępu pobierają parametry.</span><span class="sxs-lookup"><span data-stu-id="11eef-107">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="11eef-108">W poniższym przykładzie zdefiniowano klasę generyczną z prostymi metodami dostępu [Get](../../language-reference/keywords/get.md) i [Set](../../language-reference/keywords/set.md) do przypisywania i pobierania wartości.</span><span class="sxs-lookup"><span data-stu-id="11eef-108">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="11eef-109">`Program`Klasa tworzy wystąpienie tej klasy do przechowywania ciągów.</span><span class="sxs-lookup"><span data-stu-id="11eef-109">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="11eef-110">Aby uzyskać więcej przykładów, zobacz sekcję [pokrewne](./index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="11eef-110">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="11eef-111">Definicje treści wyrażenia</span><span class="sxs-lookup"><span data-stu-id="11eef-111">Expression Body Definitions</span></span>  

<span data-ttu-id="11eef-112">Metoda dostępu "Get" lub "Set" może składać się z pojedynczej instrukcji, która zwraca lub ustawia wartość.</span><span class="sxs-lookup"><span data-stu-id="11eef-112">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="11eef-113">Składowe w postaci wyrażeń zawierają uproszczoną składnię do obsługi tego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="11eef-113">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="11eef-114">Począwszy od języka C# 6, indeksator tylko do odczytu może być implementowany jako składowa z wyrażeniem, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="11eef-114">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="11eef-115">Należy zauważyć, że `=>` wprowadza treść wyrażenia, a `get` słowo kluczowe nie jest używane.</span><span class="sxs-lookup"><span data-stu-id="11eef-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span>

<span data-ttu-id="11eef-116">Począwszy od języka C# 7,0, zarówno metoda dostępu get, jak i set może być zaimplementowana jako składowe z wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="11eef-116">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="11eef-117">W takim przypadku `get` `set` należy użyć słów kluczowych i.</span><span class="sxs-lookup"><span data-stu-id="11eef-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="11eef-118">Przykład:</span><span class="sxs-lookup"><span data-stu-id="11eef-118">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="11eef-119">Omówienie indeksatorów</span><span class="sxs-lookup"><span data-stu-id="11eef-119">Indexers Overview</span></span>  
  
- <span data-ttu-id="11eef-120">Indeksatory umożliwiają indeksowanie obiektów w podobny sposób do tablic.</span><span class="sxs-lookup"><span data-stu-id="11eef-120">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="11eef-121">`get`Metoda dostępu zwraca wartość.</span><span class="sxs-lookup"><span data-stu-id="11eef-121">A `get` accessor returns a value.</span></span> <span data-ttu-id="11eef-122">`set`Metoda dostępu przypisuje wartość.</span><span class="sxs-lookup"><span data-stu-id="11eef-122">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="11eef-123">[To](../../language-reference/keywords/this.md) słowo kluczowe jest używane do definiowania indeksatora.</span><span class="sxs-lookup"><span data-stu-id="11eef-123">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="11eef-124">Słowo kluczowe [Value](../../language-reference/keywords/value.md) służy do definiowania wartości przypisywanej przez `set` metodę dostępu.</span><span class="sxs-lookup"><span data-stu-id="11eef-124">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
  
- <span data-ttu-id="11eef-125">Indeksatory nie muszą być indeksowane przez wartość całkowitą; Istnieje możliwość zdefiniowania określonego mechanizmu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="11eef-125">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="11eef-126">Indeksatory mogą być przeciążone.</span><span class="sxs-lookup"><span data-stu-id="11eef-126">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="11eef-127">Indeksatory mogą mieć więcej niż jeden parametr formalny, na przykład podczas uzyskiwania dostępu do tablicy dwuwymiarowej.</span><span class="sxs-lookup"><span data-stu-id="11eef-127">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> <span data-ttu-id="11eef-128">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="11eef-128">Related Sections</span></span>  
  
- [<span data-ttu-id="11eef-129">Używanie indeksatorów</span><span class="sxs-lookup"><span data-stu-id="11eef-129">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="11eef-130">Indeksatory w interfejsach</span><span class="sxs-lookup"><span data-stu-id="11eef-130">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="11eef-131">Porównanie właściwości i indeksatorów</span><span class="sxs-lookup"><span data-stu-id="11eef-131">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="11eef-132">Ograniczanie dostępności metody dostępu</span><span class="sxs-lookup"><span data-stu-id="11eef-132">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="11eef-133">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="11eef-133">C# Language Specification</span></span>  

<span data-ttu-id="11eef-134">Aby uzyskać więcej informacji, zobacz [indeksatory](~/_csharplang/spec/classes.md#indexers) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="11eef-134">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="11eef-135">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="11eef-135">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="11eef-136">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="11eef-136">See also</span></span>

- [<span data-ttu-id="11eef-137">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="11eef-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="11eef-138">Właściwości</span><span class="sxs-lookup"><span data-stu-id="11eef-138">Properties</span></span>](../classes-and-structs/properties.md)
