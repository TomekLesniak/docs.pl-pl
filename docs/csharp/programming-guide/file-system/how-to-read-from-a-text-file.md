---
title: Jak czytać z pliku tekstowego — Przewodnik programowania w języku C#
description: Dowiedz się, jak czytać z pliku tekstowego przy użyciu metod statycznych z klasy File. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 64ac99ec0a72ba7df120f6732edccf160a351738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201840"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="69ac3-104">Jak czytać z pliku tekstowego (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="69ac3-104">How to read from a text file (C# Programming Guide)</span></span>

<span data-ttu-id="69ac3-105">Ten przykład odczytuje zawartość pliku tekstowego przy użyciu metod statycznych <xref:System.IO.File.ReadAllText%2A> i <xref:System.IO.File.ReadAllLines%2A> z <xref:System.IO.File?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="69ac3-105">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="69ac3-106">Aby zapoznać się z przykładem korzystającym z <xref:System.IO.StreamReader> programu, zobacz [jak czytać plik tekstowy po jednym wierszu naraz](./how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="69ac3-106">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69ac3-107">Pliki, które są używane w tym przykładzie, są tworzone w temacie [jak zapisywać w pliku tekstowym](./how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="69ac3-107">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="69ac3-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="69ac3-108">Example</span></span>  

 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69ac3-109">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="69ac3-109">Compiling the Code</span></span>  

 <span data-ttu-id="69ac3-110">Skopiuj kod i wklej go do aplikacji konsolowej C#.</span><span class="sxs-lookup"><span data-stu-id="69ac3-110">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="69ac3-111">Jeśli nie używasz plików tekstowych z [metody zapisywania do pliku tekstowego](./how-to-write-to-a-text-file.md), Zamień argument na `ReadAllText` i `ReadAllLines` z odpowiednią ścieżką i nazwą pliku na komputerze.</span><span class="sxs-lookup"><span data-stu-id="69ac3-111">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="69ac3-112">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="69ac3-112">Robust Programming</span></span>  

 <span data-ttu-id="69ac3-113">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="69ac3-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="69ac3-114">Plik nie istnieje lub nie istnieje w określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="69ac3-114">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="69ac3-115">Sprawdź ścieżkę i pisownię nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="69ac3-115">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="69ac3-116">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="69ac3-116">.NET Security</span></span>  

 <span data-ttu-id="69ac3-117">Nie należy polegać na nazwie pliku, aby ustalić zawartość pliku.</span><span class="sxs-lookup"><span data-stu-id="69ac3-117">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="69ac3-118">Na przykład plik `myFile.cs` może nie być plikiem źródłowym języka C#.</span><span class="sxs-lookup"><span data-stu-id="69ac3-118">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ac3-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="69ac3-119">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="69ac3-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="69ac3-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="69ac3-121">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="69ac3-121">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
