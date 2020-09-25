---
title: 'Instrukcje: Określanie sprawdzania konfliktów współbieżności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: 7adacdccd12c6493ff7c62c0e6a44058a9719d7d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197212"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a>Instrukcje: Określanie sprawdzania konfliktów współbieżności

Można określić, które kolumny bazy danych mają być sprawdzane pod kątem konfliktów współbieżności podczas wywoływania <xref:System.Data.Linq.DataContext.SubmitChanges%2A> . Aby uzyskać więcej informacji, zobacz [How to: Określanie, które elementy członkowskie są testowane pod kątem konfliktów współbieżności](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
## <a name="example"></a>Przykład  

 Poniższy kod określa, że `HomePage` element członkowski nigdy nie powinien być testowany podczas sprawdzania aktualizacji. Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
