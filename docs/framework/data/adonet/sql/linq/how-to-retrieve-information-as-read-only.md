---
title: 'Instrukcje: Pobieranie informacji jako tylko do odczytu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 0a6853ef5d0b67e5efb95731adb5a106e8701e0f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155838"
---
# <a name="how-to-retrieve-information-as-read-only"></a>Instrukcje: Pobieranie informacji jako tylko do odczytu

Jeśli nie zamierzasz zmieniać danych, możesz zwiększyć wydajność zapytań, wyszukując wyniki tylko do odczytu.  
  
 Przetwarzanie w trybie tylko do odczytu jest implementowane przez ustawienie <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> do `false` .  
  
> [!NOTE]
> Gdy <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> jest ustawiona na `false` , <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> jest niejawnie ustawiona na `false` .  
  
## <a name="example"></a>Przykład  

 Poniższy kod pobiera kolekcję dat zatrudnienia pracowników w trybie tylko do odczytu.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
- [wykonywanie zapytania w bazie danych](querying-the-database.md)
- [Odroczone a bezpośrednie ładowanie](deferred-versus-immediate-loading.md)
