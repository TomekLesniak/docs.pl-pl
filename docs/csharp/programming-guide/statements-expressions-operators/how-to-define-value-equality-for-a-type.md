---
title: Jak zdefiniować równość wartości dla Przewodnik programowania typu C#
description: Dowiedz się, jak zdefiniować równość wartości dla typu. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- overriding Equals method [C#]
- object equivalence [C#]
- Equals method [C#], overriding
- value equality [C#]
- equivalence [C#]
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
ms.openlocfilehash: cf4449618c2b57f21855354f2250d41a403b4d57
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381648"
---
# <a name="how-to-define-value-equality-for-a-type-c-programming-guide"></a>Jak zdefiniować równość wartości dla typu (Przewodnik programowania w języku C#)

Podczas definiowania klasy lub struktury należy zdecydować, czy warto utworzyć niestandardową definicję równości (lub równoważności) dla typu. Zazwyczaj należy zaimplementować równość wartości, gdy obiekty typu powinny być dodawane do kolekcji niektórych rodzajów sortowania, lub gdy ich głównym celem jest przechowywanie zestawu pól lub właściwości. Można oprzeć swoją definicję równości wartości na porównaniu wszystkich pól i właściwości w typie lub oprzeć definicję w podzbiorze.

W obu przypadkach i w obu klasach i strukturach implementacja powinna być zgodna z pięcioma gwarancjami równoważności (w przypadku następujących zasad przyjęto założenie, że `x` `y` i `z` nie są puste):  
  
1. `x.Equals(x)`Zwraca wartość `true` . Jest to nazywane właściwością zwrotną.  
  
2. `x.Equals(y)`zwraca tę samą wartość, co `y.Equals(x)` . Jest to nazywane właściwością symetrycznymi.  
  
3. `(x.Equals(y) && y.Equals(z))`zwraca wartość `true` , a następnie `x.Equals(z)` zwraca `true` . Jest to nazywane właściwością przechodnią.  
  
4. Kolejne wywołania `x.Equals(y)` zwracające tę samą wartość, o ile obiekty przywoływane przez x i y nie są modyfikowane.  
  
5. Wartość inna niż null nie jest równa null. Jednak środowisko CLR sprawdza obecność wartości null we wszystkich wywołaniach metod i zgłasza, jeśli odwołanie będzie miało `NullReferenceException` `this` wartość null. W związku z tym `x.Equals(y)` zgłasza wyjątek, gdy `x` ma wartość null. Powoduje to przerwanie reguł 1 lub 2, w zależności od argumentu `Equals` .

 Każda zdefiniowana struktura ma już domyślną implementację wartości równość, która dziedziczy po <xref:System.ValueType?displayProperty=nameWithType> przesłonięciu <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> metody. Ta implementacja używa odbicia w celu sprawdzenia wszystkich pól i właściwości w typie. Mimo że ta implementacja daje poprawne wyniki, jest stosunkowo mała w porównaniu z implementacją niestandardową, która jest przeznaczona dla danego typu.  
  
 Szczegóły implementacji dotyczące równości wartości są różne dla klas i struktur. Jednak obie klasy i struktury wymagają tych samych podstawowych kroków w celu wdrożenia równości:  
  
1. Zastąp metodę [wirtualną](../../language-reference/keywords/virtual.md) <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> . W większości przypadków implementacja `bool Equals( object obj )` powinna być tylko wywoływana do metody specyficznej dla typu `Equals` , która jest implementacją <xref:System.IEquatable%601?displayProperty=nameWithType> interfejsu. (Zobacz krok 2).  
  
2. Zaimplementuj <xref:System.IEquatable%601?displayProperty=nameWithType> interfejs, dostarczając metodę specyficzną dla typu `Equals` . Jest to miejsce, w którym jest wykonywane rzeczywiste porównanie równoważności. Na przykład można określić równość, porównując tylko jedno lub dwa pola w typie. Nie zgłaszaj wyjątków z programu `Equals` . Tylko dla klas: Ta metoda powinna analizować tylko pola, które są zadeklarowane w klasie. Powinno to wywołać `base.Equals` , aby przeanalizować pola, które znajdują się w klasie bazowej. (Nie należy tego robić, jeśli typ dziedziczy bezpośrednio z <xref:System.Object> , ponieważ <xref:System.Object> implementacja <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> wykonuje sprawdzanie równości odwołań).  
  
3. Opcjonalne, ale zalecane: przeciążanie [==](../../language-reference/operators/equality-operators.md#equality-operator-) operatorów i [! =](../../language-reference/operators/equality-operators.md#inequality-operator-) .  
  
4. Przesłoń, <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType> Aby dwa obiekty, które mają równość wartości dawały ten sam kod skrótu.  
  
5. Opcjonalne: aby obsługiwać definicje "większe niż" lub "mniejsze niż", Implementuj <xref:System.IComparable%601> interfejs dla danego typu, a także przeciążać [<=](../../language-reference/operators/comparison-operators.md#less-than-or-equal-operator-) Operatory i [>=](../../language-reference/operators/comparison-operators.md#greater-than-or-equal-operator-) .  
  
 Pierwszy Poniższy przykład pokazuje implementację klasy. W drugim przykładzie przedstawiono implementację struktury.  

## <a name="example"></a>Przykład

 Poniższy przykład pokazuje, jak zaimplementować równość wartości w klasie (typ referencyjny).  
  
 [!code-csharp[csProgGuideStatements#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#19)]  
  
 W przypadku klas (typów referencyjnych) Domyślna implementacja obu <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> metod wykonuje porównanie równości odwołań, a nie sprawdzanie równości wartości. Gdy Realizator zastępuje metodę wirtualną, celem jest przyznanie semantyki równości wartości IT.  
  
 `==`Operatory i `!=` mogą być używane z klasami, nawet jeśli Klasa nie przeciąża ich. Jednak domyślnym zachowaniem jest wykonanie kontroli równości odwołań. W przypadku przeciążenia metody w klasie należy `Equals` przeciążać `==` `!=` Operatory i, ale nie jest to wymagane.  

## <a name="example"></a>Przykład

 Poniższy przykład pokazuje, jak zaimplementować równość wartości w strukturze (typ wartości):  
  
 [!code-csharp[csProgGuideStatements#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#20)]  
  
 W przypadku struktur domyślna implementacja <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> (która jest zastępowana wersja w programie <xref:System.ValueType?displayProperty=nameWithType> ) służy do sprawdzania równości wartości przy użyciu odbicia w celu porównania wartości każdego pola w typie. Gdy Realizator zastępuje `Equals` metodę wirtualną w strukturze, celem jest zapewnienie wydajniejszej kontroli równości wartości i, opcjonalnie, przeprowadzenie porównania w przypadku niektórych podzestawów pól lub właściwości struktury.  
  
 [==](../../language-reference/operators/equality-operators.md#equality-operator-)Operatory and [! =](../../language-reference/operators/equality-operators.md#inequality-operator-) nie mogą działać w strukturze, chyba że struktura jawnie przeciąża je.  
  
## <a name="see-also"></a>Zobacz też

- [Porównywanie równości](equality-comparisons.md)
- [Przewodnik programowania w języku C#](../index.md)
