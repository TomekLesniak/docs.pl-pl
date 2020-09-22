---
title: Take, klauzula
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: f2377d8d1635912885a310b2b0429a6a00083b47
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869669"
---
# <a name="take-clause-visual-basic"></a>Take — Klauzula (Visual Basic)

Zwraca określoną liczbę elementów sąsiadujących od początku kolekcji.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Części  

 `count`  
 Wymagany. Wartość lub wyrażenie, które oblicza liczbę elementów sekwencji do zwrócenia.  
  
## <a name="remarks"></a>Uwagi  

 `Take`Klauzula powoduje, że zapytanie zawiera określoną liczbę elementów sąsiadujących od początku listy wyników. Liczba elementów do dołączenia jest określona przez `count` parametr.  
  
 Można użyć `Take` klauzuli z `Skip` klauzulą, aby zwrócić zakres danych z dowolnego segmentu zapytania. Aby to zrobić, Przekaż indeks pierwszego elementu zakresu do `Skip` klauzuli i rozmiar zakresu do `Take` klauzuli. W takim przypadku `Take` klauzula musi być określona po `Skip` klauzuli.  
  
 W przypadku używania `Take` klauzuli w zapytaniu może być również konieczne upewnienie się, że wyniki są zwracane w kolejności, w której `Take` klauzula będzie zawierać zamierzone wyniki. Aby uzyskać więcej informacji na temat porządkowania wyników zapytania, zobacz [klauzula Order by](order-by-clause.md).  
  
 Można użyć `TakeWhile` klauzuli, aby określić, że tylko niektóre elementy mają być zwracane, w zależności od podanego warunku.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład kodu używa `Take` klauzuli razem z `Skip` klauzulą, aby zwrócić dane ze zapytania na stronach. Funkcja getcustomerss używa `Skip` klauzuli do obejścia klientów na liście do momentu podanej wartości indeksu początkowego i użycia `Take` klauzuli do zwrócenia strony klientów zaczynających się od tej wartości indeksu.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do LINQ w Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Zapytania](index.md)
- [SELECT — klauzula](select-clause.md)
- [Klauzula from](from-clause.md)
- [Klauzula Order by](order-by-clause.md)
- [Take While, klauzula](take-while-clause.md)
- [Skip, klauzula](skip-clause.md)
