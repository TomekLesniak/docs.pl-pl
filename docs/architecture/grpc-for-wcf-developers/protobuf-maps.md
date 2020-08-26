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
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="70187-103">Mapy Protobuf dla słowników</span><span class="sxs-lookup"><span data-stu-id="70187-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="70187-104">Ważne jest, aby reprezentować dowolne kolekcje nazwanych wartości w komunikatach.</span><span class="sxs-lookup"><span data-stu-id="70187-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="70187-105">W programie .NET jest to często obsługiwane przez typy słowników.</span><span class="sxs-lookup"><span data-stu-id="70187-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="70187-106">Odpowiednikiem <xref:System.Collections.Generic.IDictionary%602> typu .NET w buforze protokołu (protobuf) jest `map<key_type, value_type>` Typ.</span><span class="sxs-lookup"><span data-stu-id="70187-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="70187-107">W tej sekcji pokazano, jak zadeklarować `map` Typ w protobuf i jak używać wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="70187-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="70187-108">W wygenerowanym kodzie `map` pola są reprezentowane przez właściwości tylko do odczytu [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] typu.</span><span class="sxs-lookup"><span data-stu-id="70187-108">In the generated code, `map` fields are represented by read-only properties of the [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] type.</span></span> <span data-ttu-id="70187-109">Ten typ implementuje standardowe interfejsy kolekcji .NET, w tym <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="70187-109">This type implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="70187-110">Nie można bezpośrednio powtarzać pól mapy w definicji komunikatu.</span><span class="sxs-lookup"><span data-stu-id="70187-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="70187-111">Można jednak utworzyć zagnieżdżony komunikat zawierający mapę i użyć `repeated` jej na typ komunikatu, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="70187-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="70187-112">Używanie właściwości MapField w kodzie</span><span class="sxs-lookup"><span data-stu-id="70187-112">Using MapField properties in code</span></span>

<span data-ttu-id="70187-113">`MapField`Właściwości generowane na podstawie `map` pól są tylko do odczytu i nigdy nie będą `null` .</span><span class="sxs-lookup"><span data-stu-id="70187-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="70187-114">Aby ustawić właściwość mapy, użyj `Add(IDictionary<TKey,TValue> values)` metody na pustej właściwości, `MapField` Aby skopiować wartości z dowolnego słownika platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="70187-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="70187-115">Dalsze informacje</span><span class="sxs-lookup"><span data-stu-id="70187-115">Further reading</span></span>

<span data-ttu-id="70187-116">Aby uzyskać więcej informacji na temat protobuf, zobacz oficjalną [dokumentację protobuf](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="70187-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
><span data-ttu-id="70187-117">[Poprzedni](protobuf-enums.md) 
> [Dalej](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="70187-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
