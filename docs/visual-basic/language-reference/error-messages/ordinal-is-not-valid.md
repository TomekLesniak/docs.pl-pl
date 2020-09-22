---
title: Liczba porządkowa nie jest prawidłowa
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871388"
---
# <a name="ordinal-is-not-valid"></a>Liczba porządkowa nie jest prawidłowa

Wywołanie do biblioteki dołączanej dynamicznie (DLL) wskazane do użycia numeru zamiast nazwy procedury, przy użyciu `#num` składni. Ten błąd ma następujące możliwe przyczyny:  
  
- Próba konwersji `#num` wyrażenia na numer porządkowy nie powiodła się.  
  
- `#num`Określony nie określa żadnej funkcji w bibliotece DLL.  
  
- Biblioteka typów ma nieprawidłową deklarację powodującą użycie wewnętrznego nieprawidłowego numeru porządkowego.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że wyrażenie reprezentuje poprawną liczbę, lub wywołaj procedurę według nazwy.  
  
2. Upewnij się `#num` , że w bibliotece DLL zidentyfikowano prawidłową funkcję.  
  
3. Wyodrębnij wywołanie procedury powodujące problem, dodając komentarz do kodu. Napisz `Declare` instrukcję do procedury i Zgłoś problem dla dostawcy biblioteki typów.  
  
## <a name="see-also"></a>Zobacz też

- [Declare — Instrukcja](../statements/declare-statement.md)
