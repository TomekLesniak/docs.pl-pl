---
title: Typy wyjątków
description: 'Dowiedz się, jak definiować i używać typów wyjątków języka F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557232"
---
# <a name="exception-types"></a><span data-ttu-id="229cf-103">Typy wyjątków</span><span class="sxs-lookup"><span data-stu-id="229cf-103">Exception Types</span></span>

<span data-ttu-id="229cf-104">Istnieją dwie kategorie wyjątków w języku F #: typy wyjątków platformy .NET i typy wyjątków języka F #.</span><span class="sxs-lookup"><span data-stu-id="229cf-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="229cf-105">W tym temacie opisano sposób definiowania typów wyjątków języka F # i używania ich.</span><span class="sxs-lookup"><span data-stu-id="229cf-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="229cf-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="229cf-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="229cf-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="229cf-107">Remarks</span></span>

<span data-ttu-id="229cf-108">W poprzedniej składni *Typ wyjątku* to nazwa nowego typu wyjątku F #, a *argument-type* reprezentuje typ argumentu, który może być dostarczony podczas zgłaszania wyjątku tego typu.</span><span class="sxs-lookup"><span data-stu-id="229cf-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="229cf-109">Można określić wiele argumentów za pomocą typu krotki dla *typu argumentu*.</span><span class="sxs-lookup"><span data-stu-id="229cf-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="229cf-110">Typowa definicja wyjątku języka F # jest podobna do poniższego.</span><span class="sxs-lookup"><span data-stu-id="229cf-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="229cf-111">Wyjątek tego typu można wygenerować przy użyciu `raise` funkcji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="229cf-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="229cf-112">Możesz użyć typu wyjątku F # bezpośrednio w filtrach w `try...with` wyrażeniu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="229cf-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="229cf-113">Typ wyjątku zdefiniowany za pomocą `exception` słowa kluczowego w F # to nowy typ, który dziedziczy po `System.Exception` .</span><span class="sxs-lookup"><span data-stu-id="229cf-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="229cf-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="229cf-114">See also</span></span>

- [<span data-ttu-id="229cf-115">Obsługa wyjątków</span><span class="sxs-lookup"><span data-stu-id="229cf-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="229cf-116">Wyjątki: `raise` Funkcja</span><span class="sxs-lookup"><span data-stu-id="229cf-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="229cf-117">Hierarchia wyjątków</span><span class="sxs-lookup"><span data-stu-id="229cf-117">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
