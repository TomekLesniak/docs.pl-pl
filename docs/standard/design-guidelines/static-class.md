---
title: Projekt klasy statycznej
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: efa5ca6e7b5e7b7d03cbe1d55471a388f3faab37
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828663"
---
# <a name="static-class-design"></a><span data-ttu-id="3b5f8-102">Projekt klasy statycznej</span><span class="sxs-lookup"><span data-stu-id="3b5f8-102">Static Class Design</span></span>
<span data-ttu-id="3b5f8-103">Klasa statyczna jest definiowana jako Klasa, która zawiera tylko statyczne elementy członkowskie (oczywiście oprócz członków wystąpienia dziedziczonych z <xref:System.Object?displayProperty=nameWithType> i prawdopodobnie konstruktora prywatnego).</span><span class="sxs-lookup"><span data-stu-id="3b5f8-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="3b5f8-104">Niektóre języki zapewniają wbudowaną obsługę klas statycznych.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="3b5f8-105">W języku C# 2,0 i nowszych, gdy Klasa jest zadeklarowana jako statyczna, jest zapieczętowana, abstrakcyjna i nie można zastąpić jej elementów członkowskich wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="3b5f8-106">Klasy statyczne są kompromisem między czystym i prostotą zorientowanym na obiektem.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="3b5f8-107">Są one często używane do udostępniania skrótów do innych operacji (takich jak <xref:System.IO.File?displayProperty=nameWithType> ), posiadaczy metod rozszerzających lub funkcji, dla których pełna otoka zorientowana obiektowo jest nieuzasadniona (na przykład <xref:System.Environment?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="3b5f8-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="3b5f8-108">✔️ używać klas statycznych oszczędnie.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="3b5f8-109">Klasy statyczne powinny być używane tylko jako klasy pomocnicze dla rdzenia zorientowanego obiektowo struktury.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="3b5f8-110">❌ NIE Traktuj klas statycznych jako zasobników dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="3b5f8-111">❌ Nie deklaruj ani nie Przesłoń składowych wystąpienia w klasach statycznych.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="3b5f8-112">✔️ NALEŻY zadeklarować klasy statyczne jako zapieczętowane, abstrakcyjne i dodać konstruktora wystąpienia prywatnego, jeśli język programowania nie ma wbudowanej obsługi dla klas statycznych.</span><span class="sxs-lookup"><span data-stu-id="3b5f8-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="3b5f8-113">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="3b5f8-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3b5f8-114">*Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="3b5f8-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3b5f8-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3b5f8-115">See also</span></span>

- [<span data-ttu-id="3b5f8-116">Wskazówki dotyczące projektowania typów</span><span class="sxs-lookup"><span data-stu-id="3b5f8-116">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="3b5f8-117">Wskazówki dotyczące projektowania struktury</span><span class="sxs-lookup"><span data-stu-id="3b5f8-117">Framework Design Guidelines</span></span>](index.md)
