---
title: 'Instrukcje: Usuwanie plików i katalogów w izolowanym magazynie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET], isolated storage
- files [.NET], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
ms.openlocfilehash: ea1d7a460a8867f069aa4b4d915e03d6948e23b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688513"
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="8b950-102">Instrukcje: Usuwanie plików i katalogów w izolowanym magazynie</span><span class="sxs-lookup"><span data-stu-id="8b950-102">How to: Delete Files and Directories in Isolated Storage</span></span>

<span data-ttu-id="8b950-103">Można usunąć katalogi i pliki w izolowanym pliku magazynu.</span><span class="sxs-lookup"><span data-stu-id="8b950-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="8b950-104">W magazynie nazwy plików i katalogów są zależne od systemu operacyjnego i są określane jako względne dla katalogu głównego wirtualnego systemu plików.</span><span class="sxs-lookup"><span data-stu-id="8b950-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="8b950-105">W systemach operacyjnych Windows nie jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="8b950-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="8b950-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>Klasa oferuje dwie metody usuwania katalogów i plików: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> i <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> .</span><span class="sxs-lookup"><span data-stu-id="8b950-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="8b950-107"><xref:System.IO.IsolatedStorage.IsolatedStorageException>Wyjątek jest zgłaszany w przypadku próby usunięcia pliku lub katalogu, który nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="8b950-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="8b950-108">Jeśli w nazwie zostanie uwzględniony symbol wieloznaczny, program <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> zgłosi <xref:System.IO.IsolatedStorage.IsolatedStorageException> wyjątek i <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> zgłosi <xref:System.ArgumentException> wyjątek.</span><span class="sxs-lookup"><span data-stu-id="8b950-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="8b950-109"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>Metoda kończy się niepowodzeniem, jeśli katalog zawiera jakiekolwiek pliki lub podkatalogi.</span><span class="sxs-lookup"><span data-stu-id="8b950-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="8b950-110">Przy użyciu <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> metod i można <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> pobrać istniejące pliki i katalogi.</span><span class="sxs-lookup"><span data-stu-id="8b950-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="8b950-111">Aby uzyskać więcej informacji o przeszukiwaniu wirtualnego systemu plików w sklepie, zobacz [How to: find Existing Files i directorys in the izolowany magazyn](how-to-find-existing-files-and-directories-in-isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="8b950-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b950-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="8b950-112">Example</span></span>  

 <span data-ttu-id="8b950-113">Poniższy przykład kodu tworzy, a następnie usuwa kilka katalogów i plików.</span><span class="sxs-lookup"><span data-stu-id="8b950-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8b950-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8b950-114">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>
- [<span data-ttu-id="8b950-115">Magazyn izolowany</span><span class="sxs-lookup"><span data-stu-id="8b950-115">Isolated Storage</span></span>](isolated-storage.md)
