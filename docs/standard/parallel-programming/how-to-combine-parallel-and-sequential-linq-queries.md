---
title: 'Instrukcje: Łączenie równoległych i sekwencyjnych zapytań LINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: e851c6d72a5fd932c065368b893b907d7820c918
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827103"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Instrukcje: Łączenie równoległych i sekwencyjnych zapytań LINQ

W tym przykładzie pokazano, jak za pomocą <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metody poinstruować PLINQ, aby przetwarzać wszystkie kolejne operatory w kwerendzie sekwencyjnie. Chociaż przetwarzanie sekwencyjne jest często wolniejsze niż równoległe, czasami konieczne jest wygenerowanie poprawnych wyników.  
  
> [!NOTE]
> Ten przykład jest przeznaczony do zademonstrowania użycia i może nie działać szybciej niż równoważne LINQ to Objects sekwencyjne zapytanie. Aby uzyskać więcej informacji na temat przyspieszenie, zobacz [Opis przyspieszenie w PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie przedstawiono jeden scenariusz, w którym <xref:System.Linq.ParallelEnumerable.AsSequential%2A> jest to wymagane, czyli zachowanie kolejności, która została ustanowiona w poprzedniej klauzuli zapytania.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Aby skompilować i uruchomić ten kod, wklej go do projektu [przykładu danych PLINQ](plinq-data-sample.md) , Dodaj wiersz do wywołania metody z `Main` , a następnie naciśnij klawisz **F5**.  
  
## <a name="see-also"></a>Zobacz także

- [Równoległe LINQ (PLINQ)](introduction-to-plinq.md)
