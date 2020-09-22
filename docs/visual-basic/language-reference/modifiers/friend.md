---
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: d37a93343822d069295477958780c2b9c72043fa
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875467"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="3162c-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3162c-102">Friend (Visual Basic)</span></span>

<span data-ttu-id="3162c-103">Określa, że co najmniej jeden zadeklarowany element programistyczny jest dostępny tylko w obrębie zestawu, który zawiera jego deklarację.</span><span class="sxs-lookup"><span data-stu-id="3162c-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3162c-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3162c-104">Remarks</span></span>  

 <span data-ttu-id="3162c-105">W wielu przypadkach elementy programowania, takie jak klasy i struktury, mają być używane przez cały zestaw, nie tylko przez składnik, który deklaruje je.</span><span class="sxs-lookup"><span data-stu-id="3162c-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="3162c-106">Jednak użytkownik może nie chcieć uzyskiwać dostępu przez kod poza zestawem (na przykład jeśli aplikacja jest zastrzeżona).</span><span class="sxs-lookup"><span data-stu-id="3162c-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="3162c-107">Jeśli chcesz ograniczyć dostęp do elementu w ten sposób, możesz go zadeklarować za pomocą `Friend` modyfikatora.</span><span class="sxs-lookup"><span data-stu-id="3162c-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="3162c-108">Kod w innych klasach, strukturach i modułach, które są kompilowane do tego samego zestawu, mogą uzyskać dostęp do wszystkich `Friend` elementów w tym zestawie.</span><span class="sxs-lookup"><span data-stu-id="3162c-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="3162c-109">`Friend` dostęp jest często preferowanym poziomem dla elementów programistycznych aplikacji i `Friend` jest domyślnym poziomem dostępu do interfejsu, modułu, klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="3162c-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="3162c-110">Można używać `Friend` tylko na poziomie modułu, interfejsu lub przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="3162c-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="3162c-111">W związku z tym kontekst deklaracji dla `Friend` elementu musi być plikiem źródłowym, przestrzenią nazw, interfejsem, modułem, klasą lub strukturą. nie może to być procedura.</span><span class="sxs-lookup"><span data-stu-id="3162c-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="3162c-112">Można również użyć modyfikatora [Protected Friend](protected-friend.md) Access, który sprawia, że element członkowski klasy jest dostępny z tej klasy, z klas pochodnych i z tego samego zestawu, w którym jest zdefiniowana Klasa.</span><span class="sxs-lookup"><span data-stu-id="3162c-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="3162c-113">Aby ograniczyć dostęp do elementu członkowskiego z poziomu jego klasy i z klas pochodnych w tym samym zestawie, należy użyć modyfikatora [Private Protected](private-protected.md) Access.</span><span class="sxs-lookup"><span data-stu-id="3162c-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="3162c-114">Aby uzyskać porównanie `Friend` i inne Modyfikatory dostępu, zobacz [poziomy dostępu w Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3162c-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3162c-115">Można określić, że inny zestaw jest zestawem zaprzyjaźnionym, który umożliwia mu dostęp do wszystkich typów i elementów członkowskich, które są oznaczone jako `Friend` .</span><span class="sxs-lookup"><span data-stu-id="3162c-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="3162c-116">Aby uzyskać więcej informacji, zobacz [zaprzyjaźnione zestawy](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="3162c-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="3162c-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="3162c-117">Example</span></span>  

 <span data-ttu-id="3162c-118">Poniższa klasa używa `Friend` modyfikatora, aby zezwolić innym elementom programistycznym w tym samym zestawie na dostęp do niektórych elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="3162c-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="3162c-119">Użycie</span><span class="sxs-lookup"><span data-stu-id="3162c-119">Usage</span></span>  

 <span data-ttu-id="3162c-120">Modyfikatora można użyć `Friend` w tych kontekstach:</span><span class="sxs-lookup"><span data-stu-id="3162c-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="3162c-121">Class, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-121">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="3162c-122">Const, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-122">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="3162c-123">Declare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-123">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="3162c-124">Delegate — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-124">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="3162c-125">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-125">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="3162c-126">Enum, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-126">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="3162c-127">Event — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-127">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="3162c-128">Function, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-128">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="3162c-129">Interface, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-129">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="3162c-130">Module — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-130">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="3162c-131">Property — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-131">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="3162c-132">Structure — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-132">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="3162c-133">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="3162c-133">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3162c-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3162c-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="3162c-135">Publiczne</span><span class="sxs-lookup"><span data-stu-id="3162c-135">Public</span></span>](public.md)
- [<span data-ttu-id="3162c-136">Chronione</span><span class="sxs-lookup"><span data-stu-id="3162c-136">Protected</span></span>](protected.md)
- [<span data-ttu-id="3162c-137">Prywatne</span><span class="sxs-lookup"><span data-stu-id="3162c-137">Private</span></span>](private.md)
- [<span data-ttu-id="3162c-138">Prywatne chronione</span><span class="sxs-lookup"><span data-stu-id="3162c-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="3162c-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="3162c-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="3162c-140">Poziomy dostępu w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3162c-140">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="3162c-141">Procedury</span><span class="sxs-lookup"><span data-stu-id="3162c-141">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="3162c-142">Struktury</span><span class="sxs-lookup"><span data-stu-id="3162c-142">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3162c-143">Obiekty i klasy</span><span class="sxs-lookup"><span data-stu-id="3162c-143">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
