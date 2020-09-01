---
description: '#pragma warning — odwołanie w C#'
title: '#pragma warning — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 3085c21db386ca215d48bbe8ade83cd26732242c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137971"
---
# <a name="pragma-warning-c-reference"></a>#pragma warning (odwołanie w C#)
`#pragma warning` można włączać lub wyłączać pewne ostrzeżenia.  
  
## <a name="syntax"></a>Składnia  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a>Parametry  
 `warning-list`  
 Rozdzielana przecinkami lista numerów ostrzeżeń. Prefiks "CS" jest opcjonalny.  
  
 Gdy nie określono żadnych numerów ostrzeżeń, program `disable` wyłącza wszystkie ostrzeżenia i `restore` włącza wszystkie ostrzeżenia.  
  
> [!NOTE]
> Aby znaleźć numery ostrzegawcze w programie Visual Studio, Skompiluj projekt, a następnie poszukaj numerów ostrzeżeń w oknie **danych wyjściowych** .  
  
## <a name="example"></a>Przykład  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
- [Błędy kompilatora C#](../compiler-messages/index.md)
