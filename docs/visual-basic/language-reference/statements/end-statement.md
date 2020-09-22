---
title: End — Instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 0c99b919b50701e93fab7caf5fb5d8b6b976d44b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865853"
---
# <a name="end-statement"></a><span data-ttu-id="c64ee-102">End — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="c64ee-102">End Statement</span></span>

<span data-ttu-id="c64ee-103">Kończy wykonywanie natychmiast.</span><span class="sxs-lookup"><span data-stu-id="c64ee-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64ee-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c64ee-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="c64ee-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c64ee-105">Remarks</span></span>  

 <span data-ttu-id="c64ee-106">Możesz umieścić `End` instrukcję w dowolnym miejscu procedury, aby wymusić, że cała aplikacja przestanie działać.</span><span class="sxs-lookup"><span data-stu-id="c64ee-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="c64ee-107">`End` zamyka wszystkie pliki otwierane za pomocą `Open` instrukcji i czyści wszystkie zmienne aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c64ee-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="c64ee-108">Aplikacja jest zamykana natychmiast, gdy nie ma żadnych innych programów przechowujących odwołania do jego obiektów i żaden z jego kodu nie jest uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="c64ee-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c64ee-109">`End`Instrukcja kończy wykonywanie kodu nieoczekiwanie i nie wywołuje `Dispose` `Finalize` metody lub ani żadnego innego kodu Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c64ee-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="c64ee-110">Odwołania do obiektów przechowywane przez inne programy są unieważnione.</span><span class="sxs-lookup"><span data-stu-id="c64ee-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="c64ee-111">Jeśli `End` instrukcja jest napotkana w `Try` bloku lub `Catch` , formant nie przechodzi do odpowiadającego `Finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="c64ee-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="c64ee-112">`Stop`Instrukcja zawiesza wykonywanie, ale w przeciwieństwie do `End` siebie nie zamyka żadnych plików ani nie czyści żadnych zmiennych, chyba że występuje w skompilowanym pliku wykonywalnym (. exe).</span><span class="sxs-lookup"><span data-stu-id="c64ee-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="c64ee-113">Ponieważ `End` kończy działanie aplikacji bez udziału w zasobach, które mogą być otwarte, należy spróbować oczyścić się nieprzerwanie przed użyciem.</span><span class="sxs-lookup"><span data-stu-id="c64ee-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="c64ee-114">Na przykład jeśli aplikacja ma otwarte jakiekolwiek formularze, należy je zamknąć przed przekroczeniem przez formant `End` .</span><span class="sxs-lookup"><span data-stu-id="c64ee-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="c64ee-115">Należy używać `End` oszczędnie i tylko wtedy, gdy trzeba natychmiast zatrzymać.</span><span class="sxs-lookup"><span data-stu-id="c64ee-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="c64ee-116">Normalne metody kończenia procedury (instrukcja[Return](return-statement.md) i [Exit](exit-statement.md)) nie tylko zamykają procedurę, ale również powodują, że kod wywołujący może czyścić się nieprzerwanie.</span><span class="sxs-lookup"><span data-stu-id="c64ee-116">The normal ways to terminate a procedure ([Return Statement](return-statement.md) and [Exit Statement](exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="c64ee-117">Aplikacja konsolowa, na przykład, może po prostu wykonać `Return` `Main` procedurę.</span><span class="sxs-lookup"><span data-stu-id="c64ee-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c64ee-118">`End`Instrukcja wywołuje <xref:System.Environment.Exit%2A> metodę <xref:System.Environment> klasy w <xref:System> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c64ee-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="c64ee-119"><xref:System.Environment.Exit%2A> wymaga `UnmanagedCode` uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="c64ee-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="c64ee-120">Jeśli tego nie zrobisz, wystąpi <xref:System.Security.SecurityException> błąd.</span><span class="sxs-lookup"><span data-stu-id="c64ee-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="c64ee-121">Po wykonaniu dodatkowego słowa kluczowego [ \<keyword> instrukcja End](end-keyword-statement.md) wyznacza koniec definicji odpowiedniej procedury lub bloku.</span><span class="sxs-lookup"><span data-stu-id="c64ee-121">When followed by an additional keyword, [End \<keyword> Statement](end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="c64ee-122">Na przykład `End Function` kończy definicję `Function` procedury.</span><span class="sxs-lookup"><span data-stu-id="c64ee-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c64ee-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="c64ee-123">Example</span></span>  

 <span data-ttu-id="c64ee-124">Poniższy przykład używa instrukcji, `End` Aby przerwać wykonywanie kodu, jeśli użytkownik zażąda.</span><span class="sxs-lookup"><span data-stu-id="c64ee-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="c64ee-125">Uwagi dla deweloperów inteligentnych urządzeń</span><span class="sxs-lookup"><span data-stu-id="c64ee-125">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="c64ee-126">Ta instrukcja nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="c64ee-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64ee-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c64ee-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="c64ee-128">Stop, instrukcja</span><span class="sxs-lookup"><span data-stu-id="c64ee-128">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="c64ee-129">End — \<keyword> instrukcja</span><span class="sxs-lookup"><span data-stu-id="c64ee-129">End \<keyword> Statement</span></span>](end-keyword-statement.md)
