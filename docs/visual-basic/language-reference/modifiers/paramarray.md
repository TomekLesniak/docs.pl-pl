---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: baf9303101eea9eed27e8a4eee9e04d255c798e9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867823"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)

Określa, że parametr procedury przyjmuje opcjonalną tablicę elementów określonego typu. `ParamArray` może być używany tylko dla ostatniego parametru listy parametrów.  
  
## <a name="remarks"></a>Uwagi  

 `ParamArray` umożliwia przekazanie dowolnej liczby argumentów do procedury. `ParamArray`Parametr jest zawsze deklarowany przy użyciu [ByVal](byval.md).  
  
 Można podać jeden lub więcej argumentów do parametru, `ParamArray` przekazując tablicę odpowiedniego typu danych, rozdzielaną przecinkami listę wartości lub nic wcale. Aby uzyskać szczegółowe informacje, zobacz "wywoływanie ParamArray" w [tablicach parametrów](../../programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Za każdym razem, gdy zajmujesz się tablicą, która może być nienieskończona, istnieje ryzyko, że zachodzi taka Wewnętrzna pojemność aplikacji. Jeśli zaakceptujesz tablicę parametrów z kodu wywołującego, należy przetestować jego długość i wykonać odpowiednie czynności, jeśli jest ono zbyt duże dla aplikacji.  
  
 `ParamArray`Modyfikator może być używany w tych kontekstach:  
  
 [Declare — Instrukcja](../statements/declare-statement.md)  
  
 [Function, instrukcja](../statements/function-statement.md)  
  
 [Property — Instrukcja](../statements/property-statement.md)  
  
 [Sub, instrukcja](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Zobacz też

- [Słowa kluczowe](../keywords/index.md)
- [Parameter — Tablice](../../programming-guide/language-features/procedures/parameter-arrays.md)
