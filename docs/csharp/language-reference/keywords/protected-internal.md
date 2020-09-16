---
description: chronione wewnętrzne odwołanie do języka C#
title: chronione wewnętrzne odwołanie do języka C#
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: f22de104154df74f02c048b1209eeac754a03e64
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536808"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="c0edb-103">chroniona wewnętrznie (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="c0edb-103">protected internal (C# Reference)</span></span>

<span data-ttu-id="c0edb-104">`protected internal`Kombinacja słowa kluczowego jest modyfikatorem dostępu składowej.</span><span class="sxs-lookup"><span data-stu-id="c0edb-104">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c0edb-105">Chroniony wewnętrzny element członkowski jest dostępny z bieżącego zestawu lub z typów, które pochodzą od klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="c0edb-105">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="c0edb-106">Aby uzyskać porównanie `protected internal` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c0edb-106">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="c0edb-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="c0edb-107">Example</span></span>

<span data-ttu-id="c0edb-108">Chroniona wewnętrzna składowa klasy bazowej jest dostępna z dowolnego typu w obrębie zawierającego go zestawu.</span><span class="sxs-lookup"><span data-stu-id="c0edb-108">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="c0edb-109">Jest ona również dostępna w klasie pochodnej znajdującej się w innym zestawie tylko wtedy, gdy dostęp odbywa się za pomocą zmiennej typu klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="c0edb-109">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="c0edb-110">Rozważmy na przykład następujący segment kodu:</span><span class="sxs-lookup"><span data-stu-id="c0edb-110">For example, consider the following code segment:</span></span>

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="c0edb-111">Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly2.cs` .</span><span class="sxs-lookup"><span data-stu-id="c0edb-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="c0edb-112">Pierwszy plik zawiera publiczną klasę bazową, `BaseClass` i inną klasę, `TestAccess` .</span><span class="sxs-lookup"><span data-stu-id="c0edb-112">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="c0edb-113">`BaseClass` jest właścicielem chronionego wewnętrznego elementu członkowskiego, `myValue` do którego uzyskuje dostęp `TestAccess` Typ.</span><span class="sxs-lookup"><span data-stu-id="c0edb-113">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="c0edb-114">W drugim pliku próba uzyskania dostępu `myValue` za pomocą wystąpienia `BaseClass` spowoduje błąd, podczas gdy dostęp do tego elementu członkowskiego za pomocą wystąpienia klasy pochodnej `DerivedClass` zakończy się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="c0edb-114">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="c0edb-115">Elementy członkowskie struktury nie mogą być takie same `protected internal` , ponieważ struktura nie może być dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="c0edb-115">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c0edb-116">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c0edb-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c0edb-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c0edb-117">See also</span></span>

- [<span data-ttu-id="c0edb-118">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="c0edb-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c0edb-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="c0edb-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c0edb-120">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="c0edb-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c0edb-121">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="c0edb-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="c0edb-122">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="c0edb-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="c0edb-123">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="c0edb-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="c0edb-124">public</span><span class="sxs-lookup"><span data-stu-id="c0edb-124">public</span></span>](public.md)
- [<span data-ttu-id="c0edb-125">private</span><span class="sxs-lookup"><span data-stu-id="c0edb-125">private</span></span>](private.md)
- [<span data-ttu-id="c0edb-126">internal</span><span class="sxs-lookup"><span data-stu-id="c0edb-126">internal</span></span>](internal.md)
- <span data-ttu-id="c0edb-127">[Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c0edb-127">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
