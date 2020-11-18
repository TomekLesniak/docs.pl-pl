---
title: 'Instrukcje: Zwracanie wartości z zadania'
description: Zobacz, jak używać typu System. Threading. Tasks. Task <TResult> do zwracania wartości z właściwości wynik w programie .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: c7a4a683545c9ef0448d9cdce769aae79215aecf
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825614"
---
# <a name="how-to-return-a-value-from-a-task"></a>Instrukcje: Zwracanie wartości z zadania
W tym przykładzie pokazano, jak za pomocą <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> typu zwrócić wartość z <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości. Wymaga, aby folder C:\Users\Public\Pictures\Sample obrazy \ katalog istnieje i zawierał pliki.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <xref:System.Threading.Tasks.Task%601.Result%2A>Właściwość blokuje wątek wywołujący do momentu zakończenia zadania.  
  
 Aby dowiedzieć się, jak przekazać wynik jednego <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> do zadania kontynuacji, zobacz Tworzenie [łańcucha zadań przy użyciu zadań kontynuacji](chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Zobacz także

- [Programowanie asynchroniczne oparte na zadaniach](task-based-asynchronous-programming.md)
- [Wyrażenia lambda w PLINQ i TPL](lambda-expressions-in-plinq-and-tpl.md)
