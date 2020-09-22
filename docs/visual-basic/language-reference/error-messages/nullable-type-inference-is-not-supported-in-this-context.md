---
title: Wnioskowanie typu zerowalnego nie jest obsługiwane w tym kontekście
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: f2d3bcdaccfd993da1eebf81ae961f35eb22b294
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873674"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Wnioskowanie typu zerowalnego nie jest obsługiwane w tym kontekście

Typy wartości i struktury mogą być deklarowane jako dopuszczające wartość null.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Nie można jednak używać deklaracji wartości null w połączeniu z wnioskami o typie. Poniższe przykłady powodują wystąpienie tego błędu.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Identyfikator błędu:** BC36629  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Użyj `As` klauzuli, aby zadeklarować zmienną jako typ wartości null.  
  
## <a name="see-also"></a>Zobacz też

- [Typy wartości null](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Wnioskowanie o typie lokalnym](../../programming-guide/language-features/variables/local-type-inference.md)
