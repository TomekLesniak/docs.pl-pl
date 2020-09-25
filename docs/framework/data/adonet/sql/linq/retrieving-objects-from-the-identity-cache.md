---
title: Pobieranie obiektów z pamięci podręcznej tożsamości
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: 457e11ddad16ca3be55f53f03c480b0e464ab38f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200397"
---
# <a name="retrieving-objects-from-the-identity-cache"></a>Pobieranie obiektów z pamięci podręcznej tożsamości

W tym temacie opisano typy zapytań LINQ to SQL, które zwracają obiekt z pamięci podręcznej tożsamości, która jest zarządzana przez program <xref:System.Data.Linq.DataContext> .  
  
 W LINQ to SQL jednym ze sposobów <xref:System.Data.Linq.DataContext> zarządzania obiektami zarządza tożsamość obiektów w pamięci podręcznej tożsamości, gdy są wykonywane zapytania. W niektórych przypadkach LINQ to SQL spróbuje pobrać obiekt z pamięci podręcznej tożsamości przed wykonaniem zapytania w bazie danych.  
  
 Ogólnie rzecz biorąc, aby kwerenda LINQ to SQL zwracała obiekt z pamięci podręcznej tożsamości, zapytanie musi być oparte na kluczu podstawowym obiektu i musi zwrócić pojedynczy obiekt. W szczególności zapytanie musi znajdować się w jednym z formularzy ogólnych przedstawionych poniżej.  
  
> [!NOTE]
> Wstępnie skompilowane zapytania nie będą zwracać obiektów z pamięci podręcznej tożsamości. Aby uzyskać więcej informacji na temat wstępnie skompilowanych zapytań, zobacz <xref:System.Data.Linq.CompiledQuery> i [instrukcje: przechowywanie i ponowne używanie zapytań](how-to-store-and-reuse-queries.md).  
  
 Zapytanie musi znajdować się w jednym z następujących formularzy ogólnych, aby pobrać obiekt z pamięci podręcznej tożsamości:  
  
- <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`  
  
- <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`  
  
 W tych ogólnych formularzach `Function1` , `Function2` i `predicate` są zdefiniowane w następujący sposób.  
  
 `Function1` może to być dowolny z następujących elementów:  
  
- <xref:System.Linq.Queryable.Where%2A>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `Function2` może to być dowolny z następujących elementów:  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `predicate` musi być wyrażeniem, w którym Właściwość klucz podstawowy obiektu ma ustawioną wartość stałą. Jeśli obiekt ma klucz podstawowy zdefiniowany przez więcej niż jedną właściwość, Każda właściwość klucza podstawowego musi być ustawiona na wartość stałą. Poniżej przedstawiono przykłady formularza, które `predicate` należy wykonać:  
  
- `c => c.PK == constant_value`  
  
- `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a>Przykład  

 Poniższy kod zawiera przykłady typów zapytań LINQ to SQL, które pobierają obiekt z pamięci podręcznej tożsamości.  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
- [Tożsamość obiektu](object-identity.md)
- [Informacje uzupełniające](background-information.md)
- [Tożsamość obiektu](object-identity.md)
