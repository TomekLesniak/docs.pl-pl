---
ms.openlocfilehash: 6c120f155660863ce5ae3cf5bd81ea858a68ef8d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496604"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer nie może zdeserializować serializacji ConcurrentDictionary z inną wersją platformy .NET

#### <a name="details"></a>Szczegóły

Zgodnie z projektem, <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> może być używany tylko wtedy, gdy obie operacje serializacji i deserializacji współużytkują te same typy CLR. W związku z tym nie jest gwarantowane, że serializacja obiektu za pomocą jednej wersji .NET Framework może zostać odszeregowana przez inną wersję.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> to typ, który jest znany jako nie do poprawnego deserializacji, jeśli jest serializowany z .NET Framework 4,5 lub wcześniejszym i deserializowany z .NET Framework 4.5.1 lub nowszym.

#### <a name="suggestion"></a>Sugestia

Istnieje wiele możliwych obejścia tego problemu:<ul><li>Uaktualnij komputer serializowany, aby używał również .NET Framework 4.5.1.</li><li>Użyj <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> zamiast <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> tego, ponieważ nie oczekuje to dokładnie tych samych typów CLR zarówno w serializacji, jak i deserializacji zakończenia.</li><li>Użyj <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> zamiast <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> tego, ponieważ nie wykazuje tego konkretnego podziału 4,5- &gt; 4.5.1.</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)`

-->
