---
title: Projekt interfejsu
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 9f8ff38d5825091d4d5d3716ed6025a8d04c592d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821011"
---
# <a name="interface-design"></a><span data-ttu-id="6d00f-102">Projekt interfejsu</span><span class="sxs-lookup"><span data-stu-id="6d00f-102">Interface Design</span></span>
<span data-ttu-id="6d00f-103">Chociaż większość interfejsów API jest najlepszym modelem przy użyciu klas i struktur, istnieją przypadki, w których interfejsy są bardziej odpowiednie lub są jedyną opcją.</span><span class="sxs-lookup"><span data-stu-id="6d00f-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>

 <span data-ttu-id="6d00f-104">Środowisko CLR nie obsługuje dziedziczenia wielokrotnego (tj. klasy CLR nie mogą dziedziczyć z więcej niż jednej klasy bazowej), ale w przypadku dziedziczenia z klasy bazowej są dozwolone typy implementujące jeden lub więcej interfejsów.</span><span class="sxs-lookup"><span data-stu-id="6d00f-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="6d00f-105">W związku z tym interfejsy są często używane do osiągnięcia efektu wielokrotnego dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="6d00f-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="6d00f-106">Na przykład <xref:System.IDisposable> jest interfejsem, który umożliwia obsługę typów disposability niezależnie od innych hierarchii dziedziczenia, w których chcą uczestniczyć.</span><span class="sxs-lookup"><span data-stu-id="6d00f-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>

 <span data-ttu-id="6d00f-107">Inną sytuacją, w której jest właściwy Definiowanie interfejsu, jest utworzenie wspólnego interfejsu, który może być obsługiwany przez kilka typów, w tym niektóre typy wartości.</span><span class="sxs-lookup"><span data-stu-id="6d00f-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="6d00f-108">Typy wartości nie mogą dziedziczyć po typach innych niż <xref:System.ValueType> , ale mogą implementować interfejsy, dlatego użycie interfejsu jest jedyną opcją w celu zapewnienia wspólnego typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="6d00f-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>

 <span data-ttu-id="6d00f-109">✔️ zdefiniować interfejs, jeśli potrzebujesz wspólnego interfejsu API, który ma być obsługiwany przez zestaw typów, które zawierają typy wartości.</span><span class="sxs-lookup"><span data-stu-id="6d00f-109">✔️ DO define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>

 <span data-ttu-id="6d00f-110">✔️ ROZWAŻYĆ zdefiniowanie interfejsu, jeśli musisz obsługiwać jego funkcje na typach, które już dziedziczą z innego typu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-110">✔️ CONSIDER defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>

 <span data-ttu-id="6d00f-111">❌ UNIKAj używania interfejsów znaczników (interfejsy bez elementów członkowskich).</span><span class="sxs-lookup"><span data-stu-id="6d00f-111">❌ AVOID using marker interfaces (interfaces with no members).</span></span>

 <span data-ttu-id="6d00f-112">Jeśli konieczne jest oznaczenie klasy jako posiadającej konkretną charakterystykę (znacznik), w ogólności należy użyć atrybutu niestandardowego, a nie interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>

 <span data-ttu-id="6d00f-113">✔️ zapewnić co najmniej jeden typ, który jest implementacją interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-113">✔️ DO provide at least one type that is an implementation of an interface.</span></span>

 <span data-ttu-id="6d00f-114">Dzięki temu można sprawdzić poprawność projektu interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="6d00f-115">Na przykład <xref:System.Collections.Generic.List%601> jest implementacją <xref:System.Collections.Generic.IList%601> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>

 <span data-ttu-id="6d00f-116">✔️ zapewnić co najmniej jeden interfejs API, który wykorzystuje każdy zdefiniowany przez siebie interfejs (metodę pobierającą interfejs jako parametr lub właściwość wpisaną jako interfejs).</span><span class="sxs-lookup"><span data-stu-id="6d00f-116">✔️ DO provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>

 <span data-ttu-id="6d00f-117">Dzięki temu można sprawdzić poprawność projektu interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="6d00f-118">Na przykład <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> korzysta z <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>

 <span data-ttu-id="6d00f-119">❌ NIE należy dodawać członków do interfejsu, który został wcześniej dostarczony.</span><span class="sxs-lookup"><span data-stu-id="6d00f-119">❌ DO NOT add members to an interface that has previously shipped.</span></span>

 <span data-ttu-id="6d00f-120">Wykonanie tej operacji spowodowałoby uszkodzenie implementacji interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6d00f-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="6d00f-121">Należy utworzyć nowy interfejs, aby uniknąć problemów z wersją.</span><span class="sxs-lookup"><span data-stu-id="6d00f-121">You should create a new interface in order to avoid versioning problems.</span></span>

 <span data-ttu-id="6d00f-122">Z wyjątkiem przypadków opisanych w tych wytycznych, należy, ogólnie rzecz biorąc,, zamiast interfejsów projektowania bibliotek do wielokrotnego użytku.</span><span class="sxs-lookup"><span data-stu-id="6d00f-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>

 <span data-ttu-id="6d00f-123">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="6d00f-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6d00f-124">*Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="6d00f-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6d00f-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6d00f-125">See also</span></span>

- [<span data-ttu-id="6d00f-126">Wskazówki dotyczące projektowania typów</span><span class="sxs-lookup"><span data-stu-id="6d00f-126">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="6d00f-127">Wskazówki dotyczące projektowania struktury</span><span class="sxs-lookup"><span data-stu-id="6d00f-127">Framework Design Guidelines</span></span>](index.md)
