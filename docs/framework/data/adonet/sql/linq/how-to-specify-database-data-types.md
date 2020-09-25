---
title: 'Instrukcje: Określanie typów danych bazy danych'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: f070ff718ac10b9681c5ab3c0f4b46547349101b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197238"
---
# <a name="how-to-specify-database-data-types"></a>Instrukcje: Określanie typów danych bazy danych

Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> właściwości dla atrybutu, <xref:System.Data.Linq.Mapping.ColumnAttribute> Aby określić dokładny tekst, który definiuje kolumnę w deklaracji tabeli T-SQL.  
  
 Właściwość należy określić <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> tylko wtedy, gdy planujesz użyć, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> Aby utworzyć wystąpienie bazy danych.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> .  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Aby określić tekst definiujący typ danych w tabeli T-SQL  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Ustaw wartość <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> właściwości na dokładny tekst, który jest używany przez język T-SQL.  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
