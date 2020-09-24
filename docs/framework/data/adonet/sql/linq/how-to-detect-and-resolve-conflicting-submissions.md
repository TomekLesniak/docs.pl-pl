---
title: 'Instrukcje: Wykrywanie i rozwiązywanie powodujących konflikt przesłań'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147726"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Instrukcje: Wykrywanie i rozwiązywanie powodujących konflikt przesłań

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] oferuje wiele zasobów do wykrywania i rozwiązywania konfliktów, które pochodzą od zmian wielu użytkowników w bazie danych. Aby uzyskać więcej informacji, zobacz [How to: Manage konflikts Change](how-to-manage-change-conflicts.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje `try` / `catch` blok, który przechwytuje <xref:System.Data.Linq.ChangeConflictException> wyjątek. Informacje o jednostkach i elementach członkowskich dla każdego konfliktu są wyświetlane w oknie konsoli.  
  
> [!NOTE]
> Musisz dołączyć `using System.Reflection` dyrektywę ( `Imports System.Reflection` w Visual Basic) do obsługi pobierania informacji. Aby uzyskać więcej informacji, zobacz <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
- [Instrukcje: Zarządzanie konfliktami zmian](how-to-manage-change-conflicts.md)
