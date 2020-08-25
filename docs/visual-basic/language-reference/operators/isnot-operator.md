---
title: Operator IsNot
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811044"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="3a2ad-102">IsNot — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a2ad-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="3a2ad-103">Porównuje dwie zmienne odwołań do obiektów.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a2ad-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3a2ad-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="3a2ad-105">Części</span><span class="sxs-lookup"><span data-stu-id="3a2ad-105">Parts</span></span>

- `result`

  <span data-ttu-id="3a2ad-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-106">Required.</span></span> <span data-ttu-id="3a2ad-107">`Boolean`Wartość.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-107">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="3a2ad-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-108">Required.</span></span> <span data-ttu-id="3a2ad-109">Dowolna `Object` zmienna lub wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-109">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="3a2ad-110">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-110">Required.</span></span> <span data-ttu-id="3a2ad-111">Dowolna `Object` zmienna lub wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a2ad-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3a2ad-112">Remarks</span></span>

<span data-ttu-id="3a2ad-113">`IsNot`Operator określa, czy dwa odwołania do obiektów odwołują się do różnych obiektów.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="3a2ad-114">Jednak nie wykonuje porównania wartości.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-114">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="3a2ad-115">Jeśli `object1` i `object2` oba odnoszą się do dokładnie tego samego wystąpienia obiektu, `result` to `False` ; Jeśli nie, `result` to `True` .</span><span class="sxs-lookup"><span data-stu-id="3a2ad-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="3a2ad-116">`IsNot` jest przeciwieństwem `Is` operatora.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="3a2ad-117">Zaletą `IsNot` jest to, że można uniknąć niewygodna składni z `Not` i `Is` , co może być trudne do odczytania.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="3a2ad-118">Operatory i służą `Is` `IsNot` do testowania zarówno obiektów wczesnych, jak i z późnym wiązaniem.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="3a2ad-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="3a2ad-119">Example</span></span>

<span data-ttu-id="3a2ad-120">Poniższy przykład kodu używa `Is` operatora i `IsNot` operatora, aby wykonać to samo porównanie.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="3a2ad-121">Użycie operatora TypeOf z operatorem IsNot</span><span class="sxs-lookup"><span data-stu-id="3a2ad-121">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="3a2ad-122">Rozpoczynając od Visual Basic 14, można użyć `TypeOf` operatora z `IsNot` operatorem, aby sprawdzić, czy obiekt *nie* jest zgodny z typem danych.</span><span class="sxs-lookup"><span data-stu-id="3a2ad-122">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="3a2ad-123">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="3a2ad-123">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="3a2ad-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a2ad-124">See also</span></span>

- [<span data-ttu-id="3a2ad-125">Is, operator</span><span class="sxs-lookup"><span data-stu-id="3a2ad-125">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="3a2ad-126">TypeOf — Operator</span><span class="sxs-lookup"><span data-stu-id="3a2ad-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="3a2ad-127">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a2ad-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="3a2ad-128">Porady: testowanie, czy dwa obiekty są takie same</span><span class="sxs-lookup"><span data-stu-id="3a2ad-128">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
