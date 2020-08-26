---
title: Wyliczenia
description: 'Dowiedz się, jak używać wyliczenia F # zamiast literałów, aby kod był bardziej czytelny i konserwowany.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812110"
---
# <a name="enumerations"></a><span data-ttu-id="86cb1-103">Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="86cb1-103">Enumerations</span></span>

<span data-ttu-id="86cb1-104">*Wyliczenia*, znane także jako *wyliczenia*, są typami całkowitymi, w których etykiety są przypisywane do podzestawu wartości.</span><span class="sxs-lookup"><span data-stu-id="86cb1-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="86cb1-105">Można ich użyć zamiast literałów, aby kod był bardziej czytelny i możliwy do utrzymania.</span><span class="sxs-lookup"><span data-stu-id="86cb1-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="86cb1-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="86cb1-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="86cb1-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="86cb1-107">Remarks</span></span>

<span data-ttu-id="86cb1-108">Wyliczenie wygląda podobnie jak Unia rozłączna, która ma proste wartości, z tą różnicą, że można określić wartości.</span><span class="sxs-lookup"><span data-stu-id="86cb1-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="86cb1-109">Wartości są zwykle liczbami całkowitymi, które zaczynają się od 0 lub 1 lub liczby całkowite reprezentujące pozycje bitowe.</span><span class="sxs-lookup"><span data-stu-id="86cb1-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="86cb1-110">Jeśli Wyliczenie jest przeznaczone do reprezentowania pozycji bitowych, należy również użyć atrybutu [flags](xref:System.FlagsAttribute) .</span><span class="sxs-lookup"><span data-stu-id="86cb1-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="86cb1-111">Typ podstawowy wyliczenia jest określany na podstawie literału, który jest używany, aby na przykład można było użyć literałów z sufiksem, takim jak `1u` , `2u` , i tak dalej, dla typu Liczba całkowita bez znaku ( `uint32` ).</span><span class="sxs-lookup"><span data-stu-id="86cb1-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="86cb1-112">Gdy odwołujesz się do nazwanych wartości, musisz użyć nazwy typu wyliczenia jako kwalifikatora, czyli `enum-name.value1` nie tylko `value1` .</span><span class="sxs-lookup"><span data-stu-id="86cb1-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="86cb1-113">To zachowanie różni się od tych związków rozłącznych.</span><span class="sxs-lookup"><span data-stu-id="86cb1-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="86cb1-114">Wynika to z faktu, że wyliczenia mają zawsze atrybut [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="86cb1-114">This is because enumerations always have the [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) attribute.</span></span>

<span data-ttu-id="86cb1-115">Poniższy kod przedstawia deklarację i użycie wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="86cb1-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="86cb1-116">Wyliczenia można łatwo przekonwertować na typ podstawowy przy użyciu odpowiedniego operatora, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="86cb1-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="86cb1-117">Typy wyliczeniowe mogą mieć jeden z następujących typów podstawowych: `sbyte` ,,,,, `byte` `int16` `uint16` `int32` `uint32` , `int64` , `uint16` , `uint64` , i `char` .</span><span class="sxs-lookup"><span data-stu-id="86cb1-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="86cb1-118">Typy wyliczeniowe są reprezentowane w .NET Framework jako typy dziedziczone z `System.Enum` , które z kolei są dziedziczone z `System.ValueType` .</span><span class="sxs-lookup"><span data-stu-id="86cb1-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="86cb1-119">Z tego względu są to typy wartości, które znajdują się na stosie lub są wbudowane w obiekt zawierający, a każda wartość typu podstawowego jest prawidłową wartością wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="86cb1-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="86cb1-120">Jest to istotne w przypadku dopasowania wzorców do wartości wyliczenia, ponieważ należy dostarczyć wzorzec, który przechwytuje wartości nienazwanych.</span><span class="sxs-lookup"><span data-stu-id="86cb1-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="86cb1-121">`enum`Funkcja w bibliotece języka F # może służyć do generowania wartości wyliczenia, nawet wartości innej niż jedna ze wstępnie zdefiniowanych wartości nazwanych.</span><span class="sxs-lookup"><span data-stu-id="86cb1-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="86cb1-122">Używasz `enum` funkcji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="86cb1-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="86cb1-123">Funkcja Domyślna `enum` działa z typem `int32` .</span><span class="sxs-lookup"><span data-stu-id="86cb1-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="86cb1-124">W związku z tym nie można jej używać z typami wyliczeniowymi, które mają inne typy podstawowe.</span><span class="sxs-lookup"><span data-stu-id="86cb1-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="86cb1-125">Zamiast tego należy użyć poniższego polecenia.</span><span class="sxs-lookup"><span data-stu-id="86cb1-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="86cb1-126">Ponadto przypadki wyliczeniowe są zawsze emitowane jako `public` .</span><span class="sxs-lookup"><span data-stu-id="86cb1-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="86cb1-127">Jest to tak, aby były wyrównane do języka C# i reszty platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="86cb1-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="86cb1-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="86cb1-128">See also</span></span>

- [<span data-ttu-id="86cb1-129">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="86cb1-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="86cb1-130">Rzutowanie i konwersje</span><span class="sxs-lookup"><span data-stu-id="86cb1-130">Casting and Conversions</span></span>](casting-and-conversions.md)
