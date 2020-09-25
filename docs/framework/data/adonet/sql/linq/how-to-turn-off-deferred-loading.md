---
title: 'Instrukcje: Wyłączanie odroczonego ładowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: b2193e7e8bda396451274d2da96e7cb86774fd03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196965"
---
# <a name="how-to-turn-off-deferred-loading"></a>Instrukcje: Wyłączanie odroczonego ładowania

Można wyłączyć odroczone ładowanie według ustawienia <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> do `false` . Aby uzyskać więcej informacji, zobacz [odroczone względem natychmiastowego ładowania](deferred-versus-immediate-loading.md).  
  
> [!NOTE]
> Ładowanie odroczone jest wyłączone przez implikację, gdy śledzenie obiektów jest wyłączone. Aby uzyskać więcej informacji, zobacz [jak: pobrać informacje jako tylko do odczytu](how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak wyłączyć odroczone ładowanie przez ustawienie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> do `false` .  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
- [wykonywanie zapytania w bazie danych](querying-the-database.md)
