---
title: Biblioteka zadań równoległych (TPL)
description: Poznaj bibliotekę zadań równoległych (TPL), zestaw typów publicznych i interfejsów API, aby uprościć proces dodawania równoległości & współbieżności do aplikacji w środowisku .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
ms.openlocfilehash: 596671b267484561a8697546caa5a4764242ebd3
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925236"
---
# <a name="task-parallel-library-tpl"></a>Biblioteka zadań równoległych (TPL)

Biblioteka zadań równoległych (TPL) to zestaw typów publicznych i interfejsów API w <xref:System.Threading?displayProperty=nameWithType> <xref:System.Threading.Tasks?displayProperty=nameWithType> przestrzeniach nazw i. Zadaniem biblioteki TPL jest zwiększenie produktywności deweloperów przez uproszczenie procesu dodawania równoległości i współbieżności do aplikacji. Biblioteka TPL skaluje stopień współbieżności dynamicznie, aby jak najefektywniej wykorzystać wszystkie dostępne procesory. Ponadto TPL obsługuje partycjonowanie pracy, planowanie wątków w usłudze <xref:System.Threading.ThreadPool> , zarządzanie stanami, a także inne szczegóły niskiego poziomu. Za pomocą TPL można zmaksymalizować wydajność kodu przy jednoczesnym skoncentrowaniu się na pracy, którą program ma wykonać.  
  
 Począwszy od .NET Framework 4, TPL jest preferowanym sposobem pisania kodu wielowątkowego i równoległego. Jednak nie wszystkie kody są odpowiednie dla przetwarzanie równoległe. Na przykład jeśli pętla wykonuje tylko niewielką ilość pracy dla każdej iteracji lub nie działa dla wielu iteracji, obciążenie przetwarzanie równoległe może spowodować spowolnienie działania kodu. Ponadto przetwarzanie równoległe, jak każdy kod wielowątkowy, dodaje złożoności do wykonywania programu. Chociaż TPL upraszcza scenariusze wielowątkowe, zalecamy przynajmniej podstawowe zrozumienie pojęcia wątkowości, na przykład blokad, zakleszczeń i sytuacje wyścigu, aby skutecznie korzystać z TPL.  
  
## <a name="related-articles"></a>Pokrewne artykuły:  
  
|Tytuł|Opis|  
|-|-|  
|[Równoległość danych](data-parallelism-task-parallel-library.md)|Opisuje sposób tworzenia równoległych `for` i `foreach` wielopętly ( `For` i `For Each` w Visual Basic).|  
|[Programowanie asynchroniczne oparte na zadaniach](task-based-asynchronous-programming.md)|Opisuje sposób tworzenia i uruchamiania zadań niejawnie przy użyciu <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> lub jawnie przy użyciu <xref:System.Threading.Tasks.Task> obiektów bezpośrednio.|  
|[Przepływ danych](dataflow-task-parallel-library.md)|Opisuje, jak używać składników przepływu danych w bibliotece przepływu danych TPL w celu obsługi wielu operacji, które muszą się komunikować ze sobą, lub w celu przetwarzania danych, gdy tylko staną się dostępne.|
|[Potencjalne pułapki związane z równoległością danych i zadań](potential-pitfalls-in-data-and-task-parallelism.md)|Opisuje kilka typowych pułapek oraz sposoby unikania ich.|  
|[Równoległe LINQ (PLINQ)](introduction-to-plinq.md)|Opisuje sposób osiągnięcia równoległości danych za pomocą zapytań LINQ.|  
|[Programowanie równoległe](index.md)|Węzeł najwyższego poziomu dla równoległego programowania .NET.|  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady programowania równoległego przy użyciu programu .NET Core & .NET Standard](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
