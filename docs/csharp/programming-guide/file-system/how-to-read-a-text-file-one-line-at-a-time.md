---
title: Jak czytać plik tekstowy jeden wiersz w przewodniku programowania w języku C#
description: Dowiedz się, jak czytać plik tekstowy jeden wiersz jednocześnie. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 93645ef78f1ceb3cc4cf1d20ac73112e86957293
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178518"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="65919-104">Jak czytać plik tekstowy po jednym wierszu (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="65919-104">How to read a text file one line at a time (C# Programming Guide)</span></span>

<span data-ttu-id="65919-105">Ten przykład odczytuje zawartość pliku tekstowego, jeden wiersz naraz, do ciągu przy użyciu `ReadLine` metody `StreamReader` klasy.</span><span class="sxs-lookup"><span data-stu-id="65919-105">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="65919-106">Każdy wiersz tekstu jest przechowywany w ciągu `line` i wyświetlany na ekranie.</span><span class="sxs-lookup"><span data-stu-id="65919-106">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65919-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="65919-107">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="65919-108">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="65919-108">Compiling the Code</span></span>  

 <span data-ttu-id="65919-109">Skopiuj kod i wklej go do `Main` metody aplikacji konsolowej.</span><span class="sxs-lookup"><span data-stu-id="65919-109">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="65919-110">Zamień `"c:\test.txt"` na rzeczywistą nazwę pliku.</span><span class="sxs-lookup"><span data-stu-id="65919-110">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="65919-111">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="65919-111">Robust Programming</span></span>  

 <span data-ttu-id="65919-112">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="65919-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="65919-113">Plik może nie istnieć.</span><span class="sxs-lookup"><span data-stu-id="65919-113">The file may not exist.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="65919-114">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="65919-114">.NET Security</span></span>  

 <span data-ttu-id="65919-115">Nie należy podejmować decyzji dotyczących zawartości pliku na podstawie rozszerzenia nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="65919-115">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="65919-116">Na przykład plik `myFile.cs` nie może być plikiem źródłowym języka C#.</span><span class="sxs-lookup"><span data-stu-id="65919-116">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65919-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65919-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="65919-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="65919-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="65919-119">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="65919-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
