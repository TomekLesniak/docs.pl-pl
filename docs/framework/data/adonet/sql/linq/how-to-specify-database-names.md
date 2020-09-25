---
title: 'Instrukcje: Określanie nazw bazy danych'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 82cb3f8f31af433b0299b4fec742b548d61921e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197160"
---
# <a name="how-to-specify-database-names"></a>Instrukcje: Określanie nazw bazy danych

Użyj <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> właściwości dla atrybutu, <xref:System.Data.Linq.Mapping.DatabaseAttribute> Aby określić nazwę bazy danych, gdy nazwa nie jest dostarczana przez połączenie.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> .  
  
### <a name="to-specify-the-name-of-the-database"></a>Aby określić nazwę bazy danych  
  
1. Dodaj <xref:System.Data.Linq.Mapping.DatabaseAttribute> atrybut do deklaracji klasy dla bazy danych.  
  
2. Dodaj <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> Właściwość do <xref:System.Data.Linq.Mapping.DatabaseAttribute> atrybutu.  
  
3. Ustaw <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> wartość właściwości na nazwę, która ma zostać określona.  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
