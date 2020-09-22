---
title: Let, klauzula
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: a6ff3fc80a2b6752c61a8b8f7d4ce62b5a46baad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869882"
---
# <a name="let-clause-visual-basic"></a>Let — Klauzula (Visual Basic)

Oblicza wartość i przypisuje ją do nowej zmiennej w zapytaniu.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Części  
  
|Termin|Definicja|  
|---|---|  
|`variable`|Wymagany. Alias, który może służyć do odwoływania się do wyników podanego wyrażenia.|  
|`expression`|Wymagany. Wyrażenie, które zostanie obliczone i przypisane do określonej zmiennej.|  
  
## <a name="remarks"></a>Uwagi  

 `Let`Klauzula umożliwia obliczanie wartości dla każdego wyniku zapytania i odwoływanie się do nich za pomocą aliasu. Alias może być używany w innych klauzulach, takich jak `Where` klauzula. `Let`Klauzula umożliwia utworzenie instrukcji zapytania, która jest łatwiejsza do odczytania, ponieważ można określić alias dla klauzuli Expression zawartej w zapytaniu i zastąpić alias za każdym razem, gdy używana jest klauzula wyrażenia.  
  
 W klauzuli można uwzględnić dowolną liczbę `variable` i `expression` przypisania `Let` . Każde przypisanie należy oddzielić przecinkami (,).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład kodu używa klauzuli, `Let` Aby obliczyć rabat 10% dla produktów.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do LINQ w Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Zapytania](index.md)
- [SELECT — klauzula](select-clause.md)
- [Klauzula from](from-clause.md)
- [Klauzula WHERE](where-clause.md)
