---
description: '#Region — odwołanie w C#'
title: '#Region — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ed40d895fedb9be271bb389a4f8de69d7ae3f266
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137945"
---
# <a name="region-c-reference"></a>#region (odwołanie w C#)
`#region` umożliwia określenie bloku kodu, który można rozwijać lub zwijać podczas korzystania z funkcji tworzenia [konspektu](/visualstudio/ide/outlining) w edytorze kodu. W przypadku plików o większej liczbie można zwinąć lub ukryć jeden lub więcej regionów, aby można było skupić się na części pliku, nad którym pracujesz. Poniższy przykład pokazuje, jak zdefiniować region:  
  
```csharp
#region MyClass definition  
public class MyClass
{  
    static void Main()
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>Uwagi  
 `#region`Blok musi być zakończony przy użyciu dyrektywy [#endregion](./preprocessor-endregion.md) .  
  
 `#region`Blok nie może nakładać się na blok [#if](./preprocessor-if.md) . Jednak `#region` blok może być zagnieżdżony w `#if` bloku, a `#if` blok może być zagnieżdżony w `#region` bloku.  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
