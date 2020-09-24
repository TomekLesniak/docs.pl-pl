---
title: 'Instrukcje: Reprezentacja tabel jako klas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166225"
---
# <a name="how-to-represent-tables-as-classes"></a>Instrukcje: Reprezentacja tabel jako klas

Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atrybutu, aby wyznaczyć klasę jako klasę jednostki skojarzoną z tabelą bazy danych.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Aby zmapować klasę do tabeli bazy danych  
  
- Dodaj <xref:System.Data.Linq.Mapping.TableAttribute> atrybut do deklaracji klasy.  
  
## <a name="example"></a>Przykład  

 Poniższy kod tworzy `Customer` klasę jako klasę jednostki, która jest skojarzona z `Customers` tabelą bazy danych.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Nie trzeba określać <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> właściwości, jeśli można wywnioskować nazwę. Jeśli nie określisz nazwy, przyjmuje się, że nazwa jest taka sama jak nazwa właściwości lub pola.  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
