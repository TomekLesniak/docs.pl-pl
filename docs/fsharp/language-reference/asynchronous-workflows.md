---
title: Asynchroniczne przepływy pracy
description: 'Dowiedz się więcej o pomocy technicznej w języku programowania F # na potrzeby wykonywania obliczeń asynchronicznie, które są wykonywane bez blokowania wykonywania innych czynności.'
ms.date: 05/16/2016
ms.openlocfilehash: 3bc24639b329401a8f944488e974f0739d4680df
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855468"
---
# <a name="asynchronous-workflows"></a>Asynchroniczne przepływy pracy

W tym artykule opisano obsługę obliczeń asynchronicznie w języku F #, czyli bez blokowania wykonywania innych czynności. Na przykład asynchroniczne obliczenia mogą służyć do pisania aplikacji, które mają interfejsów użytkownika, które pozostają w stanie odpowiadać użytkownikom, ponieważ aplikacja wykonuje inne czynności.

> [!NOTE]
> Dokumentacja interfejsu API docs.microsoft.com dla języka F # nie została ukończona. Jeśli wystąpią jakieś przerwane linki, należy odwołać się do [dokumentacji podstawowej biblioteki języka F #](https://fsharp.github.io/fsharp-core-docs/) .

## <a name="syntax"></a>Składnia

```fsharp
async { expression }
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni, obliczenia reprezentowane przez program `expression` są skonfigurowane do uruchamiania asynchronicznego, czyli bez blokowania bieżącego wątku obliczeniowego, gdy asynchroniczne operacje uśpienia, we/wy i inne operacje asynchroniczne są wykonywane. Obliczenia asynchroniczne są często uruchamiane w wątku w tle, podczas gdy wykonywanie jest kontynuowane w bieżącym wątku. Typ wyrażenia to `Async<'T>` , gdzie `'T` jest typem zwracanym przez wyrażenie, gdy `return` słowo kluczowe jest używane. Kod w tym wyrażeniu jest określany jako *blok asynchroniczny*lub *blok asynchroniczny*.

Istnieją różne sposoby programowania asynchronicznego, a [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) Klasa zawiera metody, które obsługują kilka scenariuszy. Ogólna Metoda polega na tworzeniu `Async` obiektów, które reprezentują obliczenia lub obliczenia, które mają być uruchamiane asynchronicznie, a następnie uruchomić te obliczenia przy użyciu jednej z funkcji wyzwalających. Różne funkcje wyzwalające zapewniają różne sposoby uruchamiania obliczeń asynchronicznych, a których jeden jest używany, zależy od tego, czy chcesz użyć bieżącego wątku, wątku tła czy obiektu zadania .NET Framework, oraz czy istnieją funkcje kontynuacji, które powinny być uruchamiane po zakończeniu obliczeń. Na przykład, aby rozpocząć obliczanie asynchroniczne w bieżącym wątku, można użyć [`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3) . Po uruchomieniu asynchronicznego obliczenia z wątku interfejsu użytkownika nie należy blokować głównej pętli zdarzeń, która przetwarza akcje użytkownika, takie jak naciśnięcia klawiszy i aktywność myszy, dzięki czemu aplikacja będzie odpowiadać.

## <a name="asynchronous-binding-by-using-let"></a>Powiązanie asynchroniczne za pomocą let!

W asynchronicznym przepływie pracy niektóre wyrażenia i operacje są synchroniczne, a niektóre są dłuższymi obliczeniami, które zostały zaprojektowane tak, aby zwracały wynik asynchronicznie. Gdy wywoływana jest metoda asynchronicznie, zamiast zwykłego `let` powiązania należy użyć polecenia `let!` . Efektem `let!` jest włączenie wykonywania w celu kontynuowania na innych obliczeniach lub wątkach w miarę wykonywania obliczeń. Po prawej stronie `let!` powiązania zostanie przywrócona pozostała część asynchronicznego przepływu pracy.

Poniższy kod przedstawia różnicę między `let` i `let!` . Wiersz kodu, który używa `let` po prostu tworzy asynchroniczne obliczenie jako obiekt, który można uruchomić później za pomocą, na przykład `Async.StartImmediate` lub [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) . Wiersz kodu, który używa `let!` uruchamiania obliczeń, a następnie wątek jest zawieszony do momentu, w którym wykonanie tego punktu będzie kontynuowane.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Oprócz programu `let!` można używać `use!` do wykonywania powiązań asynchronicznych. Różnica między `let!` i `use!` jest taka sama jak różnica między `let` i `use` . W przypadku `use!` , obiekt jest usuwany po zamknięciu bieżącego zakresu. Należy pamiętać, że w bieżącej wersji języka F #, nie `use!` zezwala na zainicjowanie wartości null, mimo że jest to możliwe `use` .

## <a name="asynchronous-primitives"></a>Elementy pierwotne asynchroniczne

Metoda, która wykonuje pojedyncze zadanie asynchroniczne i zwraca wynik, jest nazywana *asynchroniczną pierwotną*i jest przeznaczona specjalnie do użycia z `let!` . Niektóre elementy pierwotne asynchroniczne są zdefiniowane w bibliotece podstawowej języka F #. Dwie takie metody aplikacji sieci Web są zdefiniowane w module [`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003) : [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) i [`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a) . Oba elementy pierwotne pobierają dane ze strony sieci Web przy użyciu adresu URL. `AsyncGetResponse`tworzy `System.Net.WebResponse` obiekt i `AsyncDownloadString` tworzy ciąg, który reprezentuje kod HTML dla strony sieci Web.

W module uwzględniono kilka elementów podstawowych operacji we/wy [`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) . Te metody rozszerzające `System.IO.Stream` klasy to [`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) i [`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618) .

Możesz również pisać własne elementy pierwotne, definiując funkcję, której Pełna treść jest zawarta w bloku asynchronicznym.

Aby użyć metod asynchronicznych w .NET Framework, które są przeznaczone dla innych modeli asynchronicznych z modelem programowania asynchronicznego F #, należy utworzyć funkcję, która zwraca obiekt F # `Async` . Biblioteka języka F # zawiera funkcje, które ułatwiają to łatwe.

Przykładem użycia asynchronicznych przepływów pracy jest tutaj dołączony. Istnieje wiele innych w dokumentacji metod [klasy asynchronicznej](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

Ten przykład pokazuje, jak używać asynchronicznych przepływów pracy do wykonywania obliczeń równolegle.

W poniższym przykładzie kodu funkcja `fetchAsync` Pobiera tekst HTML zwrócony przez żądanie sieci Web. `fetchAsync`Funkcja zawiera asynchroniczny blok kodu. W przypadku tworzenia powiązania z wynikiem asynchronicznej klasy pierwotnej, w tym przypadku [`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a) , niech! jest używany zamiast let.

Funkcja służy [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) do wykonywania operacji asynchronicznej i czeka na jej wynik. Przykładowo można wykonać wiele operacji asynchronicznych równolegle przy użyciu [`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) funkcji razem z `Async.RunSynchronously` funkcją. `Async.Parallel`Funkcja przyjmuje listę `Async` obiektów, konfiguruje kod dla każdego `Async` obiektu zadania do uruchomienia równoległego i zwraca `Async` obiekt, który reprezentuje obliczenia równoległe. Podobnie jak w przypadku jednej operacji, należy wywołać, `Async.RunSynchronously` Aby rozpocząć wykonywanie.

`runAll`Funkcja uruchamia trzy asynchroniczne przepływy pracy równolegle i czeka na zakończenie wszystkich operacji.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka F #](index.md)
- [Wyrażenia obliczeń](computation-expressions.md)
- [Control. Async — Klasa](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
