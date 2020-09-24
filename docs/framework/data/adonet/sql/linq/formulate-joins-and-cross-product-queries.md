---
title: Formułowanie połączeń i zapytań między produktami
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 1527ad26524dbef3ac73b92e136cd22e33046483
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155890"
---
# <a name="formulate-joins-and-cross-product-queries"></a>Formułowanie połączeń i zapytań między produktami

W poniższych przykładach pokazano, jak połączyć wyniki z wielu tabel.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa nawigacji klucza obcego w `From` klauzuli w Visual Basic ( `from` klauzula w języku C#), aby wybrać wszystkie zamówienia dla klientów w Londynie.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie jest używana Nawigacja klucza obcego w `Where` klauzuli w Visual Basic ( `where` klauzula w języku C#), aby odfiltrować elementy poza magazynem `Products` `Supplier` , których wartość znajduje się w Stany Zjednoczone.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa nawigacji klucza obcego w `From` klauzuli w Visual Basic ( `from` klauzula w języku C#) do filtrowania pracowników w Seattle i wyświetlania ich terytoriów.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie jest używana Nawigacja klucza obcego w `Select` klauzuli w Visual Basic ( `select` klauzula w języku C#), aby odfiltrować pary pracowników, w których jeden pracownik zgłosi się do drugiego i gdy obaj pracownicy są z tego samego `City` .  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>Przykład  

 Poniższy Visual Basic przykład szuka wszystkich klientów i zamówień, upewnia się, że zamówienia są dopasowane do klientów i gwarantuje, że dla każdego klienta na tej liście zostanie podana nazwa kontaktu.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład jawnie łączy dwie tabele i projekty w obu tabelach.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład jawnie sprzęga trzy tabele i projekty z każdego z nich.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak osiągnąć za `LEFT OUTER JOIN` pomocą `DefaultIfEmpty()` . `DefaultIfEmpty()`Metoda zwraca wartość null, jeśli nie ma `Order` dla elementu `Employee` .  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład tworzy w projekcie `let` wyrażenie wynikłe z sprzężenia.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład przedstawia `join` z kluczem złożonym.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak utworzyć miejsce, `join` gdzie jedna strona ma wartość null, a druga nie.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
