---
title: 'Instrukcje: Filtrowanie powiązanych danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: e12bab55b03fac3383b98b8ee1c56ab1954ff978
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173461"
---
# <a name="how-to-filter-related-data"></a>Instrukcje: Filtrowanie powiązanych danych

Użyj <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> metody, aby określić podzapytania, aby ograniczyć ilość pobranych danych.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> Metoda ogranicza `Orders` pobrane elementy do tych, które nie zostały wysłane dzisiaj. Bez tego podejścia wszystkie `Orders` zostałyby pobrane, nawet jeśli pożądane jest tylko podzbiór.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [wykonywanie zapytania w bazie danych](querying-the-database.md)
