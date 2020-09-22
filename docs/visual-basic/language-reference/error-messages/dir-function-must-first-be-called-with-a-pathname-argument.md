---
title: Należy najpierw wywołać funkcję „Dir” z argumentem „PathName”
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1064a44f7c266b9dcce05dfddedef6bb1e919999
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874464"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="95b7d-102">Należy najpierw wywołać funkcję „Dir” z argumentem „PathName”</span><span class="sxs-lookup"><span data-stu-id="95b7d-102">'Dir' function must first be called with a 'PathName' argument</span></span>

<span data-ttu-id="95b7d-103">Początkowe wywołanie `Dir` funkcji nie zawiera `PathName` argumentu.</span><span class="sxs-lookup"><span data-stu-id="95b7d-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="95b7d-104">Pierwsze wywołanie `Dir` musi zawierać a `PathName` , ale kolejne wywołania `Dir` nie muszą zawierać parametrów do pobrania następnego elementu.</span><span class="sxs-lookup"><span data-stu-id="95b7d-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95b7d-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="95b7d-105">To correct this error</span></span>  
  
1. <span data-ttu-id="95b7d-106">Podaj `PathName` argument w wywołaniu funkcji.</span><span class="sxs-lookup"><span data-stu-id="95b7d-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b7d-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="95b7d-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
