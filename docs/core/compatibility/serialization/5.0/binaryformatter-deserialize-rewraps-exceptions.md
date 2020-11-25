---
title: 'Nieprzerwana zmiana: BinaryFormatter. deserializacji odpakuje niektóre wyjątki'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie BinaryFormatter. defragmentuje odpakuje niektóre obiekty wyjątków wewnątrz SerializationException.
ms.date: 08/18/2020
ms.openlocfilehash: 90dc4cce6785fdb38644cca2a2e9aff65eb7a313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761432"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>Metoda teraz ponownie pakuje niektóre obiekty wyjątków wewnątrz a <xref:System.Runtime.Serialization.SerializationException> przed propagacją wyjątku z powrotem do obiektu wywołującego.

## <a name="change-description"></a>Zmień opis

Wcześniej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda umożliwiała niektóre dowolne wyjątki, takie jak <xref:System.ArgumentNullException> , aby propagować stos do jego obiektów wywołujących.

W programie .NET 5,0 i nowszych <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda bardziej agresywnie przechwytuje wyjątki, które występują z powodu nieprawidłowych operacji deserializacji i zawija je w <xref:System.Runtime.Serialization.SerializationException> .

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

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
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
