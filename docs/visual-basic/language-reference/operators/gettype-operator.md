---
title: GetType, operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 9ff207ea4f2b89ea30eb8f46a3e640ccf3789974
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867010"
---
# <a name="gettype-operator-visual-basic"></a>GetType — Operator (Visual Basic)

Zwraca <xref:System.Type> obiekt dla określonego typu. <xref:System.Type>Obiekt zawiera informacje o typie, takim jak jego właściwości, metody i zdarzenia.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parametry  
  
|Parametr|Opis|  
|---|---|  
|`typename`|Nazwa typu, dla którego chcesz uzyskać informacje.|  
  
## <a name="remarks"></a>Uwagi  

 `GetType`Operator zwraca <xref:System.Type> obiekt dla określonego elementu `typename` . Można przekazać nazwę dowolnego zdefiniowanego typu w `typename` . Uwzględnione są następujące elementy:  
  
- Dowolny Visual Basic typ danych, taki jak `Boolean` lub `Date` .  
  
- Wszystkie .NET Framework klasy, struktury, modułu lub interfejsu, takie jak <xref:System.ArgumentException?displayProperty=nameWithType> lub <xref:System.Double?displayProperty=nameWithType> .  
  
- Wszystkie klasy, struktury, moduły lub interfejsy zdefiniowane przez aplikację.  
  
- Dowolna tablica zdefiniowana przez aplikację.  
  
- Każdy delegat zdefiniowany przez aplikację.  
  
- Każde Wyliczenie zdefiniowane przez Visual Basic, .NET Framework lub aplikację.  
  
 Jeśli chcesz uzyskać obiekt typu zmiennej obiektu, użyj <xref:System.Type.GetType%2A?displayProperty=nameWithType> metody.  
  
 `GetType`Operator może być przydatny w następujących sytuacjach:  
  
- Należy uzyskać dostęp do metadanych dla typu w czasie wykonywania. <xref:System.Type>Obiekt dostarcza metadane, takie jak elementy członkowskie typu i informacje o wdrożeniu. Jest to konieczne, na przykład w celu odzwierciedlenia zestawu. Aby uzyskać więcej informacji, zobacz <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Chcesz porównać dwa odwołania do obiektów, aby sprawdzić, czy odwołują się do wystąpień tego samego typu. Jeśli tak, `GetType` zwraca odwołania do tego samego <xref:System.Type> obiektu.  
  
## <a name="example"></a>Przykład  

 W poniższych przykładach pokazano `GetType` operator w użyciu.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Zobacz też

- [Kolejność wykonywania działań (Visual Basic)](operator-precedence.md)
- [Operatory według funkcji](operators-listed-by-functionality.md)
- [Operatory i wyrażenia](../../programming-guide/language-features/operators-and-expressions/index.md)
