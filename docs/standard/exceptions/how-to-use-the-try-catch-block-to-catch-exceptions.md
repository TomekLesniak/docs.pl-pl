---
title: 'Instrukcje: Używanie bloku try/catch do przechwytywania wyjątków'
description: Użyj bloku try, aby zawierać instrukcje, które mogą zgłosić lub zgłosić wyjątek. Umieszczaj instrukcje w celu obsługi wyjątków w jednym lub większej liczbie bloków catch.
ms.date: 02/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: cfe5b2b304cdb9efe7f0d91059fe1c279b4fa2dd
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828013"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="ca439-104">Jak przechwytywać wyjątki przy użyciu bloku try/catch</span><span class="sxs-lookup"><span data-stu-id="ca439-104">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="ca439-105">Umieść wszystkie instrukcje Code, które mogą podnieść lub zgłosić wyjątek w `try` bloku, oraz umieścić instrukcje używane do obsługi wyjątku lub wyjątków w co najmniej jednym bloku `catch` pod `try` blokiem.</span><span class="sxs-lookup"><span data-stu-id="ca439-105">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="ca439-106">Każdy `catch` blok zawiera typ wyjątku i może zawierać dodatkowe instrukcje, które są konieczne do obsłużenia tego typu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="ca439-106">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="ca439-107">W poniższym przykładzie <xref:System.IO.StreamReader> otwiera plik o nazwie *data.txt* i pobiera wiersz z pliku.</span><span class="sxs-lookup"><span data-stu-id="ca439-107">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="ca439-108">Ponieważ kod może zgłosić którykolwiek z trzech wyjątków, zostanie umieszczony w `try` bloku.</span><span class="sxs-lookup"><span data-stu-id="ca439-108">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="ca439-109">Trzy `catch` bloki przechwytują wyjątki i obsługują je, wyświetlając wyniki w konsoli.</span><span class="sxs-lookup"><span data-stu-id="ca439-109">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="ca439-110">Aparat plików wykonywalnych języka wspólnego (CLR) przechwytuje wyjątki, które nie są obsługiwane przez `catch` bloki.</span><span class="sxs-lookup"><span data-stu-id="ca439-110">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="ca439-111">W przypadku przechwyconego wyjątku przez środowisko CLR może wystąpić jeden z następujących wyników w zależności od konfiguracji środowiska CLR:</span><span class="sxs-lookup"><span data-stu-id="ca439-111">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="ca439-112">Zostanie wyświetlone okno dialogowe **debugowanie** .</span><span class="sxs-lookup"><span data-stu-id="ca439-112">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="ca439-113">Program przerywa wykonywanie i pojawia się okno dialogowe z informacjami o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="ca439-113">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="ca439-114">Wystąpił błąd podczas drukowania [strumienia wyjściowego błędu standardowego](xref:System.Console.Error).</span><span class="sxs-lookup"><span data-stu-id="ca439-114">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="ca439-115">Większość kodu może zgłosić wyjątek, a niektóre wyjątki, takie jak <xref:System.OutOfMemoryException> , mogą być zgłaszane przez samo środowisko CLR w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="ca439-115">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="ca439-116">Chociaż aplikacje nie są wymagane do obsługi tych wyjątków, należy pamiętać o możliwości, gdy pisanie bibliotek ma być używane przez inne osoby.</span><span class="sxs-lookup"><span data-stu-id="ca439-116">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="ca439-117">Aby uzyskać sugestie dotyczące ustawiania kodu w `try` bloku, zobacz [najlepsze rozwiązania dotyczące wyjątków](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="ca439-117">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca439-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ca439-118">See also</span></span>

- [<span data-ttu-id="ca439-119">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="ca439-119">Exceptions</span></span>](index.md)
- [<span data-ttu-id="ca439-120">Obsługa błędów we/wy w programie .NET</span><span class="sxs-lookup"><span data-stu-id="ca439-120">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
