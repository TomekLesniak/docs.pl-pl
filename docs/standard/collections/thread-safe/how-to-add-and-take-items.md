---
title: 'Instrukcje: Dodawanie i pobieranie elementów osobno w ramach kolekcji BlockingCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
ms.openlocfilehash: de65dbdcc3239016a16bc12f9254bb99637e45b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733493"
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="b073a-102">Instrukcje: Dodawanie i pobieranie elementów osobno w ramach kolekcji BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="b073a-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>

<span data-ttu-id="b073a-103">Ten przykład pokazuje, jak dodawać i usuwać elementy z <xref:System.Collections.Concurrent.BlockingCollection%601> zarówno w bloku blokowania, jak i bez blokowania.</span><span class="sxs-lookup"><span data-stu-id="b073a-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and a non-blocking manner.</span></span> <span data-ttu-id="b073a-104">Aby uzyskać więcej informacji na temat <xref:System.Collections.Concurrent.BlockingCollection%601> , zobacz [BlockingCollection Overview](blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b073a-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="b073a-105">Aby zapoznać się z przykładem, jak wyliczyć a <xref:System.Collections.Concurrent.BlockingCollection%601> dopóki nie jest pusty i nie zostaną dodane żadne elementy, zobacz [How to: use foreach by Remove Items in BlockingCollection](how-to-use-foreach-to-remove.md).</span><span class="sxs-lookup"><span data-stu-id="b073a-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](how-to-use-foreach-to-remove.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="b073a-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="b073a-106">Example</span></span>  

 <span data-ttu-id="b073a-107">Ten pierwszy przykład pokazuje, jak dodawać i podejmować elementy, aby operacje były blokowane, jeśli kolekcja jest tymczasowo pusta (podczas wykonywania) lub przy maksymalnej pojemności (podczas dodawania) lub w przypadku, gdy upłynął określony limit czasu.</span><span class="sxs-lookup"><span data-stu-id="b073a-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or if a specified timeout period has elapsed.</span></span> <span data-ttu-id="b073a-108">Należy zauważyć, że blokowanie dla maksymalnej pojemności jest włączone tylko wtedy, gdy BlockingCollection został utworzony z maksymalną pojemnością określoną w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="b073a-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="b073a-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="b073a-109">Example</span></span>  

 <span data-ttu-id="b073a-110">Ten drugi przykład pokazuje, jak dodawać i podejmować elementy, aby nie blokowały operacji.</span><span class="sxs-lookup"><span data-stu-id="b073a-110">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="b073a-111">Jeśli żaden element nie jest obecny, osiągnięto maksymalną pojemność w ograniczonej kolekcji lub upłynął limit czasu, a następnie <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operacja lub zwróci wartość false.</span><span class="sxs-lookup"><span data-stu-id="b073a-111">If no item is present, maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="b073a-112">Dzięki temu wątek może wykonać inne przydatne działania przez pewien czas, a następnie spróbować ponownie później, aby pobrać nowy element, lub spróbować dodać ten sam element, którego nie można dodać wcześniej.</span><span class="sxs-lookup"><span data-stu-id="b073a-112">This allows the thread to do some other useful work for a while and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="b073a-113">Program demonstruje również sposób implementacji anulowania podczas uzyskiwania dostępu do elementu <xref:System.Collections.Concurrent.BlockingCollection%601> .</span><span class="sxs-lookup"><span data-stu-id="b073a-113">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="b073a-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b073a-114">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="b073a-115">BlockingCollection — Przegląd</span><span class="sxs-lookup"><span data-stu-id="b073a-115">BlockingCollection Overview</span></span>](blockingcollection-overview.md)
