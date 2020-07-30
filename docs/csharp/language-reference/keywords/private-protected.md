---
title: Private Protected — Dokumentacja języka C#
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: 94ef55d7e13841f81b036f52659b215e22a3a0d7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301804"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="5a81d-102">Private Protected (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5a81d-102">private protected (C# Reference)</span></span>

<span data-ttu-id="5a81d-103">`private protected`Kombinacja słowa kluczowego jest modyfikatorem dostępu składowej.</span><span class="sxs-lookup"><span data-stu-id="5a81d-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="5a81d-104">Prywatna chroniona składowa jest dostępna dla typów pochodzących od klasy zawierającej, ale tylko w obrębie zawartego zestawu.</span><span class="sxs-lookup"><span data-stu-id="5a81d-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="5a81d-105">Aby uzyskać porównanie `private protected` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5a81d-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5a81d-106">`private protected`Modyfikator dostępu jest prawidłowy w języku C# w wersji 7,2 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="5a81d-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="5a81d-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="5a81d-107">Example</span></span>

<span data-ttu-id="5a81d-108">Prywatna chroniona składowa klasy bazowej jest dostępna z typów pochodnych w jego zestawie zawierającym tylko wtedy, gdy typ statyczny zmiennej jest typem klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="5a81d-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="5a81d-109">Rozważmy na przykład następujący segment kodu:</span><span class="sxs-lookup"><span data-stu-id="5a81d-109">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="5a81d-110">Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly2.cs` .</span><span class="sxs-lookup"><span data-stu-id="5a81d-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="5a81d-111">Pierwszy plik zawiera publiczną klasę bazową, `BaseClass` i typ pochodzący od niej `DerivedClass1` .</span><span class="sxs-lookup"><span data-stu-id="5a81d-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="5a81d-112">`BaseClass`jest właścicielem prywatnej, chronionej składowej, `myValue` która `DerivedClass1` próbuje uzyskać dostęp na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="5a81d-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="5a81d-113">Pierwsza próba uzyskania dostępu `myValue` za pomocą wystąpienia `BaseClass` spowoduje wystąpienie błędu.</span><span class="sxs-lookup"><span data-stu-id="5a81d-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="5a81d-114">Jednak próba użycia jej jako dziedziczonego elementu członkowskiego w programie powiedzie `DerivedClass1` się.</span><span class="sxs-lookup"><span data-stu-id="5a81d-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="5a81d-115">W drugim pliku próba uzyskania dostępu `myValue` jako dziedziczonego elementu członkowskiego `DerivedClass2` spowoduje wystąpienie błędu, ponieważ jest on dostępny tylko dla typów pochodnych w assembly1.</span><span class="sxs-lookup"><span data-stu-id="5a81d-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="5a81d-116">Jeśli `Assembly1.cs` zawiera <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> te nazwy `Assembly2` , Klasa pochodna `DerivedClass1` będzie miała dostęp do `private protected` elementów członkowskich zadeklarowanych w elemencie `BaseClass` .</span><span class="sxs-lookup"><span data-stu-id="5a81d-116">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="5a81d-117">`InternalsVisibleTo`sprawia `private protected` , że elementy członkowskie są widoczne dla klas pochodnych w innych zestawach.</span><span class="sxs-lookup"><span data-stu-id="5a81d-117">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="5a81d-118">Elementy członkowskie struktury nie mogą być takie same `private protected` , ponieważ struktura nie może być dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="5a81d-118">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5a81d-119">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5a81d-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5a81d-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5a81d-120">See also</span></span>

- [<span data-ttu-id="5a81d-121">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="5a81d-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5a81d-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="5a81d-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a81d-123">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="5a81d-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5a81d-124">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="5a81d-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="5a81d-125">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="5a81d-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="5a81d-126">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="5a81d-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5a81d-127">public</span><span class="sxs-lookup"><span data-stu-id="5a81d-127">public</span></span>](public.md)
- [<span data-ttu-id="5a81d-128">użytek</span><span class="sxs-lookup"><span data-stu-id="5a81d-128">private</span></span>](private.md)
- [<span data-ttu-id="5a81d-129">internal</span><span class="sxs-lookup"><span data-stu-id="5a81d-129">internal</span></span>](internal.md)
- <span data-ttu-id="5a81d-130">[Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5a81d-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
