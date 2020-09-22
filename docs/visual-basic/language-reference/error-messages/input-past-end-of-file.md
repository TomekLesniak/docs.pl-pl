---
title: Próba zapisu poza końcem pliku
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873966"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="2ee6c-102">Próba zapisu poza końcem pliku</span><span class="sxs-lookup"><span data-stu-id="2ee6c-102">Input past end of file</span></span>

<span data-ttu-id="2ee6c-103">`Input`Instrukcja odczytuje z pliku, który jest pusty lub jeden, w którym są używane wszystkie dane, albo użyto `EOF` funkcji z plikiem otwartym do dostępu do danych binarnych.</span><span class="sxs-lookup"><span data-stu-id="2ee6c-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ee6c-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="2ee6c-104">To correct this error</span></span>  
  
1. <span data-ttu-id="2ee6c-105">Użyj `EOF` funkcji bezpośrednio przed `Input` instrukcją w celu wykrycia końca pliku.</span><span class="sxs-lookup"><span data-stu-id="2ee6c-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="2ee6c-106">Jeśli plik jest otwarty do dostępu do danych binarnych, użyj `Seek` i `Loc` .</span><span class="sxs-lookup"><span data-stu-id="2ee6c-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee6c-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2ee6c-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
