---
title: 'Porady: użycie bloków finally'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
ms.openlocfilehash: 8bc36ce9a755762bb5159a27f9ef5699b2992f0e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828039"
---
# <a name="how-to-use-finally-blocks"></a><span data-ttu-id="54a8e-102">Jak używać bloków finally</span><span class="sxs-lookup"><span data-stu-id="54a8e-102">How to use finally blocks</span></span>

<span data-ttu-id="54a8e-103">Gdy wystąpi wyjątek, wykonywanie zostaje zatrzymane i kontrola zostanie udzielona odpowiedniej procedurze obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="54a8e-103">When an exception occurs, execution stops and control is given to the appropriate exception handler.</span></span> <span data-ttu-id="54a8e-104">Często oznacza to, że wiersze kodu, które należy wykonać, są pomijane.</span><span class="sxs-lookup"><span data-stu-id="54a8e-104">This often means that lines of code you expect to be executed are bypassed.</span></span> <span data-ttu-id="54a8e-105">Niektóre Oczyszczanie zasobów, takie jak zamykanie pliku, należy wykonać nawet wtedy, gdy zostanie zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="54a8e-105">Some resource cleanup, such as closing a file, needs to be done even if an exception is thrown.</span></span> <span data-ttu-id="54a8e-106">W tym celu można użyć `finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="54a8e-106">To do this, you can use a `finally` block.</span></span> <span data-ttu-id="54a8e-107">`finally`Blok jest zawsze wykonywany, niezależnie od tego, czy wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="54a8e-107">A `finally` block always executes, regardless of whether an exception is thrown.</span></span>

<span data-ttu-id="54a8e-108">Poniższy przykład kodu używa `try` / `catch` bloku do przechwytywania <xref:System.ArgumentOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="54a8e-108">The following code example uses a `try`/`catch` block to catch an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="54a8e-109">`Main`Metoda tworzy dwie tablice i próbuje skopiować jeden do drugiego.</span><span class="sxs-lookup"><span data-stu-id="54a8e-109">The `Main` method creates two arrays and attempts to copy one to the other.</span></span> <span data-ttu-id="54a8e-110">Akcja generuje <xref:System.ArgumentOutOfRangeException> błąd i jest zapisywana w konsoli.</span><span class="sxs-lookup"><span data-stu-id="54a8e-110">The action generates an <xref:System.ArgumentOutOfRangeException> and the error is written to the console.</span></span> <span data-ttu-id="54a8e-111">`finally`Blok jest wykonywany niezależnie od wyniku akcji kopiowania.</span><span class="sxs-lookup"><span data-stu-id="54a8e-111">The `finally` block executes regardless of the outcome of the copy action.</span></span>

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="54a8e-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="54a8e-112">See also</span></span>

- [<span data-ttu-id="54a8e-113">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="54a8e-113">Exceptions</span></span>](index.md)
