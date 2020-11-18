---
title: Wspólne anulowanie wątków
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 9e9224e9dc9ac57defe75e916dd6b9844bba7f12
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826615"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="e967b-102">Wspólne anulowanie wątków</span><span class="sxs-lookup"><span data-stu-id="e967b-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="e967b-103">Przed rozpoczęciem .NET Framework 4 platforma .NET nie zapewniała wbudowanego sposobu anulowania wątku po jego uruchomieniu.</span><span class="sxs-lookup"><span data-stu-id="e967b-103">Prior to .NET Framework 4, .NET provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="e967b-104">Jednak rozpoczynając od .NET Framework 4, można użyć, <xref:System.Threading.CancellationToken?displayProperty=nameWithType> Aby anulować wątki, tak jak można je użyć do anulowania <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> obiektów lub zapytań PLINQ.</span><span class="sxs-lookup"><span data-stu-id="e967b-104">However, starting with .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="e967b-105">Chociaż <xref:System.Threading.Thread?displayProperty=nameWithType> Klasa nie oferuje wbudowanej obsługi tokenów anulowania, można przekazać token do procedury wątku za pomocą <xref:System.Threading.Thread> konstruktora, który przyjmuje <xref:System.Threading.ParameterizedThreadStart> Delegat.</span><span class="sxs-lookup"><span data-stu-id="e967b-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="e967b-106">Poniższy przykład demonstruje, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="e967b-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="e967b-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e967b-107">See also</span></span>

- [<span data-ttu-id="e967b-108">Używanie wątków i wątkowości</span><span class="sxs-lookup"><span data-stu-id="e967b-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
