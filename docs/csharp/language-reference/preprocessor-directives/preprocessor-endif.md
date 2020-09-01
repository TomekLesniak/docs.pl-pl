---
description: '#endif — odwołanie w C#'
title: '#endif — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 8068a6e437145178fd5c88763c86692a8700c349
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138166"
---
# <a name="endif-c-reference"></a>#endif (odwołanie w C#)
`#endif` Określa koniec dyrektywy warunkowej, która zaczyna się od dyrektywy [#if](./preprocessor-if.md) . Przykład:  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Uwagi  
 Dyrektywa warunkowa, rozpoczynająca się od `#if` dyrektywy, musi zostać jawnie zakończona `#endif` dyrektywą. Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#endif` .  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
