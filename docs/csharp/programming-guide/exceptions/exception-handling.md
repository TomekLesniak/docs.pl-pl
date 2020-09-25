---
title: Obsługa wyjątków — Przewodnik programowania w języku C#
description: Dowiedz się więcej o obsłudze wyjątków. Zobacz przykłady instrukcji try-catch, try-finally i try-catch-finally.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: 8f7dc027396e327f08a591ced6bd6df176a17606
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178687"
---
# <a name="exception-handling-c-programming-guide"></a>Obsługa wyjątków (Przewodnik programowania w języku C#)

Programiści języka C# używają bloku [try](../../language-reference/keywords/try-catch.md) do partycjonowania kodu, który może mieć wpływ na wyjątek. Skojarzone bloki [catch](../../language-reference/keywords/try-catch.md) są używane do obsługi wszelkich wyjątków z wynikiem. Blok [finally](../../language-reference/keywords/try-finally.md) zawiera kod, który jest uruchamiany niezależnie od tego, czy wyjątek jest zgłaszany w `try` bloku, na przykład zwalniając zasoby, które są przydzieloną w `try` bloku. `try`Blok wymaga jednego lub większej liczby skojarzonych `catch` bloków albo bloku lub `finally` obu tych wartości.  
  
 W poniższych przykładach pokazano `try-catch` instrukcję, `try-finally` instrukcję i `try-catch-finally` instrukcję.  
  
 [!code-csharp[csProgGuideExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#6)]  
  
 [!code-csharp[csProgGuideExceptions#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#7)]  
  
 [!code-csharp[csProgGuideExceptions#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#8)]  
  
 `try`Blok bez `catch` `finally` bloku lub powoduje błąd kompilatora.  
  
## <a name="catch-blocks"></a>Bloki catch  

 `catch`Blok może określać typ wyjątku do przechwycenia. Specyfikacja typu jest nazywana *filtrem wyjątków*. Typ wyjątku powinien pochodzić od <xref:System.Exception> . Ogólnie rzecz biorąc nie określaj <xref:System.Exception> jako filtr wyjątku, chyba że wiesz, jak obsługiwać wszystkie wyjątki, które mogą zostać zgłoszone w `try` bloku, lub dodaliśmy instrukcję [throw](../../language-reference/keywords/throw.md) na końcu `catch` bloku.  
  
 Wiele `catch` bloków z różnymi filtrami wyjątków może być łańcucha ze sobą. `catch`Bloki są oceniane z góry do dołu w kodzie, ale tylko jeden `catch` blok jest wykonywany dla każdego zgłoszonego wyjątku. `catch`Zostanie wykonany pierwszy blok, który określa typ dokładny lub Klasa bazowa zgłoszonego wyjątku. Jeśli żaden `catch` blok nie określa zgodnego filtru wyjątków, `catch` blok, który nie ma filtra jest zaznaczony, jeśli jeden jest obecny w instrukcji. Ważne jest, aby umieścić `catch` bloki z najbardziej szczegółowymi (najbardziej pochodnymi) typami wyjątków.  
  
 Wyjątki należy przechwytywać, gdy są spełnione następujące warunki:  
  
- Warto zapoznać się z informacją o tym, dlaczego wyjątek może być zgłaszany, i można zaimplementować konkretne odzyskiwanie, na przykład monitowanie użytkownika o wprowadzenie nowej nazwy pliku podczas przechwytywania <xref:System.IO.FileNotFoundException> obiektu.  
  
- Można utworzyć i zgłosić nowy, bardziej szczegółowy wyjątek.  
  
     [!code-csharp[csProgGuideExceptions#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#9)]  
  
- Chcesz częściowo obsłużyć wyjątek przed przekazaniem go do dodatkowej obsługi. W poniższym przykładzie `catch` blok jest używany do dodawania wpisu do dziennika błędów przed ponownym wygenerowaniem wyjątku.  
  
     [!code-csharp[csProgGuideExceptions#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#10)]  
  
## <a name="finally-blocks"></a>Bloki finally  

 `finally`Blok umożliwia czyszczenie akcji wykonywanych w `try` bloku. Jeśli jest obecny, `finally` blok jest wykonywany jako ostatni, po `try` bloku i dowolnym dopasowanym `catch` bloku. `finally`Blok jest zawsze uruchamiany, niezależnie od tego, czy wystąpił wyjątek, czy `catch` znaleziono blok pasujący do typu wyjątku.  
  
 `finally`Blok może służyć do zwolnienia zasobów, takich jak strumienie plików, połączenia z bazą danych i uchwyty grafiki, bez oczekiwania na zakończenie działania modułu zbierającego elementy bezużyteczne w środowisku uruchomieniowym. Aby uzyskać więcej informacji, zobacz [używanie instrukcji using](../../language-reference/keywords/using-statement.md) .  
  
 W poniższym przykładzie `finally` blok jest używany do zamykania pliku, który jest otwarty w `try` bloku. Przed zamknięciem pliku należy zauważyć, że jego stan jest sprawdzany. Jeśli `try` blok nie może otworzyć pliku, dojście do pliku nadal ma wartość, `null` a `finally` blok nie próbuje go zamknąć. Alternatywnie, jeśli plik zostanie pomyślnie otwarty w `try` bloku, `finally` blok zamknie otwarty plik.  
  
 [!code-csharp[csProgGuideExceptions#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#11)]  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [wyjątki](~/_csharplang/spec/exceptions.md) i [Instrukcje try](~/_csharplang/spec/statements.md#the-try-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../../language-reference/index.md)
- [Przewodnik programowania w języku C#](../index.md)
- [Wyjątki i obsługa wyjątków](./index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [using, instrukcja](../../language-reference/keywords/using-statement.md)
