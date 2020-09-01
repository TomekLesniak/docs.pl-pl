---
description: Typy odwołań — odwołanie w C#
title: Typy odwołań — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 1a9df3c95d6f5052821be8db5ecf5a8ed99a8ba7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137061"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="d967f-103">Typy odwołań (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="d967f-103">Reference types (C# Reference)</span></span>

<span data-ttu-id="d967f-104">Istnieją dwa rodzaje typów w języku C#: typy referencyjne i typy wartości.</span><span class="sxs-lookup"><span data-stu-id="d967f-104">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="d967f-105">W zmiennych typu referencyjnego są przechowywane odwołania do ich danych (obiekty), a zmienne typu wartości zawierają bezpośrednio swoje dane.</span><span class="sxs-lookup"><span data-stu-id="d967f-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="d967f-106">W przypadku typów referencyjnych dwie zmienne mogą odwoływać się do jednego obiektu, a więc operacje wykonane na jednej zmiennych mogą mieć wpływ na obiekt, do którego odwołuje się druga zmienna.</span><span class="sxs-lookup"><span data-stu-id="d967f-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="d967f-107">W przypadku typów wartości Każda zmienna ma własną kopię danych i nie jest możliwe wykonywanie operacji na jednej zmiennej, która ma wpływ na drugą (z wyjątkiem w przypadku zmiennych parametrów ref i out; zobacz [w](in-parameter-modifier.md), modyfikator parametru [ref](ref.md) i [out](out-parameter-modifier.md) ).</span><span class="sxs-lookup"><span data-stu-id="d967f-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="d967f-108">Do deklarowania typów referencyjnych są używane następujące słowa kluczowe:</span><span class="sxs-lookup"><span data-stu-id="d967f-108">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="d967f-109">określonej</span><span class="sxs-lookup"><span data-stu-id="d967f-109">class</span></span>](class.md)

- [<span data-ttu-id="d967f-110">interfejsu</span><span class="sxs-lookup"><span data-stu-id="d967f-110">interface</span></span>](interface.md)

- [<span data-ttu-id="d967f-111">Wierz</span><span class="sxs-lookup"><span data-stu-id="d967f-111">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="d967f-112">W języku C# są także dostępne następujące wbudowane typy referencyjne:</span><span class="sxs-lookup"><span data-stu-id="d967f-112">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="d967f-113">dynamiczna</span><span class="sxs-lookup"><span data-stu-id="d967f-113">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="d967f-114">Stream</span><span class="sxs-lookup"><span data-stu-id="d967f-114">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="d967f-115">parametry</span><span class="sxs-lookup"><span data-stu-id="d967f-115">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="d967f-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d967f-116">See also</span></span>

- [<span data-ttu-id="d967f-117">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="d967f-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d967f-118">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="d967f-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d967f-119">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="d967f-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="d967f-120">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="d967f-120">Value types</span></span>](../builtin-types/value-types.md)
