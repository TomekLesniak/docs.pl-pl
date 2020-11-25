---
title: 'Instrukcje: Mierzenie wydajności zapytań PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 2cbd178d5004d28120ab701a777a474a7e78e09e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734442"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="d0f9c-102">Instrukcje: Mierzenie wydajności zapytań PLINQ</span><span class="sxs-lookup"><span data-stu-id="d0f9c-102">How to: Measure PLINQ Query Performance</span></span>

<span data-ttu-id="d0f9c-103">Ten przykład pokazuje, jak używać <xref:System.Diagnostics.Stopwatch> klasy do mierzenia czasu potrzebnego na wykonanie zapytania PLINQ.</span><span class="sxs-lookup"><span data-stu-id="d0f9c-103">This example shows how to use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f9c-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="d0f9c-104">Example</span></span>  

 <span data-ttu-id="d0f9c-105">W tym przykładzie jest używana pusta `foreach` Pętla ( `For Each` w Visual Basic) do mierzenia czasu wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="d0f9c-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="d0f9c-106">W kodzie rzeczywistym pętla zwykle zawiera dodatkowe kroki przetwarzania, które dodają do łącznego czasu wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="d0f9c-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="d0f9c-107">Należy zauważyć, że stopera nie jest uruchomiona przed pętlą, ponieważ jest to wykonywane po rozpoczęciu wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="d0f9c-107">Notice that the stopwatch is not started until just before the loop, because that's when the query execution begins.</span></span> <span data-ttu-id="d0f9c-108">Jeśli potrzebujesz bardziej szczegółowych pomiarów, możesz użyć `ElapsedTicks` Właściwości zamiast `ElapsedMilliseconds` .</span><span class="sxs-lookup"><span data-stu-id="d0f9c-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="d0f9c-109">Łączny czas wykonywania jest przydatną metryką podczas eksperymentowania z implementacjami zapytań, ale nie zawsze informuje cały wątek.</span><span class="sxs-lookup"><span data-stu-id="d0f9c-109">The total execution time is a useful metric when you are experimenting with query implementations, but it doesn't always tell the whole story.</span></span> <span data-ttu-id="d0f9c-110">Aby uzyskać dokładniejszy i bogatszy widok interakcji między wątkami zapytań i innymi uruchomionymi procesami, użyj [wizualizatora współbieżności](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="d0f9c-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f9c-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d0f9c-111">See also</span></span>

- [<span data-ttu-id="d0f9c-112">Równoległe LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d0f9c-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
