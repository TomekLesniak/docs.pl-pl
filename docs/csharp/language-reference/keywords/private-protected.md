---
description: Private Protected — Dokumentacja języka C#
title: Private Protected — Dokumentacja języka C#
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: e7ef6d691b43abd3d07321adfc0c166629ce9098
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537304"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="fd611-103">Private Protected (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="fd611-103">private protected (C# Reference)</span></span>

<span data-ttu-id="fd611-104">`private protected`Kombinacja słowa kluczowego jest modyfikatorem dostępu składowej.</span><span class="sxs-lookup"><span data-stu-id="fd611-104">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="fd611-105">Prywatna chroniona składowa jest dostępna dla typów pochodzących od klasy zawierającej, ale tylko w obrębie zawartego zestawu.</span><span class="sxs-lookup"><span data-stu-id="fd611-105">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="fd611-106">Aby uzyskać porównanie `private protected` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="fd611-106">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fd611-107">`private protected`Modyfikator dostępu jest prawidłowy w języku C# w wersji 7,2 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="fd611-107">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="fd611-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="fd611-108">Example</span></span>

<span data-ttu-id="fd611-109">Prywatna chroniona składowa klasy bazowej jest dostępna z typów pochodnych w jego zestawie zawierającym tylko wtedy, gdy typ statyczny zmiennej jest typem klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="fd611-109">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="fd611-110">Rozważmy na przykład następujący segment kodu:</span><span class="sxs-lookup"><span data-stu-id="fd611-110">For example, consider the following code segment:</span></span>

```csharp
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="fd611-111">Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly2.cs` .</span><span class="sxs-lookup"><span data-stu-id="fd611-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="fd611-112">Pierwszy plik zawiera publiczną klasę bazową, `BaseClass` i typ pochodzący od niej `DerivedClass1` .</span><span class="sxs-lookup"><span data-stu-id="fd611-112">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="fd611-113">`BaseClass` jest właścicielem prywatnej, chronionej składowej, `myValue` która `DerivedClass1` próbuje uzyskać dostęp na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="fd611-113">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="fd611-114">Pierwsza próba uzyskania dostępu `myValue` za pomocą wystąpienia `BaseClass` spowoduje wystąpienie błędu.</span><span class="sxs-lookup"><span data-stu-id="fd611-114">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="fd611-115">Jednak próba użycia jej jako dziedziczonego elementu członkowskiego w programie powiedzie `DerivedClass1` się.</span><span class="sxs-lookup"><span data-stu-id="fd611-115">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="fd611-116">W drugim pliku próba uzyskania dostępu `myValue` jako dziedziczonego elementu członkowskiego `DerivedClass2` spowoduje wystąpienie błędu, ponieważ jest on dostępny tylko dla typów pochodnych w assembly1.</span><span class="sxs-lookup"><span data-stu-id="fd611-116">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="fd611-117">Jeśli `Assembly1.cs` zawiera <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> te nazwy `Assembly2` , Klasa pochodna `DerivedClass1` będzie miała dostęp do `private protected` elementów członkowskich zadeklarowanych w elemencie `BaseClass` .</span><span class="sxs-lookup"><span data-stu-id="fd611-117">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="fd611-118">`InternalsVisibleTo` sprawia `private protected` , że elementy członkowskie są widoczne dla klas pochodnych w innych zestawach.</span><span class="sxs-lookup"><span data-stu-id="fd611-118">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="fd611-119">Elementy członkowskie struktury nie mogą być takie same `private protected` , ponieważ struktura nie może być dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="fd611-119">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fd611-120">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="fd611-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fd611-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fd611-121">See also</span></span>

- [<span data-ttu-id="fd611-122">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="fd611-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fd611-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="fd611-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fd611-124">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="fd611-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fd611-125">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="fd611-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="fd611-126">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="fd611-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="fd611-127">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="fd611-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="fd611-128">public</span><span class="sxs-lookup"><span data-stu-id="fd611-128">public</span></span>](public.md)
- [<span data-ttu-id="fd611-129">private</span><span class="sxs-lookup"><span data-stu-id="fd611-129">private</span></span>](private.md)
- [<span data-ttu-id="fd611-130">internal</span><span class="sxs-lookup"><span data-stu-id="fd611-130">internal</span></span>](internal.md)
- <span data-ttu-id="fd611-131">[Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd611-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
