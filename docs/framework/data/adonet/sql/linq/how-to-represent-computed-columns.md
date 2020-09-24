---
title: 'Instrukcje: Reprezentacja kolumn obliczanych'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: d952a6c22cd96bbc89aeebfa4b13e9727a363c73
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166329"
---
# <a name="how-to-represent-computed-columns"></a>Instrukcje: Reprezentacja kolumn obliczanych

Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> właściwości dla atrybutu, <xref:System.Data.Linq.Mapping.ColumnAttribute> aby reprezentować kolumnę, której zawartość jest wynikiem obliczania.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> .  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Program nie obsługuje kolumn obliczanych jako kluczy podstawowych.  
  
### <a name="to-represent-a-computed-column"></a>Aby przedstawić kolumnę obliczaną  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Przypisz ciąg reprezentujący formułę do <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> właściwości.  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
