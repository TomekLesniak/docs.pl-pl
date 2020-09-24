---
description: '#undef — odwołanie w C#'
title: '#undef — odwołanie w C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 7db79be7ea9d8462e09b6ae874bf0ae7d265afe2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150560"
---
# <a name="undef-c-reference"></a>#undef (odwołanie w C#)

`#undef` umożliwia oddefiniowanie symbolu, takiego, że, przy użyciu symbolu jako wyrażenia w dyrektywie [#if](./preprocessor-if.md) , wyrażenie zwróci wartość `false` .  
  
 Symbol można zdefiniować za pomocą dyrektywy [#define](./preprocessor-define.md) lub opcji [-define](../compiler-options/define-compiler-option.md) kompilatora. `#undef`Dyrektywa musi znajdować się w pliku przed użyciem wszelkich instrukcji, które nie są również dyrektywami.  
  
## <a name="example"></a>Przykład  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

**Nie zdefiniowano debugowania**

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
