---
title: 'Instrukcje: Wyświetlanie wygenerowanego kodu SQL'
description: Dowiedz się, jak wyświetlić kod SQL wygenerowany dla zapytań za pomocą właściwości log, aby pomóc zrozumieć LINQ to SQL funkcje i debugowanie.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 81f6b9603cc7f8b7863f787272ce6a1af920fa75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169495"
---
# <a name="how-to-display-generated-sql"></a>Instrukcje: Wyświetlanie wygenerowanego kodu SQL

Można wyświetlić kod SQL wygenerowany dla zapytań i przetwarzania zmian przy użyciu <xref:System.Data.Linq.DataContext.Log%2A> właściwości. Takie podejście może być przydatne w przypadku znajomości [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] funkcjonalności i debugowania określonych problemów.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa właściwości, <xref:System.Data.Linq.DataContext.Log%2A> Aby wyświetlić kod SQL w oknie konsoli przed wykonaniem kodu.  Tej właściwości można użyć z poleceniami Query, INSERT, Update i DELETE.  
  
 Wiersze z okna konsoli są wyświetlane podczas wykonywania poniższego kodu Visual Basic lub C#.  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Obsługa debugowania](debugging-support.md)
