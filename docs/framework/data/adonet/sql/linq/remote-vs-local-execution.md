---
title: Zdalne a lokalne wykonanie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: c99e726902192fc8324e77441b80aa4519c55ddc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196952"
---
# <a name="remote-vs-local-execution"></a>Zdalne a lokalne wykonanie

Możesz zdecydować się na zdalne wykonywanie zapytań (to oznacza, że aparat bazy danych wykonuje zapytanie względem bazy danych) lub lokalnie ( [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wykonuje zapytanie względem lokalnej pamięci podręcznej).  
  
## <a name="remote-execution"></a>Zdalne wykonywanie kodu  

 Rozpatrzmy następujące zapytanie:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Jeśli baza danych ma tysiące rzędów zamówień, nie chcesz pobierać ich wszystkich, aby przetwarzać mały podzestaw. W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.EntitySet%601> Klasa implementuje <xref:System.Linq.IQueryable> interfejs. Takie podejście gwarantuje, że takie zapytania można wykonać zdalnie. Przepływ dwóch głównych korzyści z tej techniki:  
  
- Nie pobrano zbędnych danych.  
  
- Zapytanie wykonywane przez aparat bazy danych jest często wydajniejsze ze względu na indeksy bazy danych.  
  
## <a name="local-execution"></a>lokalne wykonanie  

 W innych sytuacjach może być konieczne posiadanie kompletnego zestawu powiązanych jednostek w lokalnej pamięci podręcznej. W tym celu <xref:System.Data.Linq.EntitySet%601> zapewnia metodę, <xref:System.Data.Linq.EntitySet%601.Load%2A> Aby jawnie załadować wszystkie elementy członkowskie <xref:System.Data.Linq.EntitySet%601> .  
  
 Jeśli <xref:System.Data.Linq.EntitySet%601> jest już załadowany, kolejne zapytania są wykonywane lokalnie. To podejście jest pomocne na dwa sposoby:  
  
- Jeśli kompletny zestaw musi być używany lokalnie lub wiele razy, można uniknąć zdalnych zapytań i skojarzonych opóźnień.  
  
- Jednostkę można serializować jako kompletną jednostkę.  
  
 Poniższy fragment kodu ilustruje sposób uzyskania lokalnego wykonania:  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a>Porównanie  

 Te dwie możliwości oferują zaawansowaną kombinację opcji: zdalne wykonywanie dużych kolekcji i wykonywanie lokalne dla małych kolekcji lub, gdzie jest wymagana kompletna kolekcja. Implementowanie zdalnego wykonywania przez <xref:System.Linq.IQueryable> program i wykonywanie lokalne w odniesieniu do <xref:System.Collections.Generic.IEnumerable%601> kolekcji w pamięci. Aby wymusić wykonanie lokalne (czyli <xref:System.Collections.Generic.IEnumerable%601> ), zobacz [konwertowanie typu na rodzajowy interfejs IEnumerable](convert-a-type-to-a-generic-ienumerable.md).  
  
### <a name="queries-against-unordered-sets"></a>Zapytania dotyczące nieuporządkowanych zestawów  

 Należy zwrócić uwagę na istotną różnicę między lokalną kolekcją, która implementuje <xref:System.Collections.Generic.List%601> i kolekcję, która zapewnia zapytania zdalne wykonywane w odniesieniu do *nieuporządkowanych zestawów* w relacyjnej bazie danych. <xref:System.Collections.Generic.List%601> metody, takie jak te, które używają wartości indeksu, wymagają semantyki list, która zazwyczaj nie można uzyskać za pomocą zapytania zdalnego dla nieuporządkowanego zestawu. Z tego powodu takie metody niejawnie ładują, <xref:System.Data.Linq.EntitySet%601> Aby umożliwić wykonanie lokalne.  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
