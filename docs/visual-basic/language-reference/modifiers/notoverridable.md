---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 8eec54a12c7fb748df46e8c48a8b07eab983cc72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867866"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="023c6-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="023c6-102">NotOverridable (Visual Basic)</span></span>

<span data-ttu-id="023c6-103">Określa, że właściwość lub procedura nie może zostać zastąpiona w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="023c6-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="023c6-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="023c6-104">Remarks</span></span>  

 <span data-ttu-id="023c6-105">`NotOverridable`Modyfikator uniemożliwia przesłanianie właściwości lub metody w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="023c6-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="023c6-106">Modyfikator [, który umożliwia](overridable.md) zastąpienie właściwości lub metody w klasie klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="023c6-106">The [Overridable](overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="023c6-107">Aby uzyskać więcej informacji, zobacz podstawowe informacje o [dziedziczeniu](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="023c6-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="023c6-108">Jeśli `Overridable` modyfikator or `NotOverridable` nie jest określony, ustawienie domyślne zależy od tego, czy właściwość lub metoda przesłania właściwość lub metodę klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="023c6-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="023c6-109">Jeśli właściwość lub metoda przesłania właściwość lub metodę klasy bazowej, ustawienie domyślne to `Overridable` ; w przeciwnym razie jest `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="023c6-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="023c6-110">Element, który nie może zostać zastąpiony, jest czasami nazywany *zapieczętowanym* elementem.</span><span class="sxs-lookup"><span data-stu-id="023c6-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="023c6-111">Można użyć `NotOverridable` tylko w instrukcji deklaracji właściwości lub procedury.</span><span class="sxs-lookup"><span data-stu-id="023c6-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="023c6-112">Można określić `NotOverridable` tylko dla właściwości lub procedury, która zastępuje inną właściwość lub procedurę, czyli tylko w połączeniu z `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="023c6-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="023c6-113">Połączone Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="023c6-113">Combined Modifiers</span></span>  

 <span data-ttu-id="023c6-114">Nie można określić `Overridable` lub `NotOverridable` dla `Private` metody.</span><span class="sxs-lookup"><span data-stu-id="023c6-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="023c6-115">Nie można określić `NotOverridable` razem z `MustOverride` , `Overridable` , lub `Shared` w tej samej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="023c6-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="023c6-116">Użycie</span><span class="sxs-lookup"><span data-stu-id="023c6-116">Usage</span></span>  

 <span data-ttu-id="023c6-117">`NotOverridable`Modyfikator może być używany w tych kontekstach:</span><span class="sxs-lookup"><span data-stu-id="023c6-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="023c6-118">Function, instrukcja</span><span class="sxs-lookup"><span data-stu-id="023c6-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="023c6-119">Property — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="023c6-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="023c6-120">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="023c6-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="023c6-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="023c6-121">See also</span></span>

- [<span data-ttu-id="023c6-122">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="023c6-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="023c6-123">Podstawowe informacje o dziedziczeniu</span><span class="sxs-lookup"><span data-stu-id="023c6-123">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="023c6-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="023c6-124">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="023c6-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="023c6-125">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="023c6-126">Przesłonięcia</span><span class="sxs-lookup"><span data-stu-id="023c6-126">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="023c6-127">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="023c6-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="023c6-128">Przesłanianie w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="023c6-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
