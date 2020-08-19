---
title: Typy podstawowe
description: 'Znajdź podstawowe typy podstawowe, które są używane w języku F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 659ac8424c62985affcca1741e1b2a74c9c3ee8d
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557701"
---
# <a name="basic-types"></a><span data-ttu-id="0af6f-103">Typy podstawowe</span><span class="sxs-lookup"><span data-stu-id="0af6f-103">Basic types</span></span>

<span data-ttu-id="0af6f-104">W tym temacie wymieniono podstawowe typy, które są zdefiniowane w języku F #.</span><span class="sxs-lookup"><span data-stu-id="0af6f-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="0af6f-105">Te typy są najbardziej podstawowe w języku F #, co jest podstawą niemal każdego programu w języku F #.</span><span class="sxs-lookup"><span data-stu-id="0af6f-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="0af6f-106">Są one nadzbiorem typów pierwotnych platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0af6f-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="0af6f-107">Typ</span><span class="sxs-lookup"><span data-stu-id="0af6f-107">Type</span></span>|<span data-ttu-id="0af6f-108">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="0af6f-108">.NET type</span></span>|<span data-ttu-id="0af6f-109">Opis</span><span class="sxs-lookup"><span data-stu-id="0af6f-109">Description</span></span>|<span data-ttu-id="0af6f-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="0af6f-110">Example</span></span>|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="0af6f-111">Możliwe wartości to `true` i `false` .</span><span class="sxs-lookup"><span data-stu-id="0af6f-111">Possible values are `true` and `false`.</span></span>|`true`/`false`|
|`byte`|<xref:System.Byte>|<span data-ttu-id="0af6f-112">Wartości od 0 do 255.</span><span class="sxs-lookup"><span data-stu-id="0af6f-112">Values from 0 to 255.</span></span>|`1uy`|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="0af6f-113">Wartości od-128 do 127.</span><span class="sxs-lookup"><span data-stu-id="0af6f-113">Values from -128 to 127.</span></span>|`1y`|
|`int16`|<xref:System.Int16>|<span data-ttu-id="0af6f-114">Wartości od-32768 do 32767.</span><span class="sxs-lookup"><span data-stu-id="0af6f-114">Values from -32768 to 32767.</span></span>|`1s`|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="0af6f-115">Wartości od 0 do 65535.</span><span class="sxs-lookup"><span data-stu-id="0af6f-115">Values from 0 to 65535.</span></span>|`1us`|
|`int`|<xref:System.Int32>|<span data-ttu-id="0af6f-116">Wartości od-2 147 483 648 do 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="0af6f-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|`1`|
|`uint`|<xref:System.UInt32>|<span data-ttu-id="0af6f-117">Wartości od 0 do 4 294 967 295.</span><span class="sxs-lookup"><span data-stu-id="0af6f-117">Values from 0 to 4,294,967,295.</span></span>|`1u`|
|`int64`|<xref:System.Int64>|<span data-ttu-id="0af6f-118">Wartości z-zakresu od do 9 223 372 036 854 775 807.</span><span class="sxs-lookup"><span data-stu-id="0af6f-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|`1L`|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="0af6f-119">Wartości od 0 do 18446744073709551615 są.</span><span class="sxs-lookup"><span data-stu-id="0af6f-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|`1UL`|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="0af6f-120">Natywny wskaźnik jako liczbę całkowitą ze znakiem.</span><span class="sxs-lookup"><span data-stu-id="0af6f-120">A native pointer as a signed integer.</span></span>|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="0af6f-121">Natywny wskaźnik jako liczbę całkowitą bez znaku.</span><span class="sxs-lookup"><span data-stu-id="0af6f-121">A native pointer as an unsigned integer.</span></span>|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="0af6f-122">Zmiennoprzecinkowy typ danych, który ma co najmniej 28 znaczących cyfr.</span><span class="sxs-lookup"><span data-stu-id="0af6f-122">A floating point data type that has at least 28 significant digits.</span></span>|`1.0`|
|<span data-ttu-id="0af6f-123">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="0af6f-123">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="0af6f-124">64-bitowy typ zmiennoprzecinkowy.</span><span class="sxs-lookup"><span data-stu-id="0af6f-124">A 64-bit floating point type.</span></span>|`1.0`|
|<span data-ttu-id="0af6f-125">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="0af6f-125">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="0af6f-126">32-bitowy typ zmiennoprzecinkowy.</span><span class="sxs-lookup"><span data-stu-id="0af6f-126">A 32-bit floating point type.</span></span>|`1.0f`|
|`char`|<xref:System.Char>|<span data-ttu-id="0af6f-127">Wartości znaków Unicode.</span><span class="sxs-lookup"><span data-stu-id="0af6f-127">Unicode character values.</span></span>|`'c'`|
|`string`|<xref:System.String>|<span data-ttu-id="0af6f-128">Tekst Unicode.</span><span class="sxs-lookup"><span data-stu-id="0af6f-128">Unicode text.</span></span>|`"str"`|
|`unit`|<span data-ttu-id="0af6f-129">nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="0af6f-129">not applicable</span></span>|<span data-ttu-id="0af6f-130">Wskazuje brak wartości rzeczywistej.</span><span class="sxs-lookup"><span data-stu-id="0af6f-130">Indicates the absence of an actual value.</span></span> <span data-ttu-id="0af6f-131">Typ ma tylko jedną wartość formalną, która jest oznaczona `()` .</span><span class="sxs-lookup"><span data-stu-id="0af6f-131">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="0af6f-132">Wartość jednostki, `()` ,, jest często używana jako symbol zastępczy, gdzie wartość jest wymagana, ale żadna wartość rzeczywista nie jest dostępna lub nie ma sensu.</span><span class="sxs-lookup"><span data-stu-id="0af6f-132">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|`()`|

> [!NOTE]
> <span data-ttu-id="0af6f-133">Za pomocą typu [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) można wykonać obliczenia z liczbą całkowitą za dużą dla typu 64-bitowego liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="0af6f-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) type.</span></span> <span data-ttu-id="0af6f-134">`bigint` nie jest uznawany za typ podstawowy; jest to skrót dla `System.Numerics.BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="0af6f-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0af6f-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0af6f-135">See also</span></span>

- [<span data-ttu-id="0af6f-136">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="0af6f-136">F# Language Reference</span></span>](index.md)
