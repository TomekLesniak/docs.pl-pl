---
title: 'Instrukcje: Reprezentacja kolumn jako elementów członkowskich klas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: e73b017b5a500a8c48b3fe22557f6c6619f3b227
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166355"
---
# <a name="how-to-represent-columns-as-class-members"></a>Instrukcje: Reprezentacja kolumn jako elementów członkowskich klas

Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu, aby skojarzyć pole lub właściwość z kolumną bazy danych.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Aby zmapować pole lub właściwość do kolumny bazy danych  
  
- Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybut do deklaracji właściwości lub pola.  
  
## <a name="example"></a>Przykład  

 Poniższy kod mapuje `CustomerID` pole w `Customer` klasie do `CustomerID` kolumny w `Customers` tabeli bazy danych.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Nie trzeba określać <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> właściwości, jeśli można wywnioskować nazwę. Jeśli nie określisz nazwy, przyjmuje się, że nazwa jest taka sama jak nazwa właściwości lub pola.  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
