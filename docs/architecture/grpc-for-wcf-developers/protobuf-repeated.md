---
title: Powtarzające się pola dla list i tablic — gRPC dla deweloperów WCF
description: Dowiedz się, jak protobuf obsługuje kolekcje i jak są one powiązane z kolekcjami programu .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867506"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Powtarzające się pola list i tablic

Należy określić listy w buforze protokołu (protobuf) za pomocą `repeated` słowa kluczowego prefix. Poniższy przykład pokazuje, jak utworzyć listę:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

W wygenerowanym kodzie `repeated` pola są reprezentowane przez właściwości tylko do odczytu typu, [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] a nie żadne wbudowane typy kolekcji programu .NET. Ten typ implementuje wszystkie standardowe interfejsy kolekcji .NET, takie jak <xref:System.Collections.Generic.IList%601> i <xref:System.Collections.Generic.IEnumerable%601> . Dzięki temu można używać zapytań LINQ lub łatwo konwertować je na tablicę lub listę.

`RepeatedField<T>`Typ zawiera kod wymagany do serializacji i deserializacji listy do formatu sieci binarnej.

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
>[Poprzedni](protobuf-nested-types.md) 
> [Dalej](protobuf-reserved.md)
