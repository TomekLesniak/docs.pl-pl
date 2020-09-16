---
title: x:Subclass — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540722"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="7bb52-102">x:Subclass — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="7bb52-102">x:Subclass Directive</span></span>

<span data-ttu-id="7bb52-103">Modyfikuje zachowanie kompilowania znaczników XAML, gdy `x:Class` jest również udostępniane.</span><span class="sxs-lookup"><span data-stu-id="7bb52-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="7bb52-104">Zamiast tworzenia klasy częściowej, która jest oparta na `x:Class` , dostarczony `x:Class` element jest tworzony jako Klasa pośrednicząca, a następnie powinna być oparta na podanej klasie pochodnej `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="7bb52-105">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="7bb52-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="7bb52-106">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="7bb52-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="7bb52-107">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="7bb52-107">Optional.</span></span> <span data-ttu-id="7bb52-108">Określa przestrzeń nazw środowiska CLR, która zawiera `classname` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="7bb52-109">Jeśli `namespace` jest określony, kropka (.) oddziela `namespace` i `classname` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="7bb52-110">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="7bb52-110">Required.</span></span> <span data-ttu-id="7bb52-111">Określa nazwę CLR klasy częściowej, która łączy załadowany kod XAML i związany z kodem dla tego języka XAML.</span><span class="sxs-lookup"><span data-stu-id="7bb52-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="7bb52-112">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="7bb52-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="7bb52-113">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="7bb52-113">Optional.</span></span> <span data-ttu-id="7bb52-114">Może się różnić od `namespace` tego, czy każda przestrzeń nazw może rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="7bb52-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="7bb52-115">Określa przestrzeń nazw środowiska CLR, która zawiera `subclassName` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="7bb52-116">Jeśli `subclassName` jest określony, kropka (.) oddziela `subclassNamespace` i `subclassName` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="7bb52-117">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="7bb52-117">Required.</span></span> <span data-ttu-id="7bb52-118">Określa nazwę środowiska CLR podklasy.</span><span class="sxs-lookup"><span data-stu-id="7bb52-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="7bb52-119">Zależności</span><span class="sxs-lookup"><span data-stu-id="7bb52-119">Dependencies</span></span>

<span data-ttu-id="7bb52-120">[dyrektywa x:Class](xclass-directive.md) musi być również podana dla tego samego obiektu i musi być elementem głównym produkcji XAML.</span><span class="sxs-lookup"><span data-stu-id="7bb52-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bb52-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7bb52-121">Remarks</span></span>

<span data-ttu-id="7bb52-122">`x:Subclass` Użycie jest przeznaczone głównie dla języków, które nie obsługują deklaracji klasy częściowej.</span><span class="sxs-lookup"><span data-stu-id="7bb52-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="7bb52-123">Klasa używana jako `x:Subclass` nie może być klasą zagnieżdżoną i `x:Subclass` musi odwoływać się do obiektu głównego zgodnie z opisem w sekcji "zależności".</span><span class="sxs-lookup"><span data-stu-id="7bb52-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="7bb52-124">W przeciwnym razie koncepcyjne znaczenie `x:Subclass` jest niezdefiniowane przez implementację usług .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="7bb52-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="7bb52-125">Wynika to z faktu, że zachowanie usług .NET XAML nie określa ogólnego modelu programowania, w którym są połączone znaczniki XAML i kod zapasowy.</span><span class="sxs-lookup"><span data-stu-id="7bb52-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="7bb52-126">Implementacje dalszych koncepcji związanych z programem `x:Class` i `x:Subclass` są wykonywane przez określone platformy, które używają modeli programowania lub modeli aplikacji do definiowania sposobu łączenia znaczników XAML, skompilowanych znaczników i kodu opartego na środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="7bb52-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="7bb52-127">Każda struktura może mieć własne akcje kompilacji, które umożliwiają zachowanie niektórych zachowań lub określonych składników, które muszą być zawarte w środowisku kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7bb52-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="7bb52-128">W ramach struktury akcje kompilacji mogą się różnić w zależności od języka CLR, który jest używany w kodzie.</span><span class="sxs-lookup"><span data-stu-id="7bb52-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="7bb52-129">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="7bb52-129">WPF Usage Notes</span></span>

<span data-ttu-id="7bb52-130">`x:Subclass` może znajdować się w katalogu głównym strony lub w <xref:System.Windows.Application> katalogu głównym w definicji aplikacji, która już ma `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="7bb52-131">Deklarowanie `x:Subclass` dla dowolnego elementu, innego niż strona lub katalog główny lub określenie, gdzie nie `x:Class` istnieje, powoduje błąd czasu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7bb52-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="7bb52-132">Tworzenie klas pochodnych, które działają poprawnie dla `x:Subclass` scenariusza, jest dość skomplikowane.</span><span class="sxs-lookup"><span data-stu-id="7bb52-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="7bb52-133">Może być konieczne przeanalizowanie plików pośrednich (plików g produkowanych w folderze obj projektu przez kompilację znaczników z nazwami, które zawierają nazwy plików. XAML).</span><span class="sxs-lookup"><span data-stu-id="7bb52-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="7bb52-134">Te pliki pośrednie mogą pomóc określić źródło niektórych konstrukcji programistycznych w sprzężonych klasach częściowych w skompilowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7bb52-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="7bb52-135">Procedury obsługi zdarzeń w klasie pochodnej muszą być `internal override` ( `Friend Overrides` w programie Microsoft Visual Basic), aby przesłonić elementy pośredniczące dla programów obsługi jako utworzone w klasie pośredniej podczas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7bb52-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="7bb52-136">W przeciwnym razie implementacje klas pochodnych ukryją (Shadow) implementację klasy pośredniej i procedury obsługi klasy pośredniczącej nie są wywoływane.</span><span class="sxs-lookup"><span data-stu-id="7bb52-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="7bb52-137">Podczas definiowania obu `x:Class` i `x:Subclass` , nie trzeba podawać żadnej implementacji dla klasy, do której odwołuje się `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="7bb52-138">Wystarczy nadać mu nazwę przy użyciu `x:Class` atrybutu, aby kompilator miał pewne wskazówki dotyczące klasy, którą tworzy w plikach pośrednich (w tym przypadku kompilator nie wybiera nazwy domyślnej).</span><span class="sxs-lookup"><span data-stu-id="7bb52-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="7bb52-139">Można nadać `x:Class` klasie implementację, ale nie jest to typowy scenariusz użycia obu `x:Class` i `x:Subclass` .</span><span class="sxs-lookup"><span data-stu-id="7bb52-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bb52-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7bb52-140">See also</span></span>

- [<span data-ttu-id="7bb52-141">x:Class — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="7bb52-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="7bb52-142">Klasy XAML i niestandardowe dla WPF</span><span class="sxs-lookup"><span data-stu-id="7bb52-142">XAML and Custom Classes for WPF</span></span>](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
