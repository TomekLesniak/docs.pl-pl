---
description: '#undef — odwołanie w C#'
title: '#undef — odwołanie w C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 97f99ab4230585e61fed0e057552b78c7a4c2bb5
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137867"
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
