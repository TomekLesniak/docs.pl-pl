---
title: Chronione składowe
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: a6f36ac4f994fdc3211cac619cc0b20f7b0335b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730958"
---
# <a name="protected-members"></a>Chronione składowe

Chronione elementy członkowskie nie zapewniają żadnych rozszerzalności, ale mogą zwiększyć możliwości rozszerzania za pomocą podklas. Mogą one służyć do udostępnienia zaawansowanych opcji dostosowania bez niepotrzebnego skomplikowania głównego interfejsu publicznego.

 Projektantom struktury należy zachować ostrożność z chronionymi elementami członkowskimi, ponieważ nazwa "Protected" może mieć fałszywe znaczenie dla zabezpieczeń. Każda osoba może poddawać podklasie niezapieczętowanej klasie i uzyskać dostęp do chronionych elementów członkowskich, dzięki czemu wszystkie takie same praktyki dotyczące kodowania, które są używane dla publicznych członków, mają zastosowanie do chronionych elementów członkowskich.

 ✔️ ROZWAŻYĆ użycie chronionych elementów członkowskich do dostosowania zaawansowanego.

 ✔️ Traktuj chronione elementy członkowskie z niezapieczętowanych klas jako publiczne na potrzeby analizy zabezpieczeń, dokumentacji i zgodności.

 Każdy może dziedziczyć z klasy i uzyskiwać dostęp do chronionych elementów członkowskich.

 *Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*

 *Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*

## <a name="see-also"></a>Zobacz także

- [Wskazówki dotyczące projektowania struktury](index.md)
- [Projektowanie pod kątem rozszerzalności](designing-for-extensibility.md)
