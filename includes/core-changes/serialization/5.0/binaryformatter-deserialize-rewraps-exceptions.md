---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517359"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>Metoda teraz ponownie pakuje niektóre obiekty wyjątków wewnątrz a <xref:System.Runtime.Serialization.SerializationException> przed propagacją wyjątku z powrotem do obiektu wywołującego.

#### <a name="change-description"></a>Zmień opis

Wcześniej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda umożliwiała niektóre dowolne wyjątki, takie jak <xref:System.ArgumentNullException> , aby propagować stos do jego obiektów wywołujących.

W programie .NET 5,0 i nowszych <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda bardziej agresywnie przechwytuje wyjątki, które występują z powodu nieprawidłowych operacji deserializacji i zawija je w <xref:System.Runtime.Serialization.SerializationException> .

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 1

#### <a name="recommended-action"></a>Zalecana akcja

W większości przypadków nie trzeba podejmować żadnych działań. Jeśli jednak lokacja wywołania zależy od zgłoszonego wyjątku, można Odpakuj wyjątek z elementu zewnętrznego <xref:System.Runtime.Serialization.SerializationException> , jak pokazano w poniższym przykładzie.

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a>Kategoria

Serializacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
