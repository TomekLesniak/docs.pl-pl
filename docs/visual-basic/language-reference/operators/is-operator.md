---
title: IS — operator
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 1c2d87ef0a8202332c87af552f488d652c400213
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812266"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="dcac3-102">IS — operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcac3-102">Is operator (Visual Basic)</span></span>

<span data-ttu-id="dcac3-103">Porównuje dwie zmienne odwołań do obiektów.</span><span class="sxs-lookup"><span data-stu-id="dcac3-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcac3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dcac3-104">Syntax</span></span>

```vb
result = object1 Is object2
```

## <a name="parts"></a><span data-ttu-id="dcac3-105">Części</span><span class="sxs-lookup"><span data-stu-id="dcac3-105">Parts</span></span>

 `result`  
 <span data-ttu-id="dcac3-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="dcac3-106">Required.</span></span> <span data-ttu-id="dcac3-107">Dowolna `Boolean` wartość.</span><span class="sxs-lookup"><span data-stu-id="dcac3-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="dcac3-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="dcac3-108">Required.</span></span> <span data-ttu-id="dcac3-109">Dowolna `Object` nazwa.</span><span class="sxs-lookup"><span data-stu-id="dcac3-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="dcac3-110">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="dcac3-110">Required.</span></span> <span data-ttu-id="dcac3-111">Dowolna `Object` nazwa.</span><span class="sxs-lookup"><span data-stu-id="dcac3-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcac3-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dcac3-112">Remarks</span></span>

<span data-ttu-id="dcac3-113">`Is`Operator określa, czy dwa odwołania do obiektów odwołują się do tego samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="dcac3-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="dcac3-114">Jednak nie wykonuje porównania wartości.</span><span class="sxs-lookup"><span data-stu-id="dcac3-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="dcac3-115">Jeśli `object1` i `object2` oba odnoszą się do dokładnie tego samego wystąpienia obiektu, `result` to `True` ; Jeśli nie, `result` to `False` .</span><span class="sxs-lookup"><span data-stu-id="dcac3-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>

> [!NOTE]
> <span data-ttu-id="dcac3-116">`Is`Słowo kluczowe jest również używane w [SELECT... Case — instrukcja](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dcac3-116">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="dcac3-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="dcac3-117">Example</span></span>

<span data-ttu-id="dcac3-118">Poniższy przykład używa `Is` operatora do porównywania par odwołań do obiektów.</span><span class="sxs-lookup"><span data-stu-id="dcac3-118">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="dcac3-119">Wyniki są przypisane do `Boolean` wartości reprezentującej, czy dwa obiekty są identyczne.</span><span class="sxs-lookup"><span data-stu-id="dcac3-119">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

<span data-ttu-id="dcac3-120">Jak pokazano w powyższym przykładzie, można użyć `Is` operatora do przetestowania zarówno obiektów wczesnych, jak i późnych powiązań.</span><span class="sxs-lookup"><span data-stu-id="dcac3-120">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>

## <a name="use-typeof-operator-with-is-operator"></a><span data-ttu-id="dcac3-121">Używaj operatora TypeOf z operatorem is</span><span class="sxs-lookup"><span data-stu-id="dcac3-121">Use TypeOf operator with Is operator</span></span>

<span data-ttu-id="dcac3-122">`Is` operatora można także użyć ze `TypeOf` słowem kluczowym, aby utworzyć `TypeOf` wyrażenie... `Is` , które sprawdza, czy zmienna obiektu jest zgodna z typem danych.</span><span class="sxs-lookup"><span data-stu-id="dcac3-122">`Is` operator can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span> <span data-ttu-id="dcac3-123">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="dcac3-123">For example:</span></span>

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a><span data-ttu-id="dcac3-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dcac3-124">See also</span></span>

- [<span data-ttu-id="dcac3-125">TypeOf — Operator</span><span class="sxs-lookup"><span data-stu-id="dcac3-125">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="dcac3-126">IsNot, operator</span><span class="sxs-lookup"><span data-stu-id="dcac3-126">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="dcac3-127">Operatory porównania w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dcac3-127">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="dcac3-128">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcac3-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="dcac3-129">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="dcac3-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="dcac3-130">Operatory i wyrażenia</span><span class="sxs-lookup"><span data-stu-id="dcac3-130">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
