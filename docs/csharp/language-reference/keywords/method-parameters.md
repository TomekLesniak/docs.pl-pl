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
# <a name="method-parameters-c-reference"></a><span data-ttu-id="b55d4-103">Parametry metody (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="b55d4-103">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="b55d4-104">Parametry zadeklarowane dla metody bez elementu [in](./in-parameter-modifier.md), [ref](./ref.md) lub [out](./out-parameter-modifier.md)są przesyłane do metody wywoływanej przez wartość.</span><span class="sxs-lookup"><span data-stu-id="b55d4-104">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="b55d4-105">Tę wartość można zmienić w metodzie, ale zmieniona wartość nie będzie zachowywana, gdy kontrola przechodzi z powrotem do procedury wywołującej.</span><span class="sxs-lookup"><span data-stu-id="b55d4-105">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="b55d4-106">Za pomocą słowa kluczowego Parameter metody można zmienić to zachowanie.</span><span class="sxs-lookup"><span data-stu-id="b55d4-106">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="b55d4-107">W tej sekcji opisano słowa kluczowe, których można użyć podczas deklarowania parametrów metody:</span><span class="sxs-lookup"><span data-stu-id="b55d4-107">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="b55d4-108">[params](./params.md) określa, że ten parametr może przyjmować zmienną liczbę argumentów.</span><span class="sxs-lookup"><span data-stu-id="b55d4-108">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="b55d4-109">[w programie](./in-parameter-modifier.md) określa, że ten parametr jest przesyłany przez odwołanie, ale jest odczytywany tylko przez wywołaną metodę.</span><span class="sxs-lookup"><span data-stu-id="b55d4-109">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="b55d4-110">[ref](./ref.md) określa, że ten parametr jest przesyłany przez odwołanie i może być odczytywany lub zapisywana przez wywołaną metodę.</span><span class="sxs-lookup"><span data-stu-id="b55d4-110">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="b55d4-111">[określa,](./out-parameter-modifier.md) że ten parametr jest przesyłany przez odwołanie i jest zapisywana przez wywołaną metodę.</span><span class="sxs-lookup"><span data-stu-id="b55d4-111">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b55d4-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b55d4-112">See also</span></span>

- [<span data-ttu-id="b55d4-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="b55d4-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b55d4-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b55d4-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b55d4-115">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="b55d4-115">C# Keywords</span></span>](./index.md)
