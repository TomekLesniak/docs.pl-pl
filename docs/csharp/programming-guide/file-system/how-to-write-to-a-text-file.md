---
title: Jak pisać do pliku tekstowego — Przewodnik programowania w języku C#
description: Dowiedz się, jak napisać plik tekstowy przy użyciu języka C#. Zobacz kilka przykładów kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: 4108163121d56268b810121ca3ae2b2c1338aeab
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301648"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="b25ff-104">Jak pisać do pliku tekstowego (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b25ff-104">How to write to a text file (C# Programming Guide)</span></span>
<span data-ttu-id="b25ff-105">W poniższych przykładach pokazano różne sposoby zapisywania tekstu w pliku.</span><span class="sxs-lookup"><span data-stu-id="b25ff-105">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="b25ff-106">Pierwsze dwa przykłady używają statycznych metod dogodnych na <xref:System.IO.File?displayProperty=nameWithType> klasie, aby napisać każdy element dowolnego `IEnumerable<string>` i ciągu do pliku tekstowego.</span><span class="sxs-lookup"><span data-stu-id="b25ff-106">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="b25ff-107">Przykład 3 pokazuje, jak dodać tekst do pliku, gdy trzeba przetwarzać każdy wiersz indywidualnie podczas zapisu w pliku.</span><span class="sxs-lookup"><span data-stu-id="b25ff-107">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="b25ff-108">Przykłady 1-3 Zastąp całą istniejącą zawartość pliku, ale przykład 4 pokazuje, jak dołączyć tekst do istniejącego pliku.</span><span class="sxs-lookup"><span data-stu-id="b25ff-108">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="b25ff-109">Te przykłady umożliwiają zapisanie literałów ciągu do plików.</span><span class="sxs-lookup"><span data-stu-id="b25ff-109">These examples all write string literals to files.</span></span> <span data-ttu-id="b25ff-110">Jeśli chcesz sformatować tekst zapisany w pliku, użyj <xref:System.String.Format%2A> metody [interpolacji ciągu](../../language-reference/tokens/interpolated.md) języka C#.</span><span class="sxs-lookup"><span data-stu-id="b25ff-110">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b25ff-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="b25ff-111">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b25ff-112">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="b25ff-112">Robust Programming</span></span>  
 <span data-ttu-id="b25ff-113">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="b25ff-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="b25ff-114">Plik istnieje i jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="b25ff-114">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="b25ff-115">Nazwa ścieżki może być za długa.</span><span class="sxs-lookup"><span data-stu-id="b25ff-115">The path name may be too long.</span></span>  
  
- <span data-ttu-id="b25ff-116">Dysk może być zapełniony.</span><span class="sxs-lookup"><span data-stu-id="b25ff-116">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25ff-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b25ff-117">See also</span></span>

- [<span data-ttu-id="b25ff-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b25ff-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b25ff-119">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b25ff-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="b25ff-120">Przykład: zapisywanie kolekcji w magazynie aplikacji</span><span class="sxs-lookup"><span data-stu-id="b25ff-120">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
