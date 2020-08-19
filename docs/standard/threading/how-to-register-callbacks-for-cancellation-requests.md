---
title: Rejestrowanie wywołań zwrotnych żądań anulowania
ms.date: 08/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: faa8dada5779f6eaee7a60e6210ec604f5fb4680
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608451"
---
# <a name="register-callbacks-for-cancellation-requests"></a>Rejestrowanie wywołań zwrotnych żądań anulowania

Dowiedz się, jak zarejestrować delegata, który zostanie wywołany, gdy <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Właściwość zostanie prawdziwa. Wartość jest zmieniana z false na true, gdy następuje wywołanie do <xref:System.Threading.CancellationTokenSource.Cancel%2A> obiektu, który utworzył token. Ta technika służy do anulowania operacji asynchronicznych, które nie obsługują natywnie ujednoliconych struktur anulowania oraz dla metod odblokowywania, które mogą oczekiwać na zakończenie operacji asynchronicznej.

> [!NOTE]
> Po włączeniu "Tylko mój kod" program Visual Studio będzie przerywał pracę w wierszu, który zgłosi wyjątek i wyświetli komunikat o błędzie "wyjątek nie jest obsługiwany przez kod użytkownika". Ten błąd jest niegroźny. Możesz nacisnąć klawisz <kbd>F5</kbd> , aby kontynuować z niego i zobaczyć zachowanie obsługi wyjątków, które przedstawiono w poniższych przykładach. Aby zapobiec utracie przez program Visual Studio pierwszego błędu, po prostu usuń zaznaczenie pola wyboru "Tylko mój kod" w obszarze **Narzędzia, opcje, debugowanie, ogólne**.

## <a name="example"></a>Przykład

W poniższym przykładzie <xref:System.Net.WebClient.CancelAsync%2A> Metoda jest zarejestrowana jako metoda do wywołania w przypadku żądania anulowania za pomocą tokenu anulowania.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

Jeśli po zarejestrowaniu wywołania zwrotnego zostało już zgłoszone żądanie anulowania, wywołanie zwrotne jest nadal gwarantowane. W tym konkretnym przypadku <xref:System.Net.WebClient.CancelAsync%2A> Metoda nie będzie niczego robić, jeśli żadna operacja asynchroniczna nie jest w toku, więc zawsze jest bezpieczna do wywołania metody.

## <a name="see-also"></a>Zobacz też

- [Anulowanie w zarządzanych wątkach](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
