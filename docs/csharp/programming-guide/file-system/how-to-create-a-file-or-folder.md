---
title: Jak utworzyć plik lub folder — Przewodnik programowania w języku C#
description: Dowiedz się, jak utworzyć plik lub folder programowo. Można utworzyć folder, podfolder, plik w podfolderze i zapisać dane w tym pliku.
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: f5641dc765b1a2d62adb76babe3f111730d4550b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302688"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="d0cb5-104">Jak utworzyć plik lub folder (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="d0cb5-104">How to create a file or folder (C# Programming Guide)</span></span>
<span data-ttu-id="d0cb5-105">Można programowo utworzyć folder na komputerze, utworzyć podfolder, utworzyć plik w podfolderze i zapisać dane do pliku.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-105">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0cb5-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="d0cb5-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 <span data-ttu-id="d0cb5-107">Jeśli folder już istnieje, <xref:System.IO.Directory.CreateDirectory%2A> nie robi nic i żaden wyjątek nie jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-107">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="d0cb5-108">Jednak <xref:System.IO.File.Create%2A?displayProperty=nameWithType> zastępuje istniejący plik nowym plikiem.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-108">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="d0cb5-109">W przykładzie używa się `if` - `else` instrukcji, aby zapobiec zastąpieniu istniejącego pliku.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-109">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="d0cb5-110">Wprowadzając następujące zmiany w przykładzie, można określić różne wyniki w zależności od tego, czy plik o określonej nazwie już istnieje.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-110">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="d0cb5-111">Jeśli taki plik nie istnieje, kod tworzy jeden.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-111">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="d0cb5-112">Jeśli taki plik istnieje, kod dołącza dane do tego pliku.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-112">If such a file exists, the code appends data to that file.</span></span>  
  
- <span data-ttu-id="d0cb5-113">Określ nielosową nazwę pliku.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-113">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- <span data-ttu-id="d0cb5-114">Zastąp instrukcję instrukcją `if` - `else` `using` w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-114">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="d0cb5-115">Uruchom przykład kilka razy, aby sprawdzić, czy dane są dodawane do pliku za każdym razem.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-115">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="d0cb5-116">Aby uzyskać więcej `FileMode` wartości, które można wypróbować, zobacz <xref:System.IO.FileMode> .</span><span class="sxs-lookup"><span data-stu-id="d0cb5-116">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="d0cb5-117">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="d0cb5-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d0cb5-118">Nazwa folderu jest źle sformułowana.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-118">The folder name is malformed.</span></span> <span data-ttu-id="d0cb5-119">Na przykład zawiera niedozwolone znaki lub jest tylko białym znakiem ( <xref:System.ArgumentException> Klasa).</span><span class="sxs-lookup"><span data-stu-id="d0cb5-119">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="d0cb5-120">Użyj <xref:System.IO.Path> klasy, aby utworzyć prawidłowe nazwy ścieżek.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-120">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
- <span data-ttu-id="d0cb5-121">Folder nadrzędny folderu, który ma zostać utworzony, jest tylko do odczytu ( <xref:System.IO.IOException> Klasa).</span><span class="sxs-lookup"><span data-stu-id="d0cb5-121">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="d0cb5-122">Nazwa folderu to `null` ( <xref:System.ArgumentNullException> Klasa).</span><span class="sxs-lookup"><span data-stu-id="d0cb5-122">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="d0cb5-123">Nazwa folderu jest za długa ( <xref:System.IO.PathTooLongException> Klasa).</span><span class="sxs-lookup"><span data-stu-id="d0cb5-123">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="d0cb5-124">Nazwa folderu jest tylko dwukropek, ":" ( <xref:System.IO.PathTooLongException> Klasa).</span><span class="sxs-lookup"><span data-stu-id="d0cb5-124">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="d0cb5-125">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d0cb5-125">.NET Security</span></span>  
 <span data-ttu-id="d0cb5-126">Wystąpienie <xref:System.Security.SecurityException> klasy może być zgłaszane w sytuacjach częściowej relacji zaufania.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-126">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="d0cb5-127">Jeśli nie masz uprawnień do utworzenia folderu, przykład zgłosi wystąpienie <xref:System.UnauthorizedAccessException> klasy.</span><span class="sxs-lookup"><span data-stu-id="d0cb5-127">If you don't have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0cb5-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d0cb5-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="d0cb5-129">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="d0cb5-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d0cb5-130">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="d0cb5-130">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
