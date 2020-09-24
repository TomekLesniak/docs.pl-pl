---
title: 'Instrukcje: Reprezentacja kluczy podstawowych'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 02570176c8aef5cfdc7ba09fd6976f430900e8df
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166238"
---
# <a name="how-to-represent-primary-keys"></a>Instrukcje: Reprezentacja kluczy podstawowych

Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> właściwości w atrybucie, <xref:System.Data.Linq.Mapping.ColumnAttribute> Aby wyznaczyć właściwość lub pole reprezentujące klucz podstawowy dla kolumny bazy danych.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> .  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Program nie obsługuje kolumn obliczanych jako kluczy podstawowych.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Aby wyznaczyć właściwość lub pole jako klucz podstawowy  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Określ wartość jako `true` .  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
