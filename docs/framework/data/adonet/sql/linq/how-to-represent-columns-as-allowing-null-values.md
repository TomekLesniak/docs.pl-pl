---
title: 'Instrukcje: Reprezentacja kolumn jako dopuszczających wartości Null'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: ec88429ed9c1f91917476cc807bd6b53f0bcc3a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166368"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Instrukcje: Reprezentacja kolumn jako dopuszczających wartości Null

Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> właściwości w atrybucie, <xref:System.Data.Linq.Mapping.ColumnAttribute> Aby określić, że skojarzona kolumna bazy danych może zawierać wartości null.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> .  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>Aby wyznaczyć kolumnę jako zezwalającą na wartości null  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> wartość właściwości na `true` .  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
