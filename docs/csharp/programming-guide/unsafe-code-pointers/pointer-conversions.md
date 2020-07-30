---
title: Konwersje wskaźników — Przewodnik programowania w języku C#
description: Poznaj Konwersje wskaźników. Zobacz tabele konwersji niejawnych i jawnych wskaźników, przykłady kodu i wyświetlanie dodatkowych dostępnych zasobów.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: c39be5cb52964abbea5bc5636c6fa74d8411a331
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382090"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="55f4e-104">Konwersje wskaźników (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="55f4e-104">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="55f4e-105">W poniższej tabeli przedstawiono wstępnie zdefiniowane konwersje niejawnych wskaźników.</span><span class="sxs-lookup"><span data-stu-id="55f4e-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="55f4e-106">Konwersje niejawne mogą wystąpić w wielu sytuacjach, w tym wywoływanie metod i instrukcje przypisania.</span><span class="sxs-lookup"><span data-stu-id="55f4e-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="55f4e-107">Niejawne konwersje wskaźników</span><span class="sxs-lookup"><span data-stu-id="55f4e-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="55f4e-108">Źródło</span><span class="sxs-lookup"><span data-stu-id="55f4e-108">From</span></span>|<span data-ttu-id="55f4e-109">Działanie</span><span class="sxs-lookup"><span data-stu-id="55f4e-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="55f4e-110">Dowolny typ wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-110">Any pointer type</span></span>|<span data-ttu-id="55f4e-111">pozycję</span><span class="sxs-lookup"><span data-stu-id="55f4e-111">void\*</span></span>|  
|<span data-ttu-id="55f4e-112">wartość null</span><span class="sxs-lookup"><span data-stu-id="55f4e-112">null</span></span>|<span data-ttu-id="55f4e-113">Dowolny typ wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="55f4e-114">Jawna konwersja wskaźnika jest używana do przeprowadzania konwersji, dla których nie istnieje niejawna konwersja za pomocą wyrażenia Cast.</span><span class="sxs-lookup"><span data-stu-id="55f4e-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="55f4e-115">W poniższej tabeli przedstawiono te konwersje.</span><span class="sxs-lookup"><span data-stu-id="55f4e-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="55f4e-116">Jawne konwersje wskaźników</span><span class="sxs-lookup"><span data-stu-id="55f4e-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="55f4e-117">Źródło</span><span class="sxs-lookup"><span data-stu-id="55f4e-117">From</span></span>|<span data-ttu-id="55f4e-118">Działanie</span><span class="sxs-lookup"><span data-stu-id="55f4e-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="55f4e-119">Dowolny typ wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-119">Any pointer type</span></span>|<span data-ttu-id="55f4e-120">Dowolny inny typ wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-120">Any other pointer type</span></span>|  
|<span data-ttu-id="55f4e-121">bajty, Byte, Short, UShort, int, uint, Long lub ULONG</span><span class="sxs-lookup"><span data-stu-id="55f4e-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="55f4e-122">Dowolny typ wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-122">Any pointer type</span></span>|  
|<span data-ttu-id="55f4e-123">Dowolny typ wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-123">Any pointer type</span></span>|<span data-ttu-id="55f4e-124">bajty, Byte, Short, UShort, int, uint, Long lub ULONG</span><span class="sxs-lookup"><span data-stu-id="55f4e-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55f4e-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="55f4e-125">Example</span></span>  
 <span data-ttu-id="55f4e-126">W poniższym przykładzie wskaźnik do `int` jest konwertowany na wskaźnik do `byte` .</span><span class="sxs-lookup"><span data-stu-id="55f4e-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="55f4e-127">Zauważ, że wskaźnik wskazuje najniższy przyjmowany bajt zmiennej.</span><span class="sxs-lookup"><span data-stu-id="55f4e-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="55f4e-128">Po kolejnym zwiększeniu wyniku do rozmiaru `int` (4 bajty) można wyświetlić pozostałe bajty zmiennej.</span><span class="sxs-lookup"><span data-stu-id="55f4e-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="55f4e-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="55f4e-129">See also</span></span>

- [<span data-ttu-id="55f4e-130">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="55f4e-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="55f4e-131">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="55f4e-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="55f4e-132">Typy odwołań</span><span class="sxs-lookup"><span data-stu-id="55f4e-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="55f4e-133">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="55f4e-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="55f4e-134">niebezpieczne</span><span class="sxs-lookup"><span data-stu-id="55f4e-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="55f4e-135">fixed, instrukcja</span><span class="sxs-lookup"><span data-stu-id="55f4e-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="55f4e-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="55f4e-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
