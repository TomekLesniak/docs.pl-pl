---
description: '#Dokumentacja wiersza — C#'
title: '#Dokumentacja wiersza — C#'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: e2a5ecb6c29184123b8a88ae1b12caf24ec7296a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137997"
---
# <a name="line-c-reference"></a><span data-ttu-id="95a52-103">#line (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="95a52-103">#line (C# Reference)</span></span>

<span data-ttu-id="95a52-104">`#line` umożliwia zmodyfikowanie numeracji linii kompilatora oraz (opcjonalnie) dane wyjściowe nazwy pliku dla błędów i ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="95a52-104">`#line` lets you modify the compiler's line numbering and (optionally) the file name output for errors and warnings.</span></span>

<span data-ttu-id="95a52-105">Poniższy przykład pokazuje, jak zgłosić dwa ostrzeżenia skojarzone z numerami wierszy.</span><span class="sxs-lookup"><span data-stu-id="95a52-105">The following example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="95a52-106">`#line 200`Dyrektywa wymusza numer następnego wiersza do 200 (mimo że wartość domyślna to #6), a do następnej `#line` dyrektywy nazwa pliku będzie raportowana jako "Specjalna".</span><span class="sxs-lookup"><span data-stu-id="95a52-106">The `#line 200` directive forces the next line's number to be 200 (although the default is #6), and until the next `#line` directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="95a52-107">`#line default`Dyrektywa zwraca numery wierszy do domyślnej numeracji, która zlicza wiersze, które zostały zmienione przez poprzednią dyrektywę.</span><span class="sxs-lookup"><span data-stu-id="95a52-107">The `#line default` directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

<span data-ttu-id="95a52-108">Kompilacja generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="95a52-108">Compilation produces the following output:</span></span>

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a><span data-ttu-id="95a52-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="95a52-109">Remarks</span></span>

<span data-ttu-id="95a52-110">`#line`Dyrektywa może być używana w zautomatyzowanym, pośrednim kroku w procesie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="95a52-110">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="95a52-111">Na przykład jeśli linie zostały usunięte z oryginalnego pliku kodu źródłowego, ale nadal chcesz, aby kompilator generował dane wyjściowe na podstawie pierwotnej numeracji wierszy w pliku, możesz usunąć linie, a następnie symulować pierwotne numery wierszy przy użyciu `#line` .</span><span class="sxs-lookup"><span data-stu-id="95a52-111">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>

<span data-ttu-id="95a52-112">`#line hidden`Dyrektywa powoduje ukrycie kolejnych wierszy w debugerze, takich jak w przypadku kroków wykonywanych przez dewelopera w kodzie, wszelkich wierszy między `#line hidden` a i Następna `#line` dyrektywa (przy założeniu, że nie jest to inna `#line hidden` dyrektywa) zostanie przełączona.</span><span class="sxs-lookup"><span data-stu-id="95a52-112">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="95a52-113">Tej opcji można również użyć, aby zezwolić ASP.NET na rozróżnienie między zdefiniowanym przez użytkownika i generowanym przez maszyną kodem.</span><span class="sxs-lookup"><span data-stu-id="95a52-113">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="95a52-114">Chociaż ASP.NET jest głównym odbiorcą tej funkcji, prawdopodobnie będzie ona używać większej liczby generatorów źródeł.</span><span class="sxs-lookup"><span data-stu-id="95a52-114">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>

<span data-ttu-id="95a52-115">`#line hidden`Dyrektywa nie ma wpływu na nazwy plików lub numery wierszy w raportowaniu błędów.</span><span class="sxs-lookup"><span data-stu-id="95a52-115">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="95a52-116">Oznacza to, że jeśli w ukrytym bloku wystąpi błąd, kompilator zgłosi bieżącą nazwę pliku i numer wiersza błędu.</span><span class="sxs-lookup"><span data-stu-id="95a52-116">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>

<span data-ttu-id="95a52-117">`#line filename`Dyrektywa określa nazwę pliku, który ma być wyświetlany w danych wyjściowych kompilatora.</span><span class="sxs-lookup"><span data-stu-id="95a52-117">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="95a52-118">Domyślnie używana jest rzeczywista nazwa pliku kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="95a52-118">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="95a52-119">Nazwa pliku musi być ujęta w znaki podwójnego cudzysłowu ("") i musi być poprzedzona numerem wiersza.</span><span class="sxs-lookup"><span data-stu-id="95a52-119">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>

<span data-ttu-id="95a52-120">Plik kodu źródłowego może zawierać dowolną liczbę `#line` dyrektyw.</span><span class="sxs-lookup"><span data-stu-id="95a52-120">A source code file can have any number of `#line` directives.</span></span>

## <a name="example-1"></a><span data-ttu-id="95a52-121">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="95a52-121">Example 1</span></span>

<span data-ttu-id="95a52-122">Poniższy przykład pokazuje, jak debuger ignoruje ukryte wiersze w kodzie.</span><span class="sxs-lookup"><span data-stu-id="95a52-122">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="95a52-123">Po uruchomieniu przykładu zostanie wyświetlonych trzy wiersze tekstu.</span><span class="sxs-lookup"><span data-stu-id="95a52-123">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="95a52-124">Jeśli jednak ustawisz punkt przerwania, jak pokazano w przykładzie i naciśniesz klawisz F10, aby przejść przez kod, zobaczysz, że debuger ignoruje ukrytą linię.</span><span class="sxs-lookup"><span data-stu-id="95a52-124">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="95a52-125">Zwróć również uwagę, że nawet jeśli ustawisz punkt przerwania w wierszu ukrytym, debuger nadal go zignoruje.</span><span class="sxs-lookup"><span data-stu-id="95a52-125">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="95a52-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="95a52-126">See also</span></span>

- [<span data-ttu-id="95a52-127">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="95a52-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="95a52-128">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="95a52-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="95a52-129">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="95a52-129">C# Preprocessor Directives</span></span>](./index.md)
