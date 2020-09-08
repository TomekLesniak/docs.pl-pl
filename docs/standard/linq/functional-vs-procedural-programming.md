---
title: Programowanie funkcjonalne a proceduralne
description: LINQ to XML obsługuje zarówno technik konstruowania funkcjonalnego, jak i proceduralnego tworzenia aplikacji XML. Konstrukcja funkcjonalna jest podejściem deklaratywnym. Techniki proceduralne obsługują modyfikację drzew XML w pamięci.
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: a2753a31e88fd338dad61063f559431869b9e17f
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552996"
---
# <a name="functional-vs-procedural-programming-linq-to-xml"></a>Programowanie funkcjonalne a proceduralne (LINQ to XML)

Istnieją różne typy aplikacji XML:

- Niektóre aplikacje pobierają źródłowe dokumenty XML i generują nowe dokumenty XML, które znajdują się w innym kształcie niż dokumenty źródłowe.
- Niektóre aplikacje pobierają źródłowe dokumenty XML i generują dokumenty z wynikami całkowicie różnymi formularzami, takimi jak pliki tekstowe HTML lub CSV.
- Niektóre aplikacje pobierają źródłowe dokumenty XML i wstawiają rekordy do bazy danych.
- Niektóre aplikacje pobierają dane z innego źródła, takiego jak baza danych, i tworzy z niego dokumenty XML.

Nie wszystkie typy aplikacji XML, ale są to reprezentatywny zestaw typów funkcji, które programista XML musi zaimplementować.

W przypadku wszystkich typów aplikacji istnieją dwie podejścia z kontrastem, które może podjąć Deweloper:

- Funkcjonalne konstruowanie przy użyciu podejścia deklaratywnego.
- Modyfikowanie drzewa XML w pamięci przy użyciu kodu proceduralnego.

LINQ to XML obsługuje oba podejścia.

Korzystając z podejścia funkcjonalnego, należy napisać przekształcenia, które pobierają dokumenty źródłowe i generować zupełnie nowe dokumenty wynikowe z żądanym kształtem.

Podczas modyfikowania drzewa XML w miejscu należy napisać kod, który przechodzi przez węzły w drzewie XML w pamięci, wstawiając, usuwając i modyfikując węzły, w razie potrzeby.

Możesz użyć LINQ to XML z dowolnego podejścia. Używasz tych samych klas, a w niektórych przypadkach te same metody. Jednak struktura i cele obu tych metod są różne. Na przykład w różnych sytuacjach jedno lub inne podejście często ma lepszą wydajność i będzie używać więcej lub mniej pamięci. Ponadto jedno lub inne podejście będzie łatwiejsze do pisania i uzyskania bardziej możliwego do utrzymania kodu.

Aby wyświetlić dwa podejścia z kontrastem, zobacz [Modyfikowanie drzewa XML w pamięci a konstrukcja funkcjonalna](in-memory-xml-tree-modification-vs-functional-construction.md).

Aby zapoznać się z samouczkiem dotyczącym pisania transformacji funkcjonalnych, zobacz [wprowadzenie do czystych transformacji funkcjonalnych](introduction-pure-functional-transformations.md).
