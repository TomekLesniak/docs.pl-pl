---
title: 'Instrukcje: Wyświetlanie zestawu zmian'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 288920567db75dc1d4c7273f698467063af52ed6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180780"
---
# <a name="how-to-display-a-changeset"></a>Instrukcje: Wyświetlanie zestawu zmian

Zmiany śledzone przez program można wyświetlić za <xref:System.Data.Linq.DataContext> pomocą polecenia <xref:System.Data.Linq.DataContext.GetChangeSet%2A> .  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pobiera klientów, których miasto jest Londyn, zmienia miasto na Paryż i przesyła zmiany z powrotem do bazy danych.  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 Dane wyjściowe z tego kodu są podobne do poniższych. Należy zauważyć, że podsumowanie na końcu pokazuje, że wprowadzono osiem zmian.  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a>Zobacz też

- [Obsługa debugowania](debugging-support.md)
