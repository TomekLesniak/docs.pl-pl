---
description: modyfikator extern — odwołanie w C#
title: modyfikator extern — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: 25eb5e6642d8b608bedcb4e9adadde4d84c2bae9
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89138972"
---
# <a name="extern-c-reference"></a><span data-ttu-id="65ed9-103">extern (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="65ed9-103">extern (C# Reference)</span></span>

<span data-ttu-id="65ed9-104">`extern`Modyfikator służy do deklarowania metody, która jest implementowana zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="65ed9-104">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="65ed9-105">Typowym zastosowaniem `extern` modyfikatora jest z `DllImport` atrybutem, jeśli używasz usług międzyoperacyjnych do wywoływania kodu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="65ed9-105">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="65ed9-106">W takim przypadku metoda musi być również zadeklarowana jako `static` , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="65ed9-106">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

<span data-ttu-id="65ed9-107">`extern`Słowo kluczowe może również definiować zewnętrzny alias zestawu, dzięki czemu można odwoływać się do różnych wersji tego samego składnika z poziomu jednego zestawu.</span><span class="sxs-lookup"><span data-stu-id="65ed9-107">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="65ed9-108">Aby uzyskać więcej informacji, zobacz [alias zewnętrzny](extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="65ed9-108">For more information, see [extern alias](extern-alias.md).</span></span>

<span data-ttu-id="65ed9-109">Jest to błąd, aby użyć [abstrakcyjny](abstract.md) i `extern` modyfikatorów, aby zmodyfikować ten sam element członkowski.</span><span class="sxs-lookup"><span data-stu-id="65ed9-109">It is an error to use the [abstract](abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="65ed9-110">Użycie `extern` modyfikatora oznacza, że metoda jest implementowana poza kodem C#, podczas gdy użycie `abstract` modyfikatora oznacza, że implementacja metody nie jest podana w klasie.</span><span class="sxs-lookup"><span data-stu-id="65ed9-110">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>

<span data-ttu-id="65ed9-111">Użycie słowa kluczowego extern podlega większym ograniczeniom w języku C# niż w języku C++.</span><span class="sxs-lookup"><span data-stu-id="65ed9-111">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="65ed9-112">Aby porównać to słowo kluczowe w języku C# z wersją w języku C++, zobacz temat „Używanie słowa kluczowego extern w celu określenia powiązania” w dokumentacji języka C++.</span><span class="sxs-lookup"><span data-stu-id="65ed9-112">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>

## <a name="example-1"></a><span data-ttu-id="65ed9-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="65ed9-113">Example 1</span></span>

<span data-ttu-id="65ed9-114">W tym przykładzie program odbiera ciąg od użytkownika i wyświetla go w oknie komunikatu.</span><span class="sxs-lookup"><span data-stu-id="65ed9-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="65ed9-115">Program używa `MessageBox` metody zaimportowanej z biblioteki User32.dll.</span><span class="sxs-lookup"><span data-stu-id="65ed9-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a><span data-ttu-id="65ed9-116">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="65ed9-116">Example 2</span></span>

<span data-ttu-id="65ed9-117">Ten przykład ilustruje program C#, który wywołuje do biblioteki C (natywnej biblioteki DLL).</span><span class="sxs-lookup"><span data-stu-id="65ed9-117">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>

1. <span data-ttu-id="65ed9-118">Utwórz następujący plik C i nadaj mu nazwę `cmdll.c` :</span><span class="sxs-lookup"><span data-stu-id="65ed9-118">Create the following C file and name it `cmdll.c`:</span></span>

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. <span data-ttu-id="65ed9-119">Otwórz okno wiersza polecenia narzędzi Visual Studio x64 (lub x32) Native Tools z katalogu instalacyjnego programu Visual Studio i skompiluj `cmdll.c` plik, wpisując **CL-LD cmdll. c** w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="65ed9-119">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl -LD cmdll.c** at the command prompt.</span></span>

3. <span data-ttu-id="65ed9-120">W tym samym katalogu Utwórz następujący plik C# i nadaj mu nazwę `cm.cs` :</span><span class="sxs-lookup"><span data-stu-id="65ed9-120">In the same directory, create the following C# file and name it `cm.cs`:</span></span>

    ```csharp
    // cm.cs
    using System;
    using System.Runtime.InteropServices;
    public class MainClass
    {
        [DllImport("Cmdll.dll")]
          public static extern int SampleMethod(int x);

        static void Main()
        {
            Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));
        }
    }
    ```

4. <span data-ttu-id="65ed9-121">Otwórz okno wiersza polecenia narzędzi Visual Studio x64 (lub x32) Native Tools z katalogu instalacyjnego programu Visual Studio i skompiluj `cm.cs` plik, wpisując:</span><span class="sxs-lookup"><span data-stu-id="65ed9-121">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>

    > <span data-ttu-id="65ed9-122">**csc cm.cs** (wiersz polecenia x64) — lub — **CSC-platform: x86 cm.cs** (dla wiersza polecenia x32)</span><span class="sxs-lookup"><span data-stu-id="65ed9-122">**csc cm.cs** (for the x64 command prompt) —or— **csc -platform:x86 cm.cs** (for the x32 command prompt)</span></span>

    <span data-ttu-id="65ed9-123">Spowoduje to utworzenie pliku wykonywalnego `cm.exe` .</span><span class="sxs-lookup"><span data-stu-id="65ed9-123">This will create the executable file `cm.exe`.</span></span>

5. <span data-ttu-id="65ed9-124">Uruchom polecenie `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="65ed9-124">Run `cm.exe`.</span></span> <span data-ttu-id="65ed9-125">`SampleMethod`Metoda przekazuje wartość 5 do pliku dll, który zwraca wartość pomnożoną przez 10.</span><span class="sxs-lookup"><span data-stu-id="65ed9-125">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="65ed9-126">Program tworzy następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="65ed9-126">The program produces the following output:</span></span>

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a><span data-ttu-id="65ed9-127">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="65ed9-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="65ed9-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65ed9-128">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="65ed9-129">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="65ed9-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="65ed9-130">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="65ed9-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="65ed9-131">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="65ed9-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="65ed9-132">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="65ed9-132">Modifiers</span></span>](index.md)
