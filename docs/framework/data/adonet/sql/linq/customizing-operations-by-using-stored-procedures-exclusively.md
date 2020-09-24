---
title: Dostosowywanie operacji przy użyciu wyłącznie procedur składowanych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 78db5cf448a19056d7265ab84d97d055748c3faa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164327"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Dostosowywanie operacji przy użyciu wyłącznie procedur składowanych

Dostęp do danych za pomocą tylko procedur składowanych jest typowym scenariuszem.  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  

 Możesz zmodyfikować przykład podany w temacie [Dostosowywanie operacji za pomocą procedur składowanych](customizing-operations-by-using-stored-procedures.md) , zastępując nawet pierwsze zapytanie (co powoduje dynamiczne wykonywanie kodu SQL) z wywołaniem metody, które zawija procedurę składowaną.  
  
 Załóżmy `CustomersByCity` , że jest to metoda, jak w poniższym przykładzie.  
  
### <a name="code"></a>Kod  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Poniższy kod jest wykonywany bez żadnego dynamicznego języka SQL.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Zobacz też

- [Obowiązki dewelopera podczas zastępowania domyślnego zachowania](responsibilities-of-the-developer-in-overriding-default-behavior.md)
