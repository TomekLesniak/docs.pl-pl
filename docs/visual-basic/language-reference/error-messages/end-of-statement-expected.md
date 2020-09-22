---
title: Oczekiwano końca instrukcji
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 9141400afc651629df381e0a655e2d7b9da2e45d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874420"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="7c8dd-102">Oczekiwano końca instrukcji</span><span class="sxs-lookup"><span data-stu-id="7c8dd-102">End of statement expected</span></span>

<span data-ttu-id="7c8dd-103">Instrukcja ma składnię kompletną, ale dodatkowy element programistyczny następuje po elemencie, który uzupełnia instrukcję.</span><span class="sxs-lookup"><span data-stu-id="7c8dd-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="7c8dd-104">Terminator wiersza jest wymagany na końcu każdej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="7c8dd-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="7c8dd-105">Terminator wiersza dzieli znaki pliku źródłowego Visual Basic na wiersze.</span><span class="sxs-lookup"><span data-stu-id="7c8dd-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="7c8dd-106">Przykłady terminatorów wiersza to znak powrotu karetki Unicode (&HD), znak wysuwu wiersza Unicode (&HA) i znak powrotu karetki Unicode, po którym następuje znak wysuwu wiersza w formacie Unicode.</span><span class="sxs-lookup"><span data-stu-id="7c8dd-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="7c8dd-107">Aby uzyskać więcej informacji na temat terminatorów wierszy, zobacz [Specyfikacja języka Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="7c8dd-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="7c8dd-108">**Identyfikator błędu:** BC30205</span><span class="sxs-lookup"><span data-stu-id="7c8dd-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7c8dd-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="7c8dd-109">To correct this error</span></span>
  
1. <span data-ttu-id="7c8dd-110">Sprawdź, czy dwie różne instrukcje zostały przypadkowo umieszczone w tym samym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7c8dd-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="7c8dd-111">Wstaw terminator wiersza po elemencie, który uzupełnia instrukcję.</span><span class="sxs-lookup"><span data-stu-id="7c8dd-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7c8dd-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7c8dd-112">See also</span></span>

- [<span data-ttu-id="7c8dd-113">Instrukcje: Przerywanie i łączenie instrukcji w kodzie</span><span class="sxs-lookup"><span data-stu-id="7c8dd-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="7c8dd-114">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="7c8dd-114">Statements</span></span>](../../programming-guide/language-features/statements.md)
