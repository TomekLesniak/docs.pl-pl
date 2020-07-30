---
title: Wyjątki generowane przez kompilator — Przewodnik programowania w języku C#
description: Informacje o wyjątkach wygenerowanych przez kompilator. Przejrzyj listę automatycznie zgłaszanych wyjątków i ich Stanów błędów.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 1def83f72e83976ac672ec35169b4950a20ef54e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302064"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Wyjątki generowane przez kompilator (Przewodnik programowania w języku C#)

Niektóre wyjątki są generowane automatycznie przez środowisko uruchomieniowe .NET, gdy podstawowe operacje zakończą się niepowodzeniem. Te wyjątki i ich warunki błędu są wymienione w poniższej tabeli.  
  
|Wyjątek|Opis|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Klasa bazowa dla wyjątków, które występują podczas operacji arytmetycznych, takich jak <xref:System.DivideByZeroException> i <xref:System.OverflowException> .|  
|<xref:System.ArrayTypeMismatchException>|Zgłaszany, gdy tablica nie może przechowywać danego elementu, ponieważ rzeczywisty typ elementu jest niezgodny z rzeczywistym typem tablicy.|  
|<xref:System.DivideByZeroException>|Zgłaszany, gdy podejmowana jest próba dzielenia wartości całkowitej przez zero.|  
|<xref:System.IndexOutOfRangeException>|Zgłaszany, gdy podejmowana jest próba indeksowania tablicy, gdy indeks jest mniejszy od zera lub poza granicami tablicy.|  
|<xref:System.InvalidCastException>|Zgłaszany, gdy jawna konwersja z typu podstawowego do interfejsu lub typu pochodnego kończy się niepowodzeniem w czasie wykonywania.|  
|<xref:System.NullReferenceException>|Zgłaszany, gdy podejmowana jest próba odwołująca się do obiektu, którego wartość jest [równa null](../../language-reference/keywords/null.md).|  
|<xref:System.OutOfMemoryException>|Zgłaszany, gdy próba przydzielenia pamięci przy użyciu operatora [New](../../language-reference/operators/new-operator.md) zakończy się niepowodzeniem. Oznacza to wyczerpanie pamięci dostępnej dla środowiska uruchomieniowego języka wspólnego.|  
|<xref:System.OverflowException>|Zgłaszane w przypadku przepełnienia operacji arytmetycznej w `checked` kontekście.|  
|<xref:System.StackOverflowException>|Zgłaszany, gdy stos wykonywania został wyczerpany przez zbyt wiele oczekujących wywołań metod; zwykle wskazuje bardzo głęboką lub nieskończoną rekursję.|  
|<xref:System.TypeInitializationException>|Zgłaszany, gdy Konstruktor statyczny zgłasza wyjątek i nie `catch` istnieje zgodna klauzula, aby ją przechwycić.|  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Wyjątki i obsługa wyjątków](./index.md)
- [Obsługa wyjątków](./exception-handling.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
