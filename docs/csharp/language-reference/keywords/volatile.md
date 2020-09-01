---
description: volatile — odwołanie w C#
title: volatile — odwołanie w C#
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: bb89e99e8e28ff1e263817f498619dbfae700a50
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141702"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="3d766-103">volatile (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="3d766-103">volatile (C# Reference)</span></span>

<span data-ttu-id="3d766-104">`volatile`Słowo kluczowe wskazuje, że pole może być modyfikowane przez wiele wątków, które są wykonywane w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="3d766-104">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="3d766-105">Kompilator, system środowiska uruchomieniowego i nawet sprzęt mogą zmieniać rozmieszczenie odczytów i zapisów w lokalizacjach pamięci ze względu na wydajność.</span><span class="sxs-lookup"><span data-stu-id="3d766-105">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="3d766-106">Pola, które są zadeklarowane, `volatile` nie podlegają tym optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="3d766-106">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="3d766-107">Dodanie `volatile` modyfikatora gwarantuje, że wszystkie wątki będą obserwować nietrwałe zapisy wykonywane przez każdy inny wątek w kolejności, w której zostały wykonane.</span><span class="sxs-lookup"><span data-stu-id="3d766-107">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="3d766-108">Nie istnieje gwarancja pojedynczej kolejności zapisów nietrwałych w postaci zaobserwowanej ze wszystkich wątków wykonania.</span><span class="sxs-lookup"><span data-stu-id="3d766-108">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="3d766-109">`volatile`Słowo kluczowe może być stosowane do pól tego typu:</span><span class="sxs-lookup"><span data-stu-id="3d766-109">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="3d766-110">Typy odwołań.</span><span class="sxs-lookup"><span data-stu-id="3d766-110">Reference types.</span></span>
- <span data-ttu-id="3d766-111">Typy wskaźnika (w niebezpiecznym kontekście).</span><span class="sxs-lookup"><span data-stu-id="3d766-111">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="3d766-112">Należy zauważyć, że chociaż wskaźnik może być nietrwały, obiekt, do którego wskazuje element, nie może.</span><span class="sxs-lookup"><span data-stu-id="3d766-112">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="3d766-113">Innymi słowy, nie można zadeklarować "wskaźnika do nietrwałego".</span><span class="sxs-lookup"><span data-stu-id="3d766-113">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="3d766-114">Proste typy, takie jak `sbyte` ,,,,,, `byte` ,, `short` `ushort` `int` `uint` `char` `float` i `bool` .</span><span class="sxs-lookup"><span data-stu-id="3d766-114">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="3d766-115">`enum`Typ z jednym z następujących typów podstawowych: `byte` ,,, `sbyte` , `short` `ushort` `int` lub `uint` .</span><span class="sxs-lookup"><span data-stu-id="3d766-115">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="3d766-116">Parametry typu ogólnego znane jako typy referencyjne.</span><span class="sxs-lookup"><span data-stu-id="3d766-116">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="3d766-117"><xref:System.IntPtr> i <xref:System.UIntPtr> .</span><span class="sxs-lookup"><span data-stu-id="3d766-117"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="3d766-118">Inne typy, w tym `double` i `long` , nie mogą być oznaczone `volatile` ponieważ operacje odczytu i zapisu do pól tych typów nie mogą być niepodzielne.</span><span class="sxs-lookup"><span data-stu-id="3d766-118">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="3d766-119">Aby chronić wielowątkowy dostęp do tych typów pól, użyj <xref:System.Threading.Interlocked> elementów członkowskich klasy lub Włącz ochronę dostępu przy użyciu [`lock`](lock-statement.md) instrukcji.</span><span class="sxs-lookup"><span data-stu-id="3d766-119">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="3d766-120">`volatile`Słowo kluczowe może być stosowane tylko do pól obiektu `class` lub `struct` .</span><span class="sxs-lookup"><span data-stu-id="3d766-120">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="3d766-121">Nie można zadeklarować zmiennych lokalnych `volatile` .</span><span class="sxs-lookup"><span data-stu-id="3d766-121">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="3d766-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="3d766-122">Example</span></span>

<span data-ttu-id="3d766-123">Poniższy przykład pokazuje, jak zadeklarować zmienną pola publicznego jako `volatile` .</span><span class="sxs-lookup"><span data-stu-id="3d766-123">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="3d766-124">W poniższym przykładzie pokazano, jak można utworzyć wątek pomocniczy lub proces roboczy, który będzie używany do przetwarzania równolegle z elementem wątku głównego.</span><span class="sxs-lookup"><span data-stu-id="3d766-124">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="3d766-125">Aby uzyskać więcej informacji na temat wielowątkowości, zobacz [zarządzane wątki](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="3d766-125">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="3d766-126">Po `volatile` dodaniu modyfikatora do deklaracji `_shouldStop` na miejscu, zawsze uzyskasz te same wyniki (podobnie jak w powyższym fragmencie kodu).</span><span class="sxs-lookup"><span data-stu-id="3d766-126">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="3d766-127">Jednak bez tego modyfikatora `_shouldStop` elementu członkowskiego zachowanie jest nieprzewidywalne.</span><span class="sxs-lookup"><span data-stu-id="3d766-127">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="3d766-128">`DoWork`Metoda może zoptymalizować dostęp do elementu członkowskiego, co spowoduje odczytanie starych danych.</span><span class="sxs-lookup"><span data-stu-id="3d766-128">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="3d766-129">Ze względu na charakter programowania wielowątkowego liczba nieodświeżonych odczytów jest nieprzewidywalne.</span><span class="sxs-lookup"><span data-stu-id="3d766-129">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="3d766-130">Różne uruchomienia programu będą dawać nieco inne wyniki.</span><span class="sxs-lookup"><span data-stu-id="3d766-130">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3d766-131">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="3d766-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3d766-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3d766-132">See also</span></span>

- [<span data-ttu-id="3d766-133">Specyfikacja języka C#: słowo kluczowe volatile</span><span class="sxs-lookup"><span data-stu-id="3d766-133">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="3d766-134">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="3d766-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3d766-135">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="3d766-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3d766-136">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="3d766-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3d766-137">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="3d766-137">Modifiers</span></span>](index.md)
- [<span data-ttu-id="3d766-138">lock — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3d766-138">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
