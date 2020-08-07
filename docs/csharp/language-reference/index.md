---
title: Dokumentacja języka C#
ms.date: 02/14/2017
f1_keywords:
- _CSharpKeyword
helpviewer_keywords:
- Visual C#, language reference
- language reference [C#]
- Programmer's Reference for C#
- C# language, reference
- reference, C# language
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
ms.openlocfilehash: bed8f430793a8d8544cf0bbb5ea765490945bfc0
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855338"
---
# <a name="c-reference"></a>Dokumentacja języka C#

Ta sekcja zawiera materiały referencyjne dotyczące słów kluczowych języka C#, operatorów, znaków specjalnych, dyrektyw preprocesora, opcji kompilatora i błędów i ostrzeżeń kompilatora.  
  
## <a name="in-this-section"></a>W tej sekcji

 [Słowa kluczowe języka C#](./keywords/index.md)  
 Zawiera łącza do informacji o słowach kluczowych i składni języka C#.  
  
 [Operatory języka C#](./operators/index.md)  
 Zawiera łącza do informacji na temat operatorów i składni języka C#.  

 [Znaki specjalne w języku C#](./tokens/index.md)  
 Zawiera łącza do informacji na temat specjalnych znaków kontekstowych w języku C# i ich użycia.  

 [Dyrektywy preprocesora języka C#](./preprocessor-directives/index.md)  
 Zawiera łącza do informacji o poleceniach kompilatora osadzania w kodzie źródłowym języka C#.  
  
 [Opcje kompilatora C#](./compiler-options/index.md)  
 Zawiera informacje o opcjach kompilatora i sposobach ich użycia.  
  
 [Błędy kompilatora C#](./compiler-messages/index.md)  
 Zawiera fragmenty kodu, które pokazują przyczynę i korekcję błędów i ostrzeżeń kompilatora C#.  
  
 [Specyfikacja języka C#](../../../_csharplang/spec/introduction.md)  
 Specyfikacja języka C# 6,0. Jest to wersja robocza propozycja języka C# 6,0. Ten dokument zostanie rafinowany przez współpracę z Komitetem standardowym języka C# w języku ECMA. Wersja 5,0 została wydana w grudniu 2017 jako standardowy dokument [ECMA-334 5](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf) .

Funkcje, które zostały zaimplementowane w wersjach C# po 6,0 są reprezentowane w propozycjach specyfikacji języka. Te dokumenty opisują różnice w specyfikacji języka w celu dodania tych nowych funkcji. Są one w wersji roboczej formularza propozycji. Te specyfikacje zostaną ulepszone i przesłane do Komitetu standardów ECMA dla formalnego przeglądu i w przyszłych wersjach standardu C#.

 [Propozycje dotyczące specyfikacji języka C# 7,0](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 W języku C# 7,0 wprowadzono wiele nowych funkcji. Obejmują one Dopasowywanie wzorców, funkcje lokalne, deklaracje zmiennych wyjściowych, wyrażenia throw, literały binarne i separatory cyfr. Ten folder zawiera specyfikacje dla każdej z tych funkcji.
  
 [Propozycje dotyczące specyfikacji języka C# 7,1](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 Dodano nowe funkcje w języku C# 7,1. Najpierw można napisać `Main` metodę zwracającą `Task` lub `Task<int>` . Pozwala to na dodanie `async` modyfikatora do `Main` . `default`Wyrażenia można użyć bez typu w lokalizacjach, w których można wywnioskować typ. Ponadto można wywnioskować nazwy elementów członkowskich krotki. Na koniec dopasowanie do wzorca może być używane z typami ogólnymi.

 [Propozycje dotyczące specyfikacji języka C# 7,2](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 W języku C# 7,2 dodano wiele małych funkcji. Argumenty można przekazać przez odwołanie tylko do odczytu za pomocą `in` słowa kluczowego. Istnieją pewne zmiany niskiego poziomu, które umożliwiają obsługę bezpieczeństwa w czasie kompilacji dla `Span` i powiązanych typów. Można użyć nazwanych argumentów, jeśli późniejsze argumenty są pozycjonowane w niektórych sytuacjach. `private protected`Modyfikator dostępu pozwala określić, że wywołania są ograniczone do typów pochodnych wdrożonych w tym samym zestawie. `?:`Operator może rozpoznać odwołanie do zmiennej. Możesz również sformatować liczby szesnastkowe i binarne przy użyciu wiodącego separatora cyfr.

 [Propozycje dotyczące specyfikacji języka C# 7,3](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7,3 to kolejna wersja punktu, która obejmuje kilka małych aktualizacji. Możesz użyć nowych ograniczeń dla parametrów typu ogólnego. Inne zmiany ułatwiają pracę z `fixed` polami, w tym za pomocą [`stackalloc`](./operators/stackalloc.md) przydziałów. Zmienne lokalne zadeklarowane za pomocą `ref` słowa kluczowego mogą zostać przypisane do nowego magazynu. Można umieścić atrybuty dla automatycznie implementowanych właściwości, które są przeznaczone dla pola zapasowego wygenerowanego przez kompilator. Zmiennych wyrażeń można używać w inicjatorach. Krotki można porównać pod kątem równości (lub nierówności). Wprowadzono również pewne ulepszenia dotyczące rozpoznawania przeciążenia.
  
 [Propozycje dotyczące specyfikacji języka C# 8,0](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md)  
 Język C# 8,0 jest dostępny z platformą .NET Core 3,0. Funkcje obejmują typy referencyjne dopuszczające wartość null, cykliczne dopasowywanie do wzorca, domyślne metody interfejsu, strumienie asynchroniczne, zakresy i indeksy, wzorzec oparty na używaniu i używaniu deklaracji, przypisywaniu łączenia zerowego i elementów członkowskich wystąpień tylko do odczytu.
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Używanie środowiska programistycznego Visual Studio dla języka C#](/visualstudio/get-started/csharp)  
 Zawiera łącza do tematów dotyczących pojęć i zadań, które opisują środowisko IDE i edytor.  
  
 [Przewodnik programowania w języku C#](../programming-guide/index.md)  
 Zawiera informacje o sposobach używania języka programowania w języku C#.
