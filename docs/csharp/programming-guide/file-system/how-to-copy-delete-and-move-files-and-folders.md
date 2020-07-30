---
title: Kopiowanie, usuwanie i przenoszenie plików i folderów — Przewodnik programowania w języku C#
description: Dowiedz się, jak kopiować, usuwać i przenosić pliki i foldery przy użyciu klas File, Directory, FileInfo i DirectoryInfo.
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 208502651080f4fd614e34d1bf5b088dfb1207a6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303364"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="b393d-103">Kopiowanie, usuwanie i przenoszenie plików i folderów (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b393d-103">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="b393d-104">W poniższych przykładach pokazano, jak kopiować, przenosić i usuwać pliki i foldery w sposób synchroniczny przy użyciu <xref:System.IO.File?displayProperty=nameWithType> klas, <xref:System.IO.Directory?displayProperty=nameWithType> , <xref:System.IO.FileInfo?displayProperty=nameWithType> i <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> z <xref:System.IO?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b393d-104">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b393d-105">Te przykłady nie zapewniają paska postępu ani żadnego innego interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b393d-105">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="b393d-106">Jeśli chcesz podać standardowe okno dialogowe postępu, zobacz, [jak zapewnić postęp dla operacji na plikach](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b393d-106">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="b393d-107">Służy <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> do dostarczania zdarzeń, które umożliwią obliczenie postępu podczas działania na wielu plikach.</span><span class="sxs-lookup"><span data-stu-id="b393d-107">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="b393d-108">Innym podejściem jest użycie wywołania platformy w celu wywołania odpowiednich metod związanych z plikiem w powłoce systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="b393d-108">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="b393d-109">Aby uzyskać informacje o tym, jak wykonywać te operacje na plikach asynchronicznie, zobacz [asynchroniczne we/wy pliku](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="b393d-109">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b393d-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="b393d-110">Example</span></span>  
 <span data-ttu-id="b393d-111">Poniższy przykład pokazuje, jak kopiować pliki i katalogi.</span><span class="sxs-lookup"><span data-stu-id="b393d-111">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="b393d-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="b393d-112">Example</span></span>  
 <span data-ttu-id="b393d-113">Poniższy przykład pokazuje, jak przenieść pliki i katalogi.</span><span class="sxs-lookup"><span data-stu-id="b393d-113">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="b393d-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="b393d-114">Example</span></span>  
 <span data-ttu-id="b393d-115">Poniższy przykład pokazuje, jak usunąć pliki i katalogi.</span><span class="sxs-lookup"><span data-stu-id="b393d-115">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b393d-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b393d-116">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="b393d-117">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b393d-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b393d-118">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b393d-118">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="b393d-119">Dostarczanie okna dialogowego postępu dla operacji na plikach</span><span class="sxs-lookup"><span data-stu-id="b393d-119">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="b393d-120">We/wy plików i strumieni</span><span class="sxs-lookup"><span data-stu-id="b393d-120">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="b393d-121">Typowe zadania we/wy</span><span class="sxs-lookup"><span data-stu-id="b393d-121">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
