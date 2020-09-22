---
title: Distinct, klauzula
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875277"
---
# <a name="distinct-clause-visual-basic"></a>Distinct — Klauzula (Visual Basic)

Ogranicza wartości bieżącej zmiennej zakresu w celu wyeliminowania zduplikowanych wartości w kolejnych klauzulach zapytania.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Uwagi  

 Możesz użyć klauzuli, `Distinct` Aby zwrócić listę unikatowych elementów. `Distinct`Klauzula powoduje, że zapytanie ignoruje zduplikowane wyniki zapytania. `Distinct`Klauzula ma zastosowanie do zduplikowanych wartości dla wszystkich zwracanych pól określonych przez `Select` klauzulę. Jeśli `Select` klauzula nie jest określona, `Distinct` klauzula jest stosowana do zmiennej zakresu dla zapytania określonego w `From` klauzuli. Jeśli zmienna zakresu nie jest niezmiennym typem, zapytanie zignoruje tylko wynik zapytania, jeśli wszystkie elementy członkowskie tego typu pasują do istniejącego wyniku zapytania.  
  
## <a name="example"></a>Przykład  

 Poniższe wyrażenie zapytania dołącza listę klientów i listę zamówień klientów. `Distinct`Klauzula jest uwzględniona w celu zwrócenia listy unikatowych nazw klientów i dat kolejności.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do LINQ w Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Zapytania](index.md)
- [Klauzula from](from-clause.md)
- [SELECT — klauzula](select-clause.md)
- [Klauzula WHERE](where-clause.md)
