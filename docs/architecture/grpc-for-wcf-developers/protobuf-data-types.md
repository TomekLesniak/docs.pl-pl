---
title: Protobuf typy danych skalarnych — gRPC dla deweloperów WCF
description: Dowiedz się więcej o podstawowych i dobrze znanych typach danych, które obsługują protobuf i gRPC w programie .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: 5447067b953d257258950d020636e0b38245e20d
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573647"
---
# <a name="protobuf-scalar-data-types"></a>Typy danych skalarnych Protobuf

Bufor protokołu (protobuf) obsługuje zakres natywnych typów wartości skalarnych. W poniższej tabeli wymieniono wszystkie ich równoważne typy C#:

| Typ protobuf | Typ C#      | Uwagi |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

Uwagi:

1. Standardowe kodowanie dla `int32` i `int64` jest niewydajne podczas pracy z podpisanymi wartościami. Jeśli pole może zawierać liczby ujemne, użyj `sint32` lub `sint64` zamiast. Te typy są mapowane odpowiednio do języka C# `int` i `long` typów.
2. `fixed`Pola zawsze używają tej samej liczby bajtów niezależnie od tego, co jest wartością. Takie zachowanie powoduje szybsze wykonywanie serializacji i deserializacji w przypadku większych wartości.
3. Ciągi protobuf są kodowane w formacie UTF-8 (lub 7-bitowym ASCII). Zakodowana długość nie może być większa niż 2<sup>32</sup>.
4. Środowisko uruchomieniowe protobuf zapewnia `ByteString` Typ, który umożliwia łatwe mapowanie do i z `byte[]` tablic C#.

## <a name="other-net-primitive-types"></a>Inne typy pierwotne platformy .NET

### <a name="dates-and-times"></a>Daty i godziny

Natywne typy skalarne nie zapewniają wartości daty i godziny, równoważne do języka C# <xref:System.DateTimeOffset> , <xref:System.DateTime> i <xref:System.TimeSpan> . Te typy można określić za pomocą niektórych rozszerzeń "dobrze znane typy" firmy Google. Rozszerzenia te zapewniają obsługę generowania kodu i środowiska uruchomieniowego dla złożonych typów pól na obsługiwanych platformach.

W poniższej tabeli przedstawiono typy daty i godziny:

| Typ C# | Nieznany typ protobuf |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

Wygenerowane właściwości klasy C# nie są typami dat i godzin platformy .NET. Właściwości używają `Timestamp` `Duration` klas i w `Google.Protobuf.WellKnownTypes` przestrzeni nazw. Klasy te zapewniają metody konwersji do i z `DateTimeOffset` , `DateTime` i `TimeSpan` .

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> `Timestamp`Typ działa z czasem UTC. `DateTimeOffset` wartości zawsze mają przesunięcie zero, a `DateTime.Kind` Właściwość jest zawsze `DateTimeKind.Utc` .

### <a name="systemguid"></a>System. GUID

Protobuf nie obsługuje bezpośrednio <xref:System.Guid> typu, znanego tak jak `UUID` na innych platformach. Nie ma dobrze znanego typu.

Najlepszym rozwiązaniem jest obsługa `Guid` wartości jako `string` pola przy użyciu standardowego `8-4-4-4-12` formatu szesnastkowego (na przykład `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` ). Wszystkie języki i platformy mogą przeanalizować ten format.

Nie używaj `bytes` pola dla `Guid` wartości. Problemy z *przydziałami* ([Definicja witryny Wikipedia](https://en.wikipedia.org/wiki/Endianness)) mogą spowodować błędne zachowanie, gdy protobuf się z innymi platformami, takimi jak Java.

### <a name="nullable-types"></a>Typy dopuszczające wartości null

Generowanie kodu protobuf dla języka C# używa typów natywnych, takich jak `int` for `int32` . Dlatego wartości są zawsze uwzględniane i nie mogą mieć wartości null.

Dla wartości, które wymagają jawnej wartości null, na przykład używania `int?` w kodzie c#, protobuf "dobrze znane typy" obejmują otoki, które są kompilowane do typów dopuszczających wartość null. Aby go użyć, zaimportuj `wrappers.proto` do `.proto` pliku, tak jak to:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf będzie używać prostego `T?` (na przykład `int?` ) dla wygenerowanej właściwości wiadomości.

W poniższej tabeli przedstawiono pełną listę typów otoki z równoważnym typem języka C#:

| Typ C#   | Otoka dobrze znanego typu       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Dobrze znane typy `Timestamp` i `Duration` są reprezentowane w .NET jako klasy. W języku C# 8 i poza, można użyć typów referencyjnych dopuszczających wartość null. Należy jednak pamiętać o wartości null we właściwościach tych typów podczas konwertowania na `DateTimeOffset` lub `TimeSpan` .

## <a name="decimals"></a>Miejsca dziesiętne

Protobuf nie obsługuje natywnie typu .NET `decimal` , tylko `double` i `float` . W projekcie protobuf istnieje trwająca dyskusja dotycząca możliwości dodawania `Decimal` typu standardowego do dobrze znanych typów, z obsługą platformy dla języków i struktur, które je obsługują. Nic nie zostało jeszcze zaimplementowane.

Istnieje możliwość utworzenia definicji komunikatu reprezentującej `decimal` Typ, który będzie działał do bezpiecznej serializacji między klientami i serwerami platformy .NET. Jednak deweloperzy na innych platformach będą musieli zrozumieć używany format i zaimplementować ich własny sposób obsługi.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Tworzenie niestandardowego typu dziesiętnego dla protobuf

Prosta implementacja może być podobna do typu niestandardowego, `Money` który jest używany przez niektóre interfejsy API usługi Google, bez tego `currency` pola.

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message DecimalValue {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

`nanos`Pole reprezentuje wartości z `0.999_999_999` do `-0.999_999_999` . Na przykład `decimal` wartość `1.5m` będzie reprezentowana jako `{ units = 1, nanos = 500_000_000 }` . To dlatego, że `nanos` pole w tym przykładzie używa `sfixed32` typu, który koduje bardziej wydajne niż `int32` w przypadku większych wartości. Jeśli `units` pole jest ujemne, `nanos` pole powinno również być ujemne.

> [!NOTE]
> Istnieje wiele innych algorytmów kodowania `decimal` wartości jako ciągi bajtowe, ale ten komunikat jest łatwiejszy do zrozumienia niż którekolwiek z nich. Nie ma to wpływ na wartości endian na różnych platformach.

Konwersję między tym typem a typem BCL można `decimal` zaimplementować w języku C# w następujący sposób:

```csharp
namespace CustomTypes
{
    public partial class DecimalValue
    {
        private const decimal NanoFactor = 1_000_000_000;
        public DecimalValue(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.DecimalValue grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.DecimalValue(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.DecimalValue(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> Za każdym razem, gdy używasz niestandardowych typów komunikatów, takich jak ta, *musisz* udokumentować je za pomocą komentarzy w `.proto` . Inni deweloperzy mogą następnie zaimplementować konwersję do i z równoważnego typu w własnym języku lub strukturze.

>[!div class="step-by-step"]
>[Poprzedni](protobuf-messages.md) 
> [Dalej](protobuf-nested-types.md)
