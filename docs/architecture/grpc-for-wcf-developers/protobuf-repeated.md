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
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="841eb-103">Powtarzające się pola list i tablic</span><span class="sxs-lookup"><span data-stu-id="841eb-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="841eb-104">Należy określić listy w buforze protokołu (protobuf) za pomocą `repeated` słowa kluczowego prefix.</span><span class="sxs-lookup"><span data-stu-id="841eb-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="841eb-105">Poniższy przykład pokazuje, jak utworzyć listę:</span><span class="sxs-lookup"><span data-stu-id="841eb-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="841eb-106">W wygenerowanym kodzie `repeated` pola są reprezentowane przez właściwości tylko do odczytu typu, [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] a nie żadne wbudowane typy kolekcji programu .NET.</span><span class="sxs-lookup"><span data-stu-id="841eb-106">In the generated code, `repeated` fields are represented by read-only properties of the [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="841eb-107">Ten typ implementuje wszystkie standardowe interfejsy kolekcji .NET, takie jak <xref:System.Collections.Generic.IList%601> i <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="841eb-107">This type implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="841eb-108">Dzięki temu można używać zapytań LINQ lub łatwo konwertować je na tablicę lub listę.</span><span class="sxs-lookup"><span data-stu-id="841eb-108">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

<span data-ttu-id="841eb-109">`RepeatedField<T>`Typ zawiera kod wymagany do serializacji i deserializacji listy do formatu sieci binarnej.</span><span class="sxs-lookup"><span data-stu-id="841eb-109">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span>

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
><span data-ttu-id="841eb-110">[Poprzedni](protobuf-nested-types.md) 
> [Dalej](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="841eb-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
