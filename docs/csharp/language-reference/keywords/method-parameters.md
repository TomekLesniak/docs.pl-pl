---
description: Parametry metody — odwołanie w C#
title: Parametry metody — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 7090bf1c3df65cf1e65942404f883b49612e7521
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134409"
---
# <a name="method-parameters-c-reference"></a>Parametry metody (odwołanie w C#)

Parametry zadeklarowane dla metody bez elementu [in](./in-parameter-modifier.md), [ref](./ref.md) lub [out](./out-parameter-modifier.md)są przesyłane do metody wywoływanej przez wartość. Tę wartość można zmienić w metodzie, ale zmieniona wartość nie będzie zachowywana, gdy kontrola przechodzi z powrotem do procedury wywołującej. Za pomocą słowa kluczowego Parameter metody można zmienić to zachowanie.  
  
 W tej sekcji opisano słowa kluczowe, których można użyć podczas deklarowania parametrów metody:  
  
- [params](./params.md) określa, że ten parametr może przyjmować zmienną liczbę argumentów.
  
- [w programie](./in-parameter-modifier.md) określa, że ten parametr jest przesyłany przez odwołanie, ale jest odczytywany tylko przez wywołaną metodę.
  
- [ref](./ref.md) określa, że ten parametr jest przesyłany przez odwołanie i może być odczytywany lub zapisywana przez wywołaną metodę.
  
- [określa,](./out-parameter-modifier.md) że ten parametr jest przesyłany przez odwołanie i jest zapisywana przez wywołaną metodę.
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
