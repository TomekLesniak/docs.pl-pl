---
title: 'Instrukcje: Używanie procedur składowanych zamapowanych na sekwencyjne kształty wyników'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: a53b2afcfce33c654b06b237cc55ad966c030568
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184953"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Instrukcje: Używanie procedur składowanych zamapowanych na sekwencyjne kształty wyników

Ten rodzaj procedury składowanej może generować więcej niż jeden kształt wynikowy, ale wiadomo, w jakiej kolejności zwracane są wyniki. Ten scenariusz należy wykonać w scenariuszu, w którym nie jest znana sekwencja zwracanych wartości. Aby uzyskać więcej informacji, zobacz [How to: use procedur składowanych mapowanych na wiele kształtów wynikowych](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).  
  
## <a name="example"></a>Przykład  

 Poniżej znajduje się T-SQL procedury składowanej zwracającej wiele kształtów wyników sekwencyjnie:  
  
```sql
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Przykład  

 Aby wykonać tę procedurę składowaną, należy użyć kodu podobnego do poniższego.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Zobacz też

- [Procedury składowane](stored-procedures.md)
