---
title: Typ źródłowy <typename> wyliczenia jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 42c2398945b97d68161af6fb3c3b69909f4aaf39
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161520"
---
# <a name="bc40032-underlying-type-typename-of-enum-is-not-cls-compliant"></a>BC40032: typ podstawowy \<typename> wyliczenia jest niezgodny ze specyfikacją CLS

Typ danych określony dla tego wyliczenia nie jest częścią [niezależności od języka i składników Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS). Nie jest to błąd w składniku, ponieważ .NET Framework i Visual Basic obsługują ten typ danych. Jednak inny składnik zapisany w kodzie zgodnym ze specyfikacją CLS może nie obsługiwać tego typu danych. Taki składnik może nie być w stanie pomyślnie korzystać z składnika.

 Następujące Visual Basic typy danych nie są zgodne ze specyfikacją CLS:

- [SByte, typ danych](../data-types/sbyte-data-type.md)

- [UInteger, typ danych](../data-types/uinteger-data-type.md)

- [ULong, typ danych](../data-types/ulong-data-type.md)

- [UShort, typ danych](../data-types/ushort-data-type.md)

 Domyślnie ten komunikat jest ostrzeżeniem. Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC40032

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli składnik obsługuje tylko inne składniki .NET Framework lub nie ma interfejsu z innymi składnikami, nie trzeba zmieniać żadnych elementów.

- Jeśli korzystasz z składnika, który nie został zapisany dla .NET Framework, możesz określić, poprzez odbicie lub z dokumentacji, czy obsługuje ten typ danych. W przeciwnym razie nie trzeba zmieniać żadnych elementów.

- W przypadku współdziałania ze składnikiem, który nie obsługuje tego typu danych, należy zamienić go na najbliższy typ zgodny ze specyfikacją CLS. Na przykład, zamiast `UInteger` można użyć, `Integer` Jeśli nie potrzebujesz zakresu wartości powyżej 2 147 483 647. Jeśli potrzebujesz rozszerzonego zakresu, możesz zamienić `UInteger` na `Long` .

- Jeśli masz połączenie z obiektami automatyzacji lub COM, pamiętaj, że niektóre typy mają różne szerokości danych niż w .NET Framework. Na przykład `uint` często jest 16 bitów w innych środowiskach. Jeśli przekazujesz argument 16-bitowy do takiego składnika, zadeklaruj go jako `UShort` zamiast `UInteger` w kodzie zarządzanym Visual Basic.

## <a name="see-also"></a>Zobacz też

- [Odbicie (Visual Basic)](../../programming-guide/concepts/reflection.md)
- [Odbicie](../../../framework/reflection-and-codedom/reflection.md)
