---
description: Modyfikatory dostępu — odwołanie w C#
title: Modyfikatory dostępu — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 2ea7a65c23b6a1edee572f6f6ff6c52d14358408
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127155"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="bad1d-103">Modyfikatory dostępu (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="bad1d-103">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="bad1d-104">Modyfikatory dostępu są słowami kluczowymi używanymi do określania zadeklarowanej dostępności elementu członkowskiego lub typu.</span><span class="sxs-lookup"><span data-stu-id="bad1d-104">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="bad1d-105">W tej sekcji przedstawiono cztery Modyfikatory dostępu:</span><span class="sxs-lookup"><span data-stu-id="bad1d-105">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="bad1d-106">Za pomocą modyfikatorów dostępu można określić następujące sześć poziomów dostępności:</span><span class="sxs-lookup"><span data-stu-id="bad1d-106">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="bad1d-107">[`public`](public.md): Dostęp nie jest ograniczony.</span><span class="sxs-lookup"><span data-stu-id="bad1d-107">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="bad1d-108">[`protected`](protected.md): Dostęp jest ograniczony do zawierającej klasy lub typów pochodzących od klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="bad1d-108">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="bad1d-109">[`internal`](internal.md): Dostęp jest ograniczony do bieżącego zestawu.</span><span class="sxs-lookup"><span data-stu-id="bad1d-109">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="bad1d-110">[`protected internal`](protected-internal.md): Dostęp jest ograniczony do bieżącego zestawu lub typów pochodzących od klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="bad1d-110">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="bad1d-111">[`private`](private.md): Dostęp jest ograniczony do typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="bad1d-111">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="bad1d-112">[`private protected`](private-protected.md): Dostęp jest ograniczony do zawierającej klasy lub typów pochodzących od klasy zawierającej w bieżącym zestawie.</span><span class="sxs-lookup"><span data-stu-id="bad1d-112">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="bad1d-113">W tej sekcji wprowadzono również następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="bad1d-113">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="bad1d-114">[Poziomy ułatwień](./accessibility-levels.md)dostępu: aby zadeklarować sześć poziomów dostępności, użyj czterech modyfikatorów dostępu.</span><span class="sxs-lookup"><span data-stu-id="bad1d-114">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="bad1d-115">[Domena dostępności](./accessibility-domain.md): określa, gdzie w sekcjach programu można odwoływać się do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="bad1d-115">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="bad1d-116">[Ograniczenia dotyczące używania poziomów ułatwień dostępu](./restrictions-on-using-accessibility-levels.md): Podsumowanie ograniczeń dotyczących używania zadeklarowanych poziomów ułatwień dostępu.</span><span class="sxs-lookup"><span data-stu-id="bad1d-116">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad1d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bad1d-117">See also</span></span>

- [<span data-ttu-id="bad1d-118">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="bad1d-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bad1d-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="bad1d-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bad1d-120">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="bad1d-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="bad1d-121">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="bad1d-121">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="bad1d-122">Słowa kluczowe dostępu</span><span class="sxs-lookup"><span data-stu-id="bad1d-122">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="bad1d-123">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="bad1d-123">Modifiers</span></span>](index.md)
