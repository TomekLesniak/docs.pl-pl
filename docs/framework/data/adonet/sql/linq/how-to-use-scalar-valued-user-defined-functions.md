---
title: 'Instrukcje: Używanie funkcji skalarnej zdefiniowanej przez użytkownika'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: faf8d6e94c88575f6cb73003fa5bed87650d7d54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196939"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Instrukcje: Używanie funkcji skalarnej zdefiniowanej przez użytkownika

Można zmapować metodę klienta zdefiniowaną w klasie do funkcji zdefiniowanej przez użytkownika przy użyciu <xref:System.Data.Linq.Mapping.FunctionAttribute> atrybutu. Należy zauważyć, że treść metody konstruuje wyrażenie, które przechwytuje zamiar wywołania metody i przekazuje to wyrażenie do <xref:System.Data.Linq.DataContext> translacji i wykonywania.  
  
> [!NOTE]
> Bezpośrednie wykonanie odbywa się tylko wtedy, gdy funkcja jest wywoływana poza zapytaniem. Aby uzyskać więcej informacji, zobacz [How to: Call User-Defined Functions inline](how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Przykład  

 Poniższy kod SQL przedstawia funkcję skalarną zdefiniowaną przez użytkownika `ReverseCustName()` .  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 Należy zmapować metodę klienta, na przykład następujące dla tego kodu:  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Funkcje zdefiniowane przez użytkownika](user-defined-functions.md)
