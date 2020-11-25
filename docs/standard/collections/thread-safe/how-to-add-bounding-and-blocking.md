---
title: 'Instrukcje: Dodawanie funkcji blokujących i ograniczających do kolekcji'
ms.date: 03/30/2017
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
ms.openlocfilehash: ba41176d87779fe673fa162d0bf04c10414cdd92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733480"
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="e0efd-102">Instrukcje: Dodawanie funkcji blokujących i ograniczających do kolekcji</span><span class="sxs-lookup"><span data-stu-id="e0efd-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>

<span data-ttu-id="e0efd-103">Ten przykład pokazuje, jak dodać funkcje ograniczania i blokowania do niestandardowej klasy kolekcji <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> , implementując interfejs w klasie, a następnie używając wystąpienia klasy jako wewnętrznego mechanizmu magazynowania dla <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e0efd-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e0efd-104">Aby uzyskać więcej informacji na temat ograniczania i blokowania, zobacz [BlockingCollection Overview](blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0efd-104">For more information about bounding and blocking, see [BlockingCollection Overview](blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0efd-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="e0efd-105">Example</span></span>  

 <span data-ttu-id="e0efd-106">Klasa kolekcji niestandardowych jest podstawową kolejką priorytetową, w której poziomy priorytetów są reprezentowane jako tablica <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> obiektów.</span><span class="sxs-lookup"><span data-stu-id="e0efd-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="e0efd-107">Żadna dodatkowa kolejność nie jest przeprowadzana w ramach każdej kolejki.</span><span class="sxs-lookup"><span data-stu-id="e0efd-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="e0efd-108">W kodzie klienta uruchomiono trzy zadania.</span><span class="sxs-lookup"><span data-stu-id="e0efd-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="e0efd-109">Pierwsze zadanie po prostu sonduje pod kątem pociągnięć z klawiaturą, aby umożliwić anulowanie w dowolnym momencie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="e0efd-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="e0efd-110">Drugie zadanie jest wątkiem producenta; dodaje nowe elementy do kolekcji blokującej i daje każdemu elementowi priorytet oparty na wartości losowej.</span><span class="sxs-lookup"><span data-stu-id="e0efd-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="e0efd-111">Trzecie zadanie usuwa elementy z kolekcji, gdy staną się dostępne.</span><span class="sxs-lookup"><span data-stu-id="e0efd-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="e0efd-112">Można dostosować zachowanie aplikacji, co sprawia, że jeden z wątków działa szybciej niż inne.</span><span class="sxs-lookup"><span data-stu-id="e0efd-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="e0efd-113">Jeśli producent działa szybciej, zobaczysz powiązane funkcje, ponieważ kolekcja blokująca uniemożliwia dodanie elementów, jeśli zawiera już liczbę elementów, które są określone w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="e0efd-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="e0efd-114">Jeśli klient działa szybciej, zobaczysz funkcję blokowania, gdy odbiorca czeka na dodanie nowego elementu.</span><span class="sxs-lookup"><span data-stu-id="e0efd-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 <span data-ttu-id="e0efd-115">Domyślnie magazyn dla programu to <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e0efd-115">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0efd-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e0efd-116">See also</span></span>

- [<span data-ttu-id="e0efd-117">Kolekcje bezpieczne dla wątków</span><span class="sxs-lookup"><span data-stu-id="e0efd-117">Thread-Safe Collections</span></span>](index.md)
