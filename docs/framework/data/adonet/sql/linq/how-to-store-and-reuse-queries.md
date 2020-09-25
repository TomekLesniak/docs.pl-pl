---
title: 'Instrukcje: Przechowywanie i ponowne użycie zapytań'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: aae1cf3faf2ecb3d8e9511390cdaa1e004905bea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197095"
---
# <a name="how-to-store-and-reuse-queries"></a>Instrukcje: Przechowywanie i ponowne użycie zapytań

W przypadku aplikacji, która wielokrotnie wykonuje podobne zapytania strukturalnie, często można zwiększyć wydajność, kompilując zapytanie jeden raz i wykonując je kilka razy z innymi parametrami. Na przykład aplikacja może wymagać pobrania wszystkich klientów, którzy znajdują się w konkretnym mieście, gdzie miasto jest określone w czasie wykonywania przez użytkownika w formularzu. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje w tym celu użycie *skompilowanych zapytań* .  
  
> [!NOTE]
> Ten wzorzec użycia reprezentuje najczęstsze zastosowania skompilowanych zapytań. Możliwe jest inne podejście. Na przykład skompilowane zapytania mogą być przechowywane jako statyczne elementy członkowskie klasy częściowej, która rozszerza kod generowany przez projektanta.  
  
## <a name="example"></a>Przykład  

 W wielu scenariuszach możesz chcieć ponownie wykorzystać zapytania w granicach wątków. W takich przypadkach przechowywanie skompilowanych zapytań w zmiennych statycznych jest szczególnie skuteczne. W poniższym przykładzie kodu założono `Queries` klasę zaprojektowaną do przechowywania skompilowanych zapytań i przyjmujemy klasę Northwind, która reprezentuje silnie wpisaną wartość <xref:System.Data.Linq.DataContext> .  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>Przykład  

 Obecnie nie można przechowywać (w zmiennych statycznych) zapytań, które zwracają *Typ anonimowy*, ponieważ typ nie ma nazwy, która ma być argumentem ogólnym. Poniższy przykład pokazuje, jak można obejść ten problem, tworząc typ, który może reprezentować wynik, a następnie użyć go jako argumentu rodzajowego.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.Linq.CompiledQuery>
- [Pojęcia dotyczące zapytań](query-concepts.md)
- [wykonywanie zapytania w bazie danych](querying-the-database.md)
