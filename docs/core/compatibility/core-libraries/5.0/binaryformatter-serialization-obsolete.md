---
title: 'Istotna zmiana: metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w podstawowych bibliotekach .NET, w których metody serializacji i deserializacji w BinaryFormatter, programie formatującego i IFormatter są przestarzałe.
ms.date: 11/01/2020
ms.openlocfilehash: 5807a7d4e6beab26b9848b803922396dd893075b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761527"
---
# <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET

`Serialize` i `Deserialize` metody w <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> , <xref:System.Runtime.Serialization.Formatter> , i <xref:System.Runtime.Serialization.IFormatter> są obecnie przestarzałe jako ostrzeżenie. Ponadto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Serializacja jest zabroniona domyślnie dla aplikacji ASP.NET.

## <a name="change-description"></a>Zmień opis

Ze względu na [luki w zabezpieczeniach](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) w programie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> następujące metody są obecnie przestarzałe i generują ostrzeżenie w czasie kompilacji o identyfikatorze `SYSLIB0011` . Ponadto w ASP.NET Core 5,0 i nowszych aplikacje będą <xref:System.NotSupportedException> zgłaszać, chyba że aplikacja sieci Web nie ma ponownie włączonej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> funkcjonalności.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

Następujące metody serializacji są również przestarzałe i generują ostrzeżenie `SYSLIB0011` , ale nie mają żadnych zmian w zachowaniu:

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="reason-for-change"></a>Przyczyna zmiany

Te metody są oznaczone jako przestarzałe w ramach wysiłku w celu wyróżnienia użycia <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> w ekosystemie platformy .NET.

## <a name="recommended-action"></a>Zalecana akcja

- Przestań używać <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> w kodzie. Zamiast tego należy rozważyć użycie <xref:System.Text.Json.JsonSerializer> lub <xref:System.Xml.Serialization.XmlSerializer> . Aby uzyskać więcej informacji, zobacz [Przewodnik po zabezpieczeniach BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).

- Można tymczasowo pominąć ostrzeżenie w <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> czasie kompilacji, czyli `SYSLIB0011` . Zalecamy gruntowną ocenę kodu przed wybraniem tej opcji. Najprostszym sposobem, aby pominąć ostrzeżenia, jest obcinanie poszczególnych lokacji wywołań do `#pragma` dyrektywy.

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  Możesz również pominąć ostrzeżenie w pliku projektu.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  W przypadku pominięcia ostrzeżenia w pliku projektu ostrzeżenie zostanie pominięte dla wszystkich plików kodu w projekcie. Pomijanie `SYSLIB0011` nie pomija ostrzeżeń spowodowanych przez użycie innych przestarzałych interfejsów API.

- Aby nadal korzystać <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> z aplikacji ASP.NET, możesz włączyć ją ponownie w pliku projektu. Jednak zdecydowanie nie jest to zalecane. Aby uzyskać więcej informacji, zobacz [Przewodnik po zabezpieczeniach BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

Aby uzyskać więcej informacji na temat zalecanych akcji, zobacz [Rozwiązywanie problemów z BinaryFormatter obsoletion i wyłączanie](https://aka.ms/binaryformatter).

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET Core

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
