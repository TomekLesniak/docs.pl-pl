---
title: Bufory o ustalonym rozmiarze — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat buforów o ustalonym rozmiarze. Bufory o ustalonym rozmiarze są używane do pisania metod współdziałania ze źródłami danych z innych języków.
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 1d4f5068121cdc98976954f2d99f4ac020c3b2a8
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381245"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="e8852-104">Bufory o ustalonym rozmiarze (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e8852-104">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="e8852-105">W języku C# można użyć instrukcji [FIXED](../../language-reference/keywords/fixed-statement.md) do utworzenia buforu z tablicą o stałym rozmiarze w strukturze danych.</span><span class="sxs-lookup"><span data-stu-id="e8852-105">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="e8852-106">Bufory o ustalonym rozmiarze są przydatne podczas pisania metod, które współdziałają ze źródłami danych z innych języków lub platform.</span><span class="sxs-lookup"><span data-stu-id="e8852-106">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="e8852-107">Stała tablica może przyjmować wszelkie atrybuty lub modyfikatory, które są dozwolone dla zwykłych elementów członkowskich struktury.</span><span class="sxs-lookup"><span data-stu-id="e8852-107">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="e8852-108">Jedynym ograniczeniem jest to, że typem tablicy musi być,,,,,,,,,, `bool` `byte` `char` `short` `int` `long` `sbyte` `ushort` `uint` `ulong` `float` lub `double` .</span><span class="sxs-lookup"><span data-stu-id="e8852-108">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="e8852-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e8852-109">Remarks</span></span>

<span data-ttu-id="e8852-110">W bezpiecznym kodzie struktura języka C#, która zawiera tablicę, nie zawiera elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="e8852-110">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="e8852-111">Zamiast tego, struktura zawiera odwołanie do elementów.</span><span class="sxs-lookup"><span data-stu-id="e8852-111">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="e8852-112">Można osadzić tablicę o stałym rozmiarze w [strukturze](../../language-reference/builtin-types/struct.md) , gdy jest ona używana w [niebezpiecznym](../../language-reference/keywords/unsafe.md) bloku kodu.</span><span class="sxs-lookup"><span data-stu-id="e8852-112">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="e8852-113">Poniższe rozmiary `struct` nie zależą od liczby elementów w tablicy, ponieważ `pathName` jest odwołaniem:</span><span class="sxs-lookup"><span data-stu-id="e8852-113">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](snippets/FixedKeywordExamples.cs#6)]

<span data-ttu-id="e8852-114">`struct`Może zawierać osadzoną tablicę w niebezpiecznym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e8852-114">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="e8852-115">W poniższym przykładzie `fixedBuffer` Tablica ma stały rozmiar.</span><span class="sxs-lookup"><span data-stu-id="e8852-115">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="e8852-116">Używasz instrukcji, `fixed` Aby nawiązać wskaźnik do pierwszego elementu.</span><span class="sxs-lookup"><span data-stu-id="e8852-116">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="e8852-117">Dostęp do elementów tablicy można uzyskać za pomocą tego wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="e8852-117">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="e8852-118">`fixed`Instrukcja przypina `fixedBuffer` pole wystąpienia do określonej lokalizacji w pamięci.</span><span class="sxs-lookup"><span data-stu-id="e8852-118">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#7)]

<span data-ttu-id="e8852-119">Rozmiar tablicy elementów 128 `char` wynosi 256 bajtów.</span><span class="sxs-lookup"><span data-stu-id="e8852-119">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="e8852-120">Bufory [znaków](../../language-reference/builtin-types/char.md) o stałym rozmiarze zawsze pobierają dwa bajty na znak, niezależnie od kodowania.</span><span class="sxs-lookup"><span data-stu-id="e8852-120">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="e8852-121">Jest to prawdziwe nawet wtedy, gdy bufory char są organizowane do metod interfejsu API lub struktur z `CharSet = CharSet.Auto` lub `CharSet = CharSet.Ansi` .</span><span class="sxs-lookup"><span data-stu-id="e8852-121">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="e8852-122">Aby uzyskać więcej informacji, zobacz <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="e8852-122">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="e8852-123">W poprzednim przykładzie pokazano dostęp do `fixed` pól bez przypinania, które są dostępne od języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="e8852-123">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="e8852-124">Inna wspólna tablica o stałym rozmiarze jest tablicą [logiczną](../../language-reference/builtin-types/bool.md) .</span><span class="sxs-lookup"><span data-stu-id="e8852-124">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="e8852-125">Elementy w `bool` tablicy mają zawsze jeden bajt w rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="e8852-125">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="e8852-126">`bool`Tablice nie są odpowiednie do tworzenia tablic bitowych lub buforów.</span><span class="sxs-lookup"><span data-stu-id="e8852-126">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="e8852-127">Bufory o ustalonym rozmiarze są kompilowane przy użyciu <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType> , który instruuje środowisko uruchomieniowe języka wspólnego (CLR), że typ zawiera niezarządzaną tablicę, która może być przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="e8852-127">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="e8852-128">Jest to podobne do pamięci utworzonej za pomocą [stackalloc](../../language-reference/operators/stackalloc.md), co powoduje automatyczne włączenie funkcji wykrywania przepełnienia buforu w środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="e8852-128">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="e8852-129">W poprzednim przykładzie pokazano, jak bufor o ustalonym rozmiarze może istnieć w `unsafe struct` .</span><span class="sxs-lookup"><span data-stu-id="e8852-129">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="e8852-130">Kompilator wygenerował C# dla `Buffer` , ma następujący atrybut:</span><span class="sxs-lookup"><span data-stu-id="e8852-130">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

<span data-ttu-id="e8852-131">Bufory o ustalonym rozmiarze różnią się od zwykłych tablic w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e8852-131">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="e8852-132">Może być używany tylko w [niebezpiecznym](../../language-reference/keywords/unsafe.md) kontekście.</span><span class="sxs-lookup"><span data-stu-id="e8852-132">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="e8852-133">Mogą to być tylko pola struktur.</span><span class="sxs-lookup"><span data-stu-id="e8852-133">May only be instance fields of structs.</span></span>
- <span data-ttu-id="e8852-134">Są one zawsze wektorami lub tablic jednowymiarowych.</span><span class="sxs-lookup"><span data-stu-id="e8852-134">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="e8852-135">Deklaracja powinna zawierać długość, taką jak `fixed char id[8]` .</span><span class="sxs-lookup"><span data-stu-id="e8852-135">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="e8852-136">Nie można użyć `fixed char id[]` .</span><span class="sxs-lookup"><span data-stu-id="e8852-136">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8852-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e8852-137">See also</span></span>

- [<span data-ttu-id="e8852-138">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e8852-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e8852-139">Niebezpieczny kod i wskaźniki</span><span class="sxs-lookup"><span data-stu-id="e8852-139">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="e8852-140">fixed, instrukcja</span><span class="sxs-lookup"><span data-stu-id="e8852-140">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="e8852-141">Współdziałanie</span><span class="sxs-lookup"><span data-stu-id="e8852-141">Interoperability</span></span>](../interop/index.md)
