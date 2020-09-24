---
title: 'Instrukcje: Reprezentacja kolumn jako wygenerowanych w bazie danych'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 914fdcb78efbaaddf08330e32e1d7f7c4e62436e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166316"
---
# <a name="how-to-represent-columns-as-database-generated"></a>Instrukcje: Reprezentacja kolumn jako wygenerowanych w bazie danych

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Właściwość w <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybucie służy do wyznaczania pola lub właściwości reprezentującej kolumnę wygenerowaną przez bazę danych.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> .  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>Aby wyznaczyć pole lub właściwość reprezentującą kolumnę wygenerowaną przez bazę danych  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Ustaw wartość właściwości na `true` .  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
