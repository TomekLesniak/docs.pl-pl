---
title: 'Instrukcje: Kontrolowanie, ile jest pobieranych powiązanych danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: 77ac29eeeaa30ef438b635364dc8e883a0e4c158
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161337"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a>Instrukcje: Kontrolowanie, ile jest pobieranych powiązanych danych

Użyj <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> metody, aby określić, które dane związane z głównym miejscem docelowym powinny być pobierane w tym samym czasie. Jeśli na przykład wiesz, że potrzebujesz informacji o zamówieniach klientów, możesz użyć <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> programu, aby upewnić się, że informacje o zamówieniach są pobierane w tym samym czasie co informacje o kliencie. To podejście powoduje tylko jedną podróż do bazy danych dla obu zestawów informacji.  
  
> [!NOTE]
> Dane związane z głównym celem zapytania można pobrać, pobierając jeden z wielu produktów, takich jak pobieranie zamówień w przypadku docelowych klientów. Ale takie podejście często ma wady. Na przykład wyniki są tylko projekcjami, a nie jednostkami, które mogą być zmieniane i utrwalane przez program [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . Możesz też pobrać wiele niepotrzebnych danych.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie wszystkie `Orders` dla wszystkich osób, które znajdują się `Customers` w Londynie, są pobierane po wykonaniu zapytania. W efekcie dostęp do `Orders` właściwości na `Customer` obiekcie nie wyzwala nowej kwerendy bazy danych.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [wykonywanie zapytania w bazie danych](querying-the-database.md)
