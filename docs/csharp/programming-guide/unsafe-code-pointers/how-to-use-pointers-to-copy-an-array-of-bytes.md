---
title: Jak używać wskaźników do kopiowania macierzy bajtów — Przewodnik programowania w języku C#
description: Dowiedz się, jak używać wskaźników do kopiowania tablicy bajtów. Zobacz przykład kodu i dodatkowe dostępne zasoby.
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 70ab1441d25ea69afb2244bd94bd404a3e32838d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381791"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a><span data-ttu-id="01baf-104">Jak używać wskaźników do kopiowania tablicy bajtów (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="01baf-104">How to use pointers to copy an array of bytes (C# Programming Guide)</span></span>

<span data-ttu-id="01baf-105">Poniższy przykład używa wskaźników do kopiowania bajtów z jednej tablicy do innej.</span><span class="sxs-lookup"><span data-stu-id="01baf-105">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="01baf-106">W tym przykładzie użyto słowa kluczowego [UNSAFE](../../language-reference/keywords/unsafe.md) , które umożliwia używanie wskaźników w `Copy` metodzie.</span><span class="sxs-lookup"><span data-stu-id="01baf-106">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="01baf-107">[Stała](../../language-reference/keywords/fixed-statement.md) Instrukcja służy do deklarowania wskaźników do tablicy źródłowej i docelowej.</span><span class="sxs-lookup"><span data-stu-id="01baf-107">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="01baf-108">`fixed`Instrukcja *przypina* lokalizację źródłową i docelową tablicę w pamięci, dzięki czemu nie będą one przenoszone przez wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="01baf-108">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="01baf-109">Bloki pamięci dla tablic są odpięte po `fixed` zakończeniu bloku.</span><span class="sxs-lookup"><span data-stu-id="01baf-109">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="01baf-110">Ponieważ `Copy` Metoda w tym przykładzie używa `unsafe` słowa kluczowego, należy ją skompilować przy użyciu opcji [niebezpiecznego](../../language-reference/compiler-options/unsafe-compiler-option.md) kompilatora.</span><span class="sxs-lookup"><span data-stu-id="01baf-110">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="01baf-111">Ten przykład uzyskuje dostęp do elementów obydwu tablic przy użyciu indeksów zamiast drugiego niezarządzanego wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="01baf-111">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="01baf-112">Deklaracja `pSource` `pTarget` wskaźników i przypina tablicę.</span><span class="sxs-lookup"><span data-stu-id="01baf-112">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="01baf-113">Ta funkcja jest dostępna od języka C# 7,3.</span><span class="sxs-lookup"><span data-stu-id="01baf-113">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="01baf-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="01baf-114">Example</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="01baf-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="01baf-115">See also</span></span>

- [<span data-ttu-id="01baf-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="01baf-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="01baf-117">Niebezpieczny kod i wskaźniki</span><span class="sxs-lookup"><span data-stu-id="01baf-117">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="01baf-118">-unsafe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="01baf-118">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [<span data-ttu-id="01baf-119">Odzyskiwanie pamięci</span><span class="sxs-lookup"><span data-stu-id="01baf-119">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
