---
title: Asynchroniczne przepływy pracy
description: 'Dowiedz się więcej o pomocy technicznej w języku programowania F # na potrzeby wykonywania obliczeń asynchronicznie, które są wykonywane bez blokowania wykonywania innych czynności.'
ms.date: 08/15/2020
ms.openlocfilehash: 14146cc8a643f31831475075212cc06da5f8d6ff
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720273"
---
# <a name="asynchronous-workflows"></a>Asynchroniczne przepływy pracy

W tym artykule opisano obsługę obliczeń asynchronicznie w języku F #, czyli bez blokowania wykonywania innych czynności. Na przykład asynchroniczne obliczenia mogą służyć do pisania aplikacji, które mają interfejsów użytkownika, które pozostają w stanie odpowiadać użytkownikom, ponieważ aplikacja wykonuje inne czynności.

## <a name="syntax"></a>Składnia

```fsharp
async { expression }
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni, obliczenia reprezentowane przez program `expression` są skonfigurowane do uruchamiania asynchronicznego, czyli bez blokowania bieżącego wątku obliczeniowego, gdy asynchroniczne operacje uśpienia, we/wy i inne operacje asynchroniczne są wykonywane. Obliczenia asynchroniczne są często uruchamiane w wątku w tle, podczas gdy wykonywanie jest kontynuowane w bieżącym wątku. Typ wyrażenia to `Async<'T>` , gdzie `'T` jest typem zwracanym przez wyrażenie, gdy `return` słowo kluczowe jest używane. Kod w tym wyrażeniu jest określany jako *blok asynchroniczny*lub *blok asynchroniczny*.

Istnieją różne sposoby programowania asynchronicznego, a [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html) Klasa zawiera metody, które obsługują kilka scenariuszy. Ogólna Metoda polega na tworzeniu `Async` obiektów, które reprezentują obliczenia lub obliczenia, które mają być uruchamiane asynchronicznie, a następnie uruchomić te obliczenia przy użyciu jednej z funkcji wyzwalających. Różne funkcje wyzwalające zapewniają różne sposoby uruchamiania obliczeń asynchronicznych, a których jeden jest używany, zależy od tego, czy chcesz użyć bieżącego wątku, wątku tła czy obiektu zadania .NET Framework, oraz czy istnieją funkcje kontynuacji, które powinny być uruchamiane po zakończeniu obliczeń. Na przykład, aby rozpocząć obliczanie asynchroniczne w bieżącym wątku, można użyć [`Async.StartImmediate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#StartImmediate) . Po uruchomieniu asynchronicznego obliczenia z wątku interfejsu użytkownika nie należy blokować głównej pętli zdarzeń, która przetwarza akcje użytkownika, takie jak naciśnięcia klawiszy i aktywność myszy, dzięki czemu aplikacja będzie odpowiadać.

## <a name="asynchronous-binding-by-using-let"></a>Powiązanie asynchroniczne za pomocą let!

W asynchronicznym przepływie pracy niektóre wyrażenia i operacje są synchroniczne, a niektóre są dłuższymi obliczeniami, które zostały zaprojektowane tak, aby zwracały wynik asynchronicznie. Gdy wywoływana jest metoda asynchronicznie, zamiast zwykłego `let` powiązania należy użyć polecenia `let!` . Efektem `let!` jest włączenie wykonywania w celu kontynuowania na innych obliczeniach lub wątkach w miarę wykonywania obliczeń. Po prawej stronie `let!` powiązania zostanie przywrócona pozostała część asynchronicznego przepływu pracy.

Poniższy kod przedstawia różnicę między `let` i `let!` . Wiersz kodu, który używa `let` po prostu tworzy asynchroniczne obliczenie jako obiekt, który można uruchomić później za pomocą, na przykład `Async.StartImmediate` lub [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) . Wiersz kodu, który używa `let!` uruchamiania obliczeń, a następnie wątek jest zawieszony do momentu, w którym wykonanie tego punktu będzie kontynuowane.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Oprócz programu `let!` można używać `use!` do wykonywania powiązań asynchronicznych. Różnica między `let!` i `use!` jest taka sama jak różnica między `let` i `use` . W przypadku `use!` , obiekt jest usuwany po zamknięciu bieżącego zakresu. Należy pamiętać, że w bieżącej wersji języka F #, nie `use!` zezwala na zainicjowanie wartości null, mimo że jest to możliwe `use` .

## <a name="asynchronous-primitives"></a>Elementy pierwotne asynchroniczne

Metoda, która wykonuje pojedyncze zadanie asynchroniczne i zwraca wynik, jest nazywana *asynchroniczną pierwotną*i jest przeznaczona specjalnie do użycia z `let!` . Niektóre elementy pierwotne asynchroniczne są zdefiniowane w bibliotece podstawowej języka F #. Dwie takie metody aplikacji sieci Web są zdefiniowane w module [`FSharp.Control.WebExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html) : [`WebRequest.AsyncGetResponse`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncGetResponse) i [`WebClient.AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) . Oba elementy pierwotne pobierają dane ze strony sieci Web przy użyciu adresu URL. `AsyncGetResponse` tworzy `System.Net.WebResponse` obiekt i `AsyncDownloadString` tworzy ciąg, który reprezentuje kod HTML dla strony sieci Web.

W module uwzględniono kilka elementów podstawowych operacji we/wy [`FSharp.Control.CommonExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html) . Te metody rozszerzające `System.IO.Stream` klasy to [`Stream.AsyncRead`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncRead) i [`Stream.AsyncWrite`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncWrite) .

Możesz również pisać własne elementy pierwotne, definiując funkcję, której Pełna treść jest zawarta w bloku asynchronicznym.

Aby użyć metod asynchronicznych w .NET Framework, które są przeznaczone dla innych modeli asynchronicznych z modelem programowania asynchronicznego F #, należy utworzyć funkcję, która zwraca obiekt F # `Async` . Biblioteka języka F # zawiera funkcje, które ułatwiają to łatwe.

Przykładem użycia asynchronicznych przepływów pracy jest tutaj dołączony. Istnieje wiele innych w dokumentacji metod [klasy asynchronicznej](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html).

Ten przykład pokazuje, jak używać asynchronicznych przepływów pracy do wykonywania obliczeń równolegle.

W poniższym przykładzie kodu funkcja `fetchAsync` Pobiera tekst HTML zwrócony przez żądanie sieci Web. `fetchAsync`Funkcja zawiera asynchroniczny blok kodu. Gdy wiązanie jest tworzone w wyniku asynchronicznej klasy pierwotnej, w tym przypadku [`AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) `let!` jest używane zamiast `let` .

Funkcja służy [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) do wykonywania operacji asynchronicznej i czeka na jej wynik. Przykładowo można wykonać wiele operacji asynchronicznych równolegle przy użyciu [`Async.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#Parallel) funkcji razem z `Async.RunSynchronously` funkcją. `Async.Parallel`Funkcja przyjmuje listę `Async` obiektów, konfiguruje kod dla każdego `Async` obiektu zadania do uruchomienia równoległego i zwraca `Async` obiekt, który reprezentuje obliczenia równoległe. Podobnie jak w przypadku jednej operacji, należy wywołać, `Async.RunSynchronously` Aby rozpocząć wykonywanie.

`runAll`Funkcja uruchamia trzy asynchroniczne przepływy pracy równolegle i czeka na zakończenie wszystkich operacji.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Wyrażenia obliczeń](computation-expressions.md)
- [Control. Async — Klasa](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html)
