---
title: ReadOnly
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 3ca322da4e5f0edcbe12bf29bded863daabffe3d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867703"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="8330a-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8330a-102">ReadOnly (Visual Basic)</span></span>

<span data-ttu-id="8330a-103">Określa, że zmienna lub właściwość może być odczytana, ale nie zapisywana.</span><span class="sxs-lookup"><span data-stu-id="8330a-103">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="8330a-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8330a-104">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="8330a-105">Reguły</span><span class="sxs-lookup"><span data-stu-id="8330a-105">Rules</span></span>

- <span data-ttu-id="8330a-106">**Kontekst deklaracji.**</span><span class="sxs-lookup"><span data-stu-id="8330a-106">**Declaration Context.**</span></span> <span data-ttu-id="8330a-107">Można używać `ReadOnly` tylko na poziomie modułu.</span><span class="sxs-lookup"><span data-stu-id="8330a-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="8330a-108">Oznacza to, że kontekst deklaracji dla `ReadOnly` elementu musi być klasą, strukturą lub modułem, i nie może być plikiem źródłowym, przestrzenią nazw ani procedurą.</span><span class="sxs-lookup"><span data-stu-id="8330a-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="8330a-109">**Połączone modyfikatory.**</span><span class="sxs-lookup"><span data-stu-id="8330a-109">**Combined Modifiers.**</span></span> <span data-ttu-id="8330a-110">Nie można określić `ReadOnly` razem z `Static` w tej samej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="8330a-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="8330a-111">**Przypisywanie wartości.**</span><span class="sxs-lookup"><span data-stu-id="8330a-111">**Assigning a Value.**</span></span> <span data-ttu-id="8330a-112">Kod zużywający `ReadOnly` Właściwość nie może mieć ustawionej wartości.</span><span class="sxs-lookup"><span data-stu-id="8330a-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="8330a-113">Jednak kod, który ma dostęp do magazynu bazowego, może przypisywać lub zmieniać wartość w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="8330a-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="8330a-114">Można przypisać wartość do `ReadOnly` zmiennej tylko w swojej deklaracji lub w konstruktorze klasy lub struktury, w której jest zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="8330a-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="8330a-115">Kiedy używać zmiennej tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="8330a-115">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="8330a-116">Istnieją sytuacje, w których nie można użyć [instrukcji const](../statements/const-statement.md) do zadeklarowania i przypisania wartości stałej.</span><span class="sxs-lookup"><span data-stu-id="8330a-116">There are situations in which you cannot use a [Const Statement](../statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="8330a-117">Na przykład `Const` instrukcja może nie akceptować typu danych, który chcesz przypisać, lub nie można obliczyć wartości w czasie kompilacji przy użyciu wyrażenia stałej.</span><span class="sxs-lookup"><span data-stu-id="8330a-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="8330a-118">Wartość w czasie kompilacji może nie być jeszcze znana.</span><span class="sxs-lookup"><span data-stu-id="8330a-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="8330a-119">W takich przypadkach można użyć `ReadOnly` zmiennej do przechowywania wartości stałej.</span><span class="sxs-lookup"><span data-stu-id="8330a-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8330a-120">Jeśli typ danych zmiennej jest typem referencyjnym, takim jak tablica lub wystąpienie klasy, jego elementy członkowskie można zmienić, nawet jeśli sama zmienna jest `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="8330a-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="8330a-121">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="8330a-121">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="8330a-122">Po zainicjowaniu tablica wskazywana przez `characterArray()` zawiera wartości "x", "y" i "z".</span><span class="sxs-lookup"><span data-stu-id="8330a-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="8330a-123">Ponieważ zmienna `characterArray` to `ReadOnly` , nie można zmienić jej wartości, gdy jest ona zainicjowana; oznacza to, że nie można przypisać do niej nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="8330a-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="8330a-124">Można jednak zmienić wartości co najmniej jednego elementu członkowskiego tablicy.</span><span class="sxs-lookup"><span data-stu-id="8330a-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="8330a-125">Po wywołaniu procedury `ChangeArrayElement` Tablica wskazywana przez `characterArray()` posiada "x", "M" i "z".</span><span class="sxs-lookup"><span data-stu-id="8330a-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="8330a-126">Należy zauważyć, że jest to podobne do deklarowania parametru procedury jako [ByVal](byval.md), co uniemożliwia procedury zmiany argumentu wywołującego, ale pozwala na zmianę jego elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="8330a-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="8330a-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="8330a-127">Example</span></span>

<span data-ttu-id="8330a-128">W poniższym przykładzie zdefiniowano `ReadOnly` Właściwość dla daty zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="8330a-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="8330a-129">Klasa przechowuje wartość właściwości wewnętrznie jako `Private` zmienną i tylko kod wewnątrz klasy może zmienić tę wartość.</span><span class="sxs-lookup"><span data-stu-id="8330a-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="8330a-130">Jednak właściwość jest `Public` , a każdy kod, który może uzyskać dostęp do klasy, może odczytać właściwość.</span><span class="sxs-lookup"><span data-stu-id="8330a-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="8330a-131">`ReadOnly`Modyfikator może być używany w tych kontekstach:</span><span class="sxs-lookup"><span data-stu-id="8330a-131">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="8330a-132">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="8330a-132">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="8330a-133">Property — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="8330a-133">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="8330a-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8330a-134">See also</span></span>

- [<span data-ttu-id="8330a-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="8330a-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="8330a-136">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="8330a-136">Keywords</span></span>](../keywords/index.md)
