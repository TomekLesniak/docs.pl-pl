---
title: Alias, klauzula
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866682"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="eaf01-102">Alias — Klauzula (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaf01-102">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="eaf01-103">Wskazuje, że procedura zewnętrzna ma inną nazwę w bibliotece DLL.</span><span class="sxs-lookup"><span data-stu-id="eaf01-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaf01-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="eaf01-104">Remarks</span></span>  

 <span data-ttu-id="eaf01-105">`Alias`Słowo kluczowe może być używane w tym kontekście:</span><span class="sxs-lookup"><span data-stu-id="eaf01-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="eaf01-106">Declare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="eaf01-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="eaf01-107">W poniższym przykładzie `Alias` słowo kluczowe jest używane do podania nazwy funkcji w advapi32.dll, `GetUserNameA` , która `getUserName` jest używana zamiast w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="eaf01-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="eaf01-108">Funkcja `getUserName` jest wywoływana w sub `getUser` , która wyświetla nazwę bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="eaf01-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="eaf01-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eaf01-109">See also</span></span>

- [<span data-ttu-id="eaf01-110">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="eaf01-110">Keywords</span></span>](../keywords/index.md)
