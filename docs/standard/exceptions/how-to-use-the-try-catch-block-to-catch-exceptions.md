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
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Jak przechwytywać wyjątki przy użyciu bloku try/catch

Umieść wszystkie instrukcje Code, które mogą podnieść lub zgłosić wyjątek w `try` bloku, oraz umieścić instrukcje używane do obsługi wyjątku lub wyjątków w co najmniej jednym bloku `catch` pod `try` blokiem. Każdy `catch` blok zawiera typ wyjątku i może zawierać dodatkowe instrukcje, które są konieczne do obsłużenia tego typu wyjątku.

W poniższym przykładzie <xref:System.IO.StreamReader> otwiera plik o nazwie *data.txt* i pobiera wiersz z pliku. Ponieważ kod może zgłosić którykolwiek z trzech wyjątków, zostanie umieszczony w `try` bloku. Trzy `catch` bloki przechwytują wyjątki i obsługują je, wyświetlając wyniki w konsoli.

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

Aparat plików wykonywalnych języka wspólnego (CLR) przechwytuje wyjątki, które nie są obsługiwane przez `catch` bloki. W przypadku przechwyconego wyjątku przez środowisko CLR może wystąpić jeden z następujących wyników w zależności od konfiguracji środowiska CLR:

- Zostanie wyświetlone okno dialogowe **debugowanie** .
- Program przerywa wykonywanie i pojawia się okno dialogowe z informacjami o wyjątku.
- Wystąpił błąd podczas drukowania [strumienia wyjściowego błędu standardowego](xref:System.Console.Error).

> [!NOTE]
> Większość kodu może zgłosić wyjątek, a niektóre wyjątki, takie jak <xref:System.OutOfMemoryException> , mogą być zgłaszane przez samo środowisko CLR w dowolnym momencie. Chociaż aplikacje nie są wymagane do obsługi tych wyjątków, należy pamiętać o możliwości, gdy pisanie bibliotek ma być używane przez inne osoby. Aby uzyskać sugestie dotyczące ustawiania kodu w `try` bloku, zobacz [najlepsze rozwiązania dotyczące wyjątków](best-practices-for-exceptions.md).

## <a name="see-also"></a>Zobacz także

- [Wyjątki](index.md)
- [Obsługa błędów we/wy w programie .NET](../io/handling-io-errors.md)
