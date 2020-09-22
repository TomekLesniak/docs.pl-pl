---
title: W elemencie „<name>” nie odnaleziono dostępnej metody „Main” z odpowiednim podpisem.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6958e778701066760aa74e3b4d566800b7527b76
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871487"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="5d28d-102">W elemencie „\<name>” nie odnaleziono dostępnej metody „Main” z odpowiednim podpisem.</span><span class="sxs-lookup"><span data-stu-id="5d28d-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>

<span data-ttu-id="5d28d-103">Aplikacje wiersza polecenia muszą mieć `Sub Main` zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="5d28d-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="5d28d-104">`Main` musi być zadeklarowany tak, jakby `Public Shared` jest zdefiniowana w klasie lub tak, jakby została `Public` zdefiniowana w module.</span><span class="sxs-lookup"><span data-stu-id="5d28d-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="5d28d-105">**Identyfikator błędu:** BC30737</span><span class="sxs-lookup"><span data-stu-id="5d28d-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d28d-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="5d28d-106">To correct this error</span></span>  
  
- <span data-ttu-id="5d28d-107">Zdefiniuj `Public Sub Main` procedurę dla projektu.</span><span class="sxs-lookup"><span data-stu-id="5d28d-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="5d28d-108">Zadeklaruj go jako `Shared` if i tylko wtedy, gdy zdefiniujesz go wewnątrz klasy.</span><span class="sxs-lookup"><span data-stu-id="5d28d-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d28d-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5d28d-109">See also</span></span>

- [<span data-ttu-id="5d28d-110">Struktura programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d28d-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="5d28d-111">Procedury</span><span class="sxs-lookup"><span data-stu-id="5d28d-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
