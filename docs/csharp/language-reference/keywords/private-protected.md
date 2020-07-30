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
# <a name="private-protected-c-reference"></a>Private Protected (odwołanie w C#)

`private protected`Kombinacja słowa kluczowego jest modyfikatorem dostępu składowej. Prywatna chroniona składowa jest dostępna dla typów pochodzących od klasy zawierającej, ale tylko w obrębie zawartego zestawu. Aby uzyskać porównanie `private protected` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).

> [!NOTE]
> `private protected`Modyfikator dostępu jest prawidłowy w języku C# w wersji 7,2 i nowszych.

## <a name="example"></a>Przykład

Prywatna chroniona składowa klasy bazowej jest dostępna z typów pochodnych w jego zestawie zawierającym tylko wtedy, gdy typ statyczny zmiennej jest typem klasy pochodnej. Rozważmy na przykład następujący segment kodu:

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

Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly2.cs` .
Pierwszy plik zawiera publiczną klasę bazową, `BaseClass` i typ pochodzący od niej `DerivedClass1` . `BaseClass`jest właścicielem prywatnej, chronionej składowej, `myValue` która `DerivedClass1` próbuje uzyskać dostęp na dwa sposoby. Pierwsza próba uzyskania dostępu `myValue` za pomocą wystąpienia `BaseClass` spowoduje wystąpienie błędu. Jednak próba użycia jej jako dziedziczonego elementu członkowskiego w programie powiedzie `DerivedClass1` się.

W drugim pliku próba uzyskania dostępu `myValue` jako dziedziczonego elementu członkowskiego `DerivedClass2` spowoduje wystąpienie błędu, ponieważ jest on dostępny tylko dla typów pochodnych w assembly1.

Jeśli `Assembly1.cs` zawiera <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> te nazwy `Assembly2` , Klasa pochodna `DerivedClass1` będzie miała dostęp do `private protected` elementów członkowskich zadeklarowanych w elemencie `BaseClass` . `InternalsVisibleTo`sprawia `private protected` , że elementy członkowskie są widoczne dla klas pochodnych w innych zestawach.

Elementy członkowskie struktury nie mogą być takie same `private protected` , ponieważ struktura nie może być dziedziczona.

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory dostępu](access-modifiers.md)
- [Poziomy ułatwień dostępu](accessibility-levels.md)
- [Modyfikatory](index.md)
- [public](public.md)
- [użytek](private.md)
- [internal](internal.md)
- [Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
