---
title: Plik jest już otwarty
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874186"
---
# <a name="file-already-open"></a><span data-ttu-id="7a6d5-102">Plik jest już otwarty</span><span class="sxs-lookup"><span data-stu-id="7a6d5-102">File already open</span></span>

<span data-ttu-id="7a6d5-103">Czasami plik musi być zamknięty, aby `FileOpen` można było wykonać inną lub inną operację.</span><span class="sxs-lookup"><span data-stu-id="7a6d5-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="7a6d5-104">Wśród możliwych przyczyn tego błędu są:</span><span class="sxs-lookup"><span data-stu-id="7a6d5-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="7a6d5-105">Operacja trybu sekwencyjnego wyjścia `FileOpen` została wykonana dla pliku, który jest już otwarty</span><span class="sxs-lookup"><span data-stu-id="7a6d5-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="7a6d5-106">Instrukcja odwołuje się do otwartego pliku.</span><span class="sxs-lookup"><span data-stu-id="7a6d5-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a6d5-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="7a6d5-107">To correct this error</span></span>  
  
1. <span data-ttu-id="7a6d5-108">Zamknij plik przed wykonaniem instrukcji.</span><span class="sxs-lookup"><span data-stu-id="7a6d5-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a6d5-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7a6d5-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
