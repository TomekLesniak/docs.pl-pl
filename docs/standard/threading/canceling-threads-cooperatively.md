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
# <a name="canceling-threads-cooperatively"></a>Wspólne anulowanie wątków

Przed rozpoczęciem .NET Framework 4 platforma .NET nie zapewniała wbudowanego sposobu anulowania wątku po jego uruchomieniu. Jednak rozpoczynając od .NET Framework 4, można użyć, <xref:System.Threading.CancellationToken?displayProperty=nameWithType> Aby anulować wątki, tak jak można je użyć do anulowania <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> obiektów lub zapytań PLINQ. Chociaż <xref:System.Threading.Thread?displayProperty=nameWithType> Klasa nie oferuje wbudowanej obsługi tokenów anulowania, można przekazać token do procedury wątku za pomocą <xref:System.Threading.Thread> konstruktora, który przyjmuje <xref:System.Threading.ParameterizedThreadStart> Delegat. Poniższy przykład demonstruje, jak to zrobić.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Zobacz także

- [Używanie wątków i wątkowości](using-threads-and-threading.md)
