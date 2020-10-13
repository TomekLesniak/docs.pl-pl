---
ms.openlocfilehash: 572ebc47d26e30738fc4e5b8a8fab1f2643e3d83
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997730"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a>Niepubliczne konstruktory bez parametrów, które nie są używane do deserializacji

Aby zapewnić spójność wszystkich obsługiwanych monikerów platformy docelowej (TFMs), niepubliczne konstruktory bez parametrów nie są już używane do deserializacji z <xref:System.Text.Json.JsonSerializer> , domyślnie.

#### <a name="change-description"></a>Zmień opis

W przypadku programu .NET Core 3,0 i 3,1 konstruktory wewnętrzne i prywatne mogą służyć do deserializacji. W przypadku .NET Standard 2,0 i 2,1 konstruktory wewnętrzne i prywatne są niedozwolone i <xref:System.MissingMethodException> są generowane, jeśli nie jest zdefiniowany publiczny Konstruktor bez parametrów.

Począwszy od programu .NET 5,0, konstruktory niepubliczne, w tym konstruktory bez parametrów, są domyślnie ignorowane przez serializator. Serializator używa jednego z następujących konstruktorów do deserializacji:

- Konstruktor publiczny z adnotacją <xref:System.Text.Json.Serialization.JsonConstructorAttribute> .
- Publiczny Konstruktor bez parametrów.
- Publiczny Konstruktor sparametryzowany (jeśli jest to jedyny Konstruktor publiczny obecny).

Jeśli żaden z tych konstruktorów nie jest dostępny, <xref:System.NotSupportedException> jest zgłaszany w przypadku próby deserializacji typu.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="reason-for-change"></a>Przyczyna zmiany

- Aby wymusić spójne zachowanie między wszystkimi monikerami platformy docelowej (TFMs), które <xref:System.Text.Json?displayProperty=fullName> kompilują program (.NET Core 3,0 i nowsze wersje oraz .NET Standard 2,0 i 2,1)
- Ponieważ <xref:System.Text.Json.JsonSerializer> nie należy wywoływać obszaru powierzchni niepublicznej typu, niezależnie od tego, czy jest to Konstruktor, właściwość, czy pole.

#### <a name="recommended-action"></a>Zalecana akcja

- Jeśli jesteś własnością typu i jest to możliwe, ustaw konstruktora bez parametrów jako publiczny.
- W przeciwnym razie należy zaimplementować `JsonConverter<T>` dla typu i kontrolować zachowanie deserializacji.

#### <a name="category"></a>Kategoria

Serializacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
