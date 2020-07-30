---
title: chronione wewnętrzne odwołanie do języka C#
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: 4067da93bcceba0fa3e4a14aa58b4cde812412f3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301791"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="32f0b-102">chroniona wewnętrznie (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="32f0b-102">protected internal (C# Reference)</span></span>

<span data-ttu-id="32f0b-103">`protected internal`Kombinacja słowa kluczowego jest modyfikatorem dostępu składowej.</span><span class="sxs-lookup"><span data-stu-id="32f0b-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="32f0b-104">Chroniony wewnętrzny element członkowski jest dostępny z bieżącego zestawu lub z typów, które pochodzą od klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="32f0b-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="32f0b-105">Aby uzyskać porównanie `protected internal` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="32f0b-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="32f0b-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="32f0b-106">Example</span></span>

<span data-ttu-id="32f0b-107">Chroniona wewnętrzna składowa klasy bazowej jest dostępna z dowolnego typu w obrębie zawierającego go zestawu.</span><span class="sxs-lookup"><span data-stu-id="32f0b-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="32f0b-108">Jest ona również dostępna w klasie pochodnej znajdującej się w innym zestawie tylko wtedy, gdy dostęp odbywa się za pomocą zmiennej typu klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="32f0b-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="32f0b-109">Rozważmy na przykład następujący segment kodu:</span><span class="sxs-lookup"><span data-stu-id="32f0b-109">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="32f0b-110">Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly2.cs` .</span><span class="sxs-lookup"><span data-stu-id="32f0b-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="32f0b-111">Pierwszy plik zawiera publiczną klasę bazową, `BaseClass` i inną klasę, `TestAccess` .</span><span class="sxs-lookup"><span data-stu-id="32f0b-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="32f0b-112">`BaseClass`jest właścicielem chronionego wewnętrznego elementu członkowskiego, `myValue` do którego uzyskuje dostęp `TestAccess` Typ.</span><span class="sxs-lookup"><span data-stu-id="32f0b-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="32f0b-113">W drugim pliku próba uzyskania dostępu `myValue` za pomocą wystąpienia `BaseClass` spowoduje błąd, podczas gdy dostęp do tego elementu członkowskiego za pomocą wystąpienia klasy pochodnej `DerivedClass` zakończy się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="32f0b-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="32f0b-114">Elementy członkowskie struktury nie mogą być takie same `protected internal` , ponieważ struktura nie może być dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="32f0b-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="32f0b-115">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="32f0b-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="32f0b-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="32f0b-116">See also</span></span>

- [<span data-ttu-id="32f0b-117">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="32f0b-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="32f0b-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="32f0b-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="32f0b-119">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="32f0b-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="32f0b-120">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="32f0b-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="32f0b-121">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="32f0b-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="32f0b-122">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="32f0b-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="32f0b-123">public</span><span class="sxs-lookup"><span data-stu-id="32f0b-123">public</span></span>](public.md)
- [<span data-ttu-id="32f0b-124">użytek</span><span class="sxs-lookup"><span data-stu-id="32f0b-124">private</span></span>](private.md)
- [<span data-ttu-id="32f0b-125">internal</span><span class="sxs-lookup"><span data-stu-id="32f0b-125">internal</span></span>](internal.md)
- <span data-ttu-id="32f0b-126">[Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="32f0b-126">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
