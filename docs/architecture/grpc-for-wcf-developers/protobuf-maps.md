---
title: Mapy protobuf dla słowników — gRPC dla deweloperów WCF
description: Zapoznaj się z tematem jak używać map protobuf do reprezentowania typów słowników w programie .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 2c2ae76d47b2309227d22235b5acbe2afa794158
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867469"
---
# <a name="protobuf-maps-for-dictionaries"></a>Mapy Protobuf dla słowników

Ważne jest, aby reprezentować dowolne kolekcje nazwanych wartości w komunikatach. W programie .NET jest to często obsługiwane przez typy słowników. Odpowiednikiem <xref:System.Collections.Generic.IDictionary%602> typu .NET w buforze protokołu (protobuf) jest `map<key_type, value_type>` Typ. W tej sekcji pokazano, jak zadeklarować `map` Typ w protobuf i jak używać wygenerowanego kodu.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

W wygenerowanym kodzie `map` pola są reprezentowane przez właściwości tylko do odczytu [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] typu. Ten typ implementuje standardowe interfejsy kolekcji .NET, w tym <xref:System.Collections.Generic.IDictionary%602> .

Nie można bezpośrednio powtarzać pól mapy w definicji komunikatu. Można jednak utworzyć zagnieżdżony komunikat zawierający mapę i użyć `repeated` jej na typ komunikatu, jak w poniższym przykładzie:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Używanie właściwości MapField w kodzie

`MapField`Właściwości generowane na podstawie `map` pól są tylko do odczytu i nigdy nie będą `null` . Aby ustawić właściwość mapy, użyj `Add(IDictionary<TKey,TValue> values)` metody na pustej właściwości, `MapField` Aby skopiować wartości z dowolnego słownika platformy .NET.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Dalsze informacje

Aby uzyskać więcej informacji na temat protobuf, zobacz oficjalną [dokumentację protobuf](https://developers.google.com/protocol-buffers/docs/overview).

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
>[Poprzedni](protobuf-enums.md) 
> [Dalej](wcf-services-to-grpc-comparison.md)
