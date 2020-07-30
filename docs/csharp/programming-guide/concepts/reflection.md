---
title: Odbicie (C#)
description: Odbicie zawiera obiekty, które opisują zestawy, moduły i typy w języku C#. Jeśli kod zawiera atrybuty, odbicie umożliwia uzyskanie dostępu do nich.
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4d4f4c082dd2d58e212bae53524e5dd4fd06fb75
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302805"
---
# <a name="reflection-c"></a><span data-ttu-id="bc042-104">Odbicie (C#)</span><span class="sxs-lookup"><span data-stu-id="bc042-104">Reflection (C#)</span></span>

<span data-ttu-id="bc042-105">Odbicie zawiera obiekty (typu <xref:System.Type> ) opisujące zestawy, moduły i typy.</span><span class="sxs-lookup"><span data-stu-id="bc042-105">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="bc042-106">Możesz użyć odbicia, aby dynamicznie utworzyć wystąpienie typu, powiązać typ z istniejącym obiektem lub uzyskać typ z istniejącego obiektu i wywołać jego metody lub uzyskać dostęp do jego pól i właściwości.</span><span class="sxs-lookup"><span data-stu-id="bc042-106">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="bc042-107">Jeśli używasz atrybutów w kodzie, odbicie umożliwia uzyskanie dostępu do nich.</span><span class="sxs-lookup"><span data-stu-id="bc042-107">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="bc042-108">Aby uzyskać więcej informacji, zobacz [atrybuty](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc042-108">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="bc042-109">Oto prosty przykład odbicia przy użyciu <xref:System.Object.GetType> metody dziedziczonej przez wszystkie typy z `Object` klasy podstawowej — w celu uzyskania typu zmiennej:</span><span class="sxs-lookup"><span data-stu-id="bc042-109">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="bc042-110">Upewnij się, że dodano `using System;` i `using System.Reflection;` w górnej części pliku *CS* .</span><span class="sxs-lookup"><span data-stu-id="bc042-110">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="bc042-111">Wynik: `System.Int32` .</span><span class="sxs-lookup"><span data-stu-id="bc042-111">The output is: `System.Int32`.</span></span>

<span data-ttu-id="bc042-112">Poniższy przykład używa odbicia w celu uzyskania pełnej nazwy załadowanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="bc042-112">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="bc042-113">Wynik: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e` .</span><span class="sxs-lookup"><span data-stu-id="bc042-113">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="bc042-114">Słowa kluczowe języka C# `protected` i nie `internal` mają znaczenia w Il i nie są używane w interfejsach API odbicia.</span><span class="sxs-lookup"><span data-stu-id="bc042-114">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="bc042-115">Odpowiednie warunki w IL są *rodziną* i *zestawem*.</span><span class="sxs-lookup"><span data-stu-id="bc042-115">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="bc042-116">Aby zidentyfikować `internal` metodę przy użyciu odbicia, należy użyć <xref:System.Reflection.MethodBase.IsAssembly%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="bc042-116">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="bc042-117">Aby zidentyfikować `protected internal` metodę, użyj <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> .</span><span class="sxs-lookup"><span data-stu-id="bc042-117">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="bc042-118">Przegląd odbicia</span><span class="sxs-lookup"><span data-stu-id="bc042-118">Reflection overview</span></span>

<span data-ttu-id="bc042-119">Odbicie jest przydatne w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="bc042-119">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="bc042-120">Gdy musisz uzyskać dostęp do atrybutów w metadanych programu.</span><span class="sxs-lookup"><span data-stu-id="bc042-120">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="bc042-121">Aby uzyskać więcej informacji, zobacz artykuł [pobieranie informacji przechowywanych w atrybutach](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="bc042-121">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="bc042-122">Do badania i tworzenia wystąpień typów w zestawie.</span><span class="sxs-lookup"><span data-stu-id="bc042-122">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="bc042-123">Do kompilowania nowych typów w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bc042-123">For building new types at runtime.</span></span> <span data-ttu-id="bc042-124">Użyj klas w <xref:System.Reflection.Emit> .</span><span class="sxs-lookup"><span data-stu-id="bc042-124">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="bc042-125">Do wykonywania późnego wiązania, uzyskiwanie dostępu do metod w typach utworzonych w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bc042-125">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="bc042-126">Zobacz temat [dynamiczne ładowanie i używanie typów](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="bc042-126">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="bc042-127">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="bc042-127">Related sections</span></span>

<span data-ttu-id="bc042-128">Więcej informacji:</span><span class="sxs-lookup"><span data-stu-id="bc042-128">For more information:</span></span>

- [<span data-ttu-id="bc042-129">Odbicie</span><span class="sxs-lookup"><span data-stu-id="bc042-129">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="bc042-130">Wyświetlanie informacji o typie</span><span class="sxs-lookup"><span data-stu-id="bc042-130">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="bc042-131">Odbicie i typy ogólne</span><span class="sxs-lookup"><span data-stu-id="bc042-131">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="bc042-132">Pobieranie informacji przechowywanych w atrybutach</span><span class="sxs-lookup"><span data-stu-id="bc042-132">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="bc042-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bc042-133">See also</span></span>

- [<span data-ttu-id="bc042-134">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="bc042-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bc042-135">Zestawy w środowisku .NET</span><span class="sxs-lookup"><span data-stu-id="bc042-135">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
