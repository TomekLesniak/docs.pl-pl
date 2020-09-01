---
description: Poziomy ułatwień dostępu — odwołanie w C#
title: Poziomy ułatwień dostępu — odwołanie w C#
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26b8f78595b1406deb371113cf491b80ad7c1474
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127025"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="53d36-103">Poziomy ułatwień dostępu (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="53d36-103">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="53d36-104">Użyj modyfikatorów dostępu,, `public` , `protected` `internal` lub `private` , aby określić jeden z następujących zadeklarowanych poziomów dostępności dla elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="53d36-104">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="53d36-105">Zadeklarowane ułatwienia dostępu</span><span class="sxs-lookup"><span data-stu-id="53d36-105">Declared accessibility</span></span>|<span data-ttu-id="53d36-106">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="53d36-106">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="53d36-107">Dostęp nie jest ograniczony.</span><span class="sxs-lookup"><span data-stu-id="53d36-107">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="53d36-108">Dostęp jest ograniczony do zawierającej klasy lub typów pochodzących od klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="53d36-108">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="53d36-109">Dostęp jest ograniczony do bieżącego zestawu.</span><span class="sxs-lookup"><span data-stu-id="53d36-109">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="53d36-110">Dostęp jest ograniczony do bieżącego zestawu lub typów pochodzących od klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="53d36-110">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="53d36-111">Dostęp jest ograniczony do typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="53d36-111">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="53d36-112">Dostęp jest ograniczony do zawierającej klasy lub typów pochodzących od klasy zawierającej w bieżącym zestawie.</span><span class="sxs-lookup"><span data-stu-id="53d36-112">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="53d36-113">Dostępne od języka C# 7,2.</span><span class="sxs-lookup"><span data-stu-id="53d36-113">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="53d36-114">Tylko jeden modyfikator dostępu jest dozwolony dla elementu członkowskiego lub typu, z wyjątkiem tego, że używane są `protected internal` `private protected` kombinacje lub.</span><span class="sxs-lookup"><span data-stu-id="53d36-114">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="53d36-115">Modyfikatory dostępu są niedozwolone w przestrzeniach nazw.</span><span class="sxs-lookup"><span data-stu-id="53d36-115">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="53d36-116">Przestrzenie nazw nie mają ograniczeń dostępu.</span><span class="sxs-lookup"><span data-stu-id="53d36-116">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="53d36-117">W zależności od kontekstu, w którym występuje Deklaracja elementu członkowskiego, dozwolone są tylko niektóre zadeklarowane podano.</span><span class="sxs-lookup"><span data-stu-id="53d36-117">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="53d36-118">Jeśli w deklaracji elementu członkowskiego nie określono modyfikatora dostępu, zostanie użyta domyślna dostępność.</span><span class="sxs-lookup"><span data-stu-id="53d36-118">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="53d36-119">Typy najwyższego poziomu, które nie są zagnieżdżone w innych typach, mogą mieć `internal` tylko `public` dostępność lub ułatwienia dostępu.</span><span class="sxs-lookup"><span data-stu-id="53d36-119">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="53d36-120">Domyślną dostępnością dla tych typów jest `internal` .</span><span class="sxs-lookup"><span data-stu-id="53d36-120">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="53d36-121">Zagnieżdżone typy, które są elementami członkowskimi innych typów, mogą mieć zadeklarowane podano, jak wskazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="53d36-121">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="53d36-122">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="53d36-122">Members of</span></span>|<span data-ttu-id="53d36-123">Dostępność domyślnego elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="53d36-123">Default member accessibility</span></span>|<span data-ttu-id="53d36-124">Dozwolone zadeklarowane dostępność elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="53d36-124">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="53d36-125">Brak</span><span class="sxs-lookup"><span data-stu-id="53d36-125">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="53d36-126">Brak</span><span class="sxs-lookup"><span data-stu-id="53d36-126">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="53d36-127">Dostępność typu zagnieżdżonego zależy od jego [domeny dostępności](./accessibility-domain.md), który jest określany przez zadeklarowaną dostępność elementu członkowskiego i domenę dostępności typu natychmiastowego.</span><span class="sxs-lookup"><span data-stu-id="53d36-127">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="53d36-128">Jednak domena dostępności typu zagnieżdżonego nie może przekroczyć tego typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="53d36-128">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="53d36-129">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="53d36-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53d36-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="53d36-130">See also</span></span>

- [<span data-ttu-id="53d36-131">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="53d36-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="53d36-132">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="53d36-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="53d36-133">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="53d36-133">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="53d36-134">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="53d36-134">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="53d36-135">Domena ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="53d36-135">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="53d36-136">Ograniczenia dotyczące używania poziomów ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="53d36-136">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="53d36-137">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="53d36-137">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="53d36-138">public</span><span class="sxs-lookup"><span data-stu-id="53d36-138">public</span></span>](./public.md)
- [<span data-ttu-id="53d36-139">private</span><span class="sxs-lookup"><span data-stu-id="53d36-139">private</span></span>](./private.md)
- [<span data-ttu-id="53d36-140">protected</span><span class="sxs-lookup"><span data-stu-id="53d36-140">protected</span></span>](./protected.md)
- [<span data-ttu-id="53d36-141">internal</span><span class="sxs-lookup"><span data-stu-id="53d36-141">internal</span></span>](./internal.md)
