---
description: '#pragma warning — odwołanie w C#'
title: '#pragma warning — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5b67d384e37a5e509ce8ebcc5ddeb16a4437ea2b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91168533"
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
  
## <a name="see-also"></a>Zobacz także

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
- [Błędy kompilatora C#](../compiler-messages/index.md)
