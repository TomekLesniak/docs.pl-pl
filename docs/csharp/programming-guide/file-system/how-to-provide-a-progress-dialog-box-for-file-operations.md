---
title: Jak zapewnić okno dialogowe postępu dla operacji na plikach — Przewodnik programowania w języku C#
description: Dowiedz się, jak udostępnić okno dialogowe postępu dla operacji na plikach przy użyciu metody CopyFile (String, String, UIOption).
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 2ea18d924b47fc10412d37479f1b09f7eef7ad3b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301973"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="e506f-103">Jak zapewnić okno dialogowe postępu dla operacji na plikach (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e506f-103">How to provide a progress dialog box for file operations (C# Programming Guide)</span></span>
<span data-ttu-id="e506f-104">Możesz podać standardowe okno dialogowe, które pokazuje postęp operacji na plikach w systemie Windows, jeśli używasz <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> metody z <xref:Microsoft.VisualBasic?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e506f-104">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="e506f-105">Aby dodać odwołanie w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e506f-105">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="e506f-106">Na pasku menu wybierz **projekt**, **Dodaj odwołanie**.</span><span class="sxs-lookup"><span data-stu-id="e506f-106">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="e506f-107">Zostanie wyświetlone okno dialogowe **Menedżer odwołań** .</span><span class="sxs-lookup"><span data-stu-id="e506f-107">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="e506f-108">W obszarze **zestawy** wybierz pozycję **Struktura** , jeśli nie została jeszcze wybrana.</span><span class="sxs-lookup"><span data-stu-id="e506f-108">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="e506f-109">Na liście nazw zaznacz pole wyboru **Microsoft. VisualBasic** , a następnie wybierz przycisk **OK** , aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="e506f-109">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e506f-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="e506f-110">Example</span></span>  
 <span data-ttu-id="e506f-111">Poniższy kod kopiuje katalog `sourcePath` określany w katalogu, który określa `destinationPath` .</span><span class="sxs-lookup"><span data-stu-id="e506f-111">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="e506f-112">Ten kod udostępnia również standardowe okno dialogowe, które pokazuje szacowany czas pozostały do zakończenia operacji.</span><span class="sxs-lookup"><span data-stu-id="e506f-112">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e506f-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e506f-113">See also</span></span>

- [<span data-ttu-id="e506f-114">System plików i rejestr (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e506f-114">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
