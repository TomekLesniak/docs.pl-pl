---
title: Operatory równości
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 85a9e81d28995229e6b47d7fe4d0b541265999f8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821349"
---
# <a name="equality-operators"></a>Operatory równości
W tej sekcji omówiono przeciążanie operatorów równości i odwołuje się do nich `operator==` `operator!=` operator równości i.

 ❌ Nie należy przeciążać jednego z operatorów równości, a nie innych.

 ✔️ Upewnij się, że <xref:System.Object.Equals%2A?displayProperty=nameWithType> Operatory równości mają dokładnie taką samą semantykę i podobną charakterystykę wydajności.

 Często oznacza to, że należy `Object.Equals` je zastąpić, gdy operatory równości są przeciążone.

 ❌ UNIKAj zgłaszania wyjątków od operatorów równości.

 Na przykład Zwróć wartość false, jeśli jeden z argumentów ma wartość null, a nie Przerzucanie `NullReferenceException` .

## <a name="equality-operators-on-value-types"></a>Operatory równości w typach wartości
 ✔️ przeciążać operatory równości dla typów wartości, jeśli równość jest istotna.

 W większości języków programowania nie istnieje domyślna implementacja `operator==` dla typów wartości.

## <a name="equality-operators-on-reference-types"></a>Operatory równości w typach referencyjnych
 ❌ UNIKAj przeciążania operatorów równości dla modyfikowalnych typów odwołań.

 Wiele języków ma wbudowane operatory równości dla typów referencyjnych. Operatory wbudowane zwykle implementują równość odwołań, a wielu deweloperów jest przeważnie, gdy domyślne zachowanie zostanie zmienione na równość wartości.

 Ten problem został skorygowany dla niezmiennego typu referencyjnego, ponieważ niezmienności znacznie trudniejsze do zauważenia różnicy między równośćmi referencyjnymi i równość wartości.

 ❌ UNIKAj przeciążania operatorów równości w typach referencyjnych, jeśli implementacja będzie znacznie wolniejsza niż równość odwołania.

 *Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*

 *Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*

## <a name="see-also"></a>Zobacz także

- [Wskazówki dotyczące projektowania struktury](index.md)
- [Wskazówki dotyczące użycia](usage-guidelines.md)
