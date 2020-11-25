---
title: Przeciążanie składowej
ms.date: 10/22/2008
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: fe8bf23a04e6684564d3d7e287c2a009e0817732
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706635"
---
# <a name="member-overloading"></a><span data-ttu-id="82965-102">Przeciążanie składowej</span><span class="sxs-lookup"><span data-stu-id="82965-102">Member Overloading</span></span>

<span data-ttu-id="82965-103">Przeciążenie elementu członkowskiego oznacza utworzenie dwóch lub większej liczby elementów członkowskich tego samego typu, które różnią się tylko liczbą lub typem parametrów, ale mają tę samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="82965-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="82965-104">Na przykład w poniższym przykładzie `WriteLine` Metoda jest przeciążona:</span><span class="sxs-lookup"><span data-stu-id="82965-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 <span data-ttu-id="82965-105">Ponieważ tylko metody, konstruktory i właściwości indeksowane mogą mieć parametry, tylko te elementy członkowskie mogą być przeciążone.</span><span class="sxs-lookup"><span data-stu-id="82965-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>

 <span data-ttu-id="82965-106">Przeciążanie to jedna z najważniejszych technik zwiększania użyteczności, produktywności i czytelności bibliotek wielokrotnego użytku.</span><span class="sxs-lookup"><span data-stu-id="82965-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="82965-107">Przeciążanie liczby parametrów pozwala na zapewnienie prostszej wersji konstruktorów i metod.</span><span class="sxs-lookup"><span data-stu-id="82965-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="82965-108">Przeciążanie w typie parametru umożliwia używanie tej samej nazwy elementu członkowskiego dla elementów członkowskich wykonujących identyczne operacje na wybranym zestawie różnych typów.</span><span class="sxs-lookup"><span data-stu-id="82965-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>

 <span data-ttu-id="82965-109">✔️ Spróbuj użyć opisowych nazw parametrów, aby wskazać wartość domyślną używaną przez krótsze przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="82965-109">✔️ DO try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>

 <span data-ttu-id="82965-110">❌ UNIKAj arbitralnie różnych nazw parametrów w przeciążeniach.</span><span class="sxs-lookup"><span data-stu-id="82965-110">❌ AVOID arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="82965-111">Jeśli parametr w jednym przeciążeniu reprezentuje takie samo dane wejściowe jak parametr w innym przeciążeniu, parametry powinny mieć taką samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="82965-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>

 <span data-ttu-id="82965-112">❌ UNIKAj niespójności w kolejności parametrów w przeciążonych elementach członkowskich.</span><span class="sxs-lookup"><span data-stu-id="82965-112">❌ AVOID being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="82965-113">Parametry o tej samej nazwie powinny znajdować się w tej samej pozycji we wszystkich przeciążeń.</span><span class="sxs-lookup"><span data-stu-id="82965-113">Parameters with the same name should appear in the same position in all overloads.</span></span>

 <span data-ttu-id="82965-114">✔️ WYKONAĆ tylko najdłuższym wirtualnym przeciążeniem (jeśli jest wymagana rozszerzalność).</span><span class="sxs-lookup"><span data-stu-id="82965-114">✔️ DO make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="82965-115">Krótsze przeciążenia powinny po prostu wywołać do dłuższego przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="82965-115">Shorter overloads should simply call through to a longer overload.</span></span>

 <span data-ttu-id="82965-116">❌ NIE należy używać `ref` `out` modyfikatorów ani do przeciążania elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="82965-116">❌ DO NOT use `ref` or `out` modifiers to overload members.</span></span>

 <span data-ttu-id="82965-117">Niektóre języki nie mogą rozpoznawać wywołań do przeciążenia, takich jak ten.</span><span class="sxs-lookup"><span data-stu-id="82965-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="82965-118">Ponadto takie przeciążenia zwykle mają całkowicie inną semantykę i prawdopodobnie nie powinny być przeciążeniami, ale zamiast nich należy użyć dwóch oddzielnych metod.</span><span class="sxs-lookup"><span data-stu-id="82965-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>

 <span data-ttu-id="82965-119">❌ NIE należy przeciążać z parametrami w tym samym położeniu i podobnych typach z inną semantyką.</span><span class="sxs-lookup"><span data-stu-id="82965-119">❌ DO NOT have overloads with parameters at the same position and similar types yet with different semantics.</span></span>

 <span data-ttu-id="82965-120">✔️ zezwalać na `null` przekazywanie argumentów opcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="82965-120">✔️ DO  allow `null` to be passed for optional arguments.</span></span>

 <span data-ttu-id="82965-121">✔️ użyć przeciążenia elementu członkowskiego zamiast definiować członków z argumentami domyślnymi.</span><span class="sxs-lookup"><span data-stu-id="82965-121">✔️ DO use member overloading rather than defining members with default arguments.</span></span>

 <span data-ttu-id="82965-122">Argumenty domyślne nie są zgodne ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="82965-122">Default arguments are not CLS compliant.</span></span>

 <span data-ttu-id="82965-123">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="82965-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="82965-124">*Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="82965-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="82965-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="82965-125">See also</span></span>

- [<span data-ttu-id="82965-126">Wskazówki dotyczące projektowania elementów członkowskich</span><span class="sxs-lookup"><span data-stu-id="82965-126">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="82965-127">Wskazówki dotyczące projektowania struktury</span><span class="sxs-lookup"><span data-stu-id="82965-127">Framework Design Guidelines</span></span>](index.md)
