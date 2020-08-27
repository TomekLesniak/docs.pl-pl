---
title: Main () i argumenty wiersza polecenia — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat głównych () i argumentów wiersza polecenia. Metoda "Main" jest punktem wejścia w programie wykonywalnym.
ms.date: 08/02/2017
f1_keywords:
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 611b0c8818f8f800cf1cf5c0f6b2789882939b7b
ms.sourcegitcommit: 60dc0a11ebdd77f969f41891d5cca06335cda6a7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2020
ms.locfileid: "88957541"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="323cd-104">Main () i argumenty wiersza polecenia (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="323cd-104">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="323cd-105">`Main`Metoda jest punktem wejścia aplikacji języka C#.</span><span class="sxs-lookup"><span data-stu-id="323cd-105">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="323cd-106">(Biblioteki i usługi nie wymagają `Main` metody jako punktu wejścia.) Gdy aplikacja jest uruchomiona, jest to `Main` Pierwsza metoda wywoływana.</span><span class="sxs-lookup"><span data-stu-id="323cd-106">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

<span data-ttu-id="323cd-107">W programie w języku C# może istnieć tylko jeden punkt wejścia.</span><span class="sxs-lookup"><span data-stu-id="323cd-107">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="323cd-108">Jeśli masz więcej niż jedną klasę, która ma `Main` metodę, musisz skompilować program z `-main` opcją kompilatora, aby określić, która `Main` Metoda ma być używana jako punkt wejścia.</span><span class="sxs-lookup"><span data-stu-id="323cd-108">If you have more than one class that has a `Main` method, you must compile your program with the `-main` compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="323cd-109">Aby uzyskać więcej informacji, zobacz [— Main (opcje kompilatora C#)](../../language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="323cd-109">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="323cd-110">Omówienie</span><span class="sxs-lookup"><span data-stu-id="323cd-110">Overview</span></span>

- <span data-ttu-id="323cd-111">`Main`Metoda jest punktem wejścia programu wykonywalnego; jest to miejsce, w którym kontrola programu zaczyna się i skończy.</span><span class="sxs-lookup"><span data-stu-id="323cd-111">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="323cd-112">`Main` jest zadeklarowany wewnątrz klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="323cd-112">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="323cd-113">`Main` musi być [statyczna](../../language-reference/keywords/static.md) i nie musi być [publiczny](../../language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="323cd-113">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="323cd-114">(W poprzednim przykładzie otrzymuje on domyślny dostęp do [prywatnego](../../language-reference/keywords/private.md)). Otaczająca Klasa lub struktura nie musi być statyczna.</span><span class="sxs-lookup"><span data-stu-id="323cd-114">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="323cd-115">`Main` może mieć parametr `void` , `int` , lub, zaczynając od języka C# 7,1 `Task` lub `Task<int>` typu zwracanego.</span><span class="sxs-lookup"><span data-stu-id="323cd-115">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="323cd-116">Jeśli i tylko wtedy `Main` , gdy zwraca `Task` lub `Task<int>` , deklaracja `Main` może zawierać [`async`](../../language-reference/keywords/async.md) modyfikator.</span><span class="sxs-lookup"><span data-stu-id="323cd-116">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="323cd-117">Należy zauważyć, że ta metoda nie wyklucza `async void Main` metody.</span><span class="sxs-lookup"><span data-stu-id="323cd-117">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="323cd-118">`Main`Metodę można zadeklarować z `string[]` parametrem zawierającym argumenty wiersza polecenia lub bez niego.</span><span class="sxs-lookup"><span data-stu-id="323cd-118">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="323cd-119">Korzystając z programu Visual Studio do tworzenia aplikacji systemu Windows, można dodać parametr ręcznie lub użyć <xref:System.Environment.GetCommandLineArgs> metody do uzyskania [argumentów wiersza polecenia](command-line-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="323cd-119">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="323cd-120">Parametry są odczytywane jako argumenty wiersza polecenia indeksowane przez zero.</span><span class="sxs-lookup"><span data-stu-id="323cd-120">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="323cd-121">W przeciwieństwie do języka C i C++, nazwa programu nie jest traktowana jako pierwszy argument wiersza polecenia w `args` tablicy, ale jest to pierwszy element <xref:System.Environment.GetCommandLineArgs> metody.</span><span class="sxs-lookup"><span data-stu-id="323cd-121">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="323cd-122">Poniżej znajduje się lista prawidłowych `Main` podpisów:</span><span class="sxs-lookup"><span data-stu-id="323cd-122">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="323cd-123">Powyższe przykłady używają modyfikatora Public akcesor.</span><span class="sxs-lookup"><span data-stu-id="323cd-123">The preceding examples all use the public accessor modifier.</span></span> <span data-ttu-id="323cd-124">Jest to typowy, ale nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="323cd-124">That is typical, but not required.</span></span>

<span data-ttu-id="323cd-125">Dodawanie `async` i `Task` , `Task<int>` typy zwracane upraszczają kod programu, gdy aplikacje konsolowe muszą rozpoczynać pracę i `await` asynchroniczne operacje w programie `Main` .</span><span class="sxs-lookup"><span data-stu-id="323cd-125">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="323cd-126">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="323cd-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="323cd-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="323cd-127">See also</span></span>

- [<span data-ttu-id="323cd-128">Kompilacja za pomocą wiersza polecenia przy użyciu csc.exe</span><span class="sxs-lookup"><span data-stu-id="323cd-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="323cd-129">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="323cd-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="323cd-130">Metody</span><span class="sxs-lookup"><span data-stu-id="323cd-130">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="323cd-131">Wewnątrz programu C#</span><span class="sxs-lookup"><span data-stu-id="323cd-131">Inside a C# Program</span></span>](../inside-a-program/index.md)
