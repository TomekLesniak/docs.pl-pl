---
title: Jak uzyskać informacje o plikach, folderach i dyskach — Przewodnik programowania w języku C#
description: Dowiedz się, jak uzyskać informacje o plikach, folderach i dyskach. Zobacz przykład kodu i dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 7cbaea4dc5381a2ebeb97ce2797ffe850488e126
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170457"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="57006-104">Jak uzyskać informacje o plikach, folderach i dyskach (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="57006-104">How to get information about files, folders, and drives  (C# Programming Guide)</span></span>

<span data-ttu-id="57006-105">W programie .NET można uzyskać dostęp do informacji o systemie plików przy użyciu następujących klas:</span><span class="sxs-lookup"><span data-stu-id="57006-105">In .NET, you can access file system information by using the following classes:</span></span>  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <span data-ttu-id="57006-106"><xref:System.IO.FileInfo>Klasy i <xref:System.IO.DirectoryInfo> reprezentują plik lub katalog i zawierają właściwości, które uwidaczniają wiele atrybutów plików, które są obsługiwane przez system plików NTFS.</span><span class="sxs-lookup"><span data-stu-id="57006-106">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="57006-107">Zawierają również metody otwierania, zamykania, przechodzenia i usuwania plików i folderów.</span><span class="sxs-lookup"><span data-stu-id="57006-107">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="57006-108">Wystąpienia tych klas można utworzyć, przekazując ciąg, który reprezentuje nazwę pliku, folderu lub dysku w konstruktorze:</span><span class="sxs-lookup"><span data-stu-id="57006-108">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="57006-109">Można również uzyskać nazwy plików, folderów lub dysków przy użyciu wywołań do <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType> , <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> i <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="57006-109">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="57006-110"><xref:System.IO.Directory?displayProperty=nameWithType>Klasy i <xref:System.IO.File?displayProperty=nameWithType> zapewniają statyczne metody pobierania informacji o katalogach i plikach.</span><span class="sxs-lookup"><span data-stu-id="57006-110">The <xref:System.IO.Directory?displayProperty=nameWithType> and <xref:System.IO.File?displayProperty=nameWithType> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57006-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="57006-111">Example</span></span>  

 <span data-ttu-id="57006-112">W poniższym przykładzie przedstawiono różne sposoby uzyskiwania dostępu do informacji o plikach i folderach.</span><span class="sxs-lookup"><span data-stu-id="57006-112">The following example shows various ways to access information about files and folders.</span></span>  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="57006-113">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="57006-113">Robust Programming</span></span>  

 <span data-ttu-id="57006-114">Podczas przetwarzania ciągów ścieżki określonych przez użytkownika należy również obsługiwać wyjątki dla następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="57006-114">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
- <span data-ttu-id="57006-115">Nazwa pliku jest źle sformułowana.</span><span class="sxs-lookup"><span data-stu-id="57006-115">The file name is malformed.</span></span> <span data-ttu-id="57006-116">Na przykład zawiera nieprawidłowe znaki lub tylko odstęp.</span><span class="sxs-lookup"><span data-stu-id="57006-116">For example, it contains invalid characters or only white space.</span></span>  
  
- <span data-ttu-id="57006-117">Nazwa pliku ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="57006-117">The file name is null.</span></span>  
  
- <span data-ttu-id="57006-118">Nazwa pliku jest dłuższa niż zdefiniowana w systemie długość maksymalna.</span><span class="sxs-lookup"><span data-stu-id="57006-118">The file name is longer than the system-defined maximum length.</span></span>  
  
- <span data-ttu-id="57006-119">Nazwa pliku zawiera dwukropek (:).</span><span class="sxs-lookup"><span data-stu-id="57006-119">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="57006-120">Jeśli aplikacja nie ma wystarczających uprawnień do odczytu określonego pliku, `Exists` Metoda zwraca `false` bez względu na to, czy ścieżka istnieje; metoda nie zgłasza wyjątku.</span><span class="sxs-lookup"><span data-stu-id="57006-120">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57006-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57006-121">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="57006-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="57006-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="57006-123">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="57006-123">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
