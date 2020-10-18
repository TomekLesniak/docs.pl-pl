---
title: Plik jest już otwarty
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162755"
---
# <a name="file-already-open"></a><span data-ttu-id="96502-102">Plik jest już otwarty</span><span class="sxs-lookup"><span data-stu-id="96502-102">File already open</span></span>

<span data-ttu-id="96502-103">Czasami plik musi być zamknięty, aby `FileOpen` można było wykonać inną lub inną operację.</span><span class="sxs-lookup"><span data-stu-id="96502-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="96502-104">Wśród możliwych przyczyn tego błędu są:</span><span class="sxs-lookup"><span data-stu-id="96502-104">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="96502-105">Operacja trybu sekwencyjnego wyjścia `FileOpen` została wykonana dla pliku, który jest już otwarty</span><span class="sxs-lookup"><span data-stu-id="96502-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="96502-106">Instrukcja odwołuje się do otwartego pliku.</span><span class="sxs-lookup"><span data-stu-id="96502-106">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="96502-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="96502-107">To correct this error</span></span>

- <span data-ttu-id="96502-108">Zamknij plik przed wykonaniem instrukcji.</span><span class="sxs-lookup"><span data-stu-id="96502-108">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="96502-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96502-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
