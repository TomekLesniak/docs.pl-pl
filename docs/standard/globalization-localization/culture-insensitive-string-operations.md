---
title: Niezależne od kultury operacje na ciągach
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET], culture-insensitive string operations
- strings [.NET], culture-insensitive string operations
- localization [.NET], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
ms.openlocfilehash: 3a6085d15dbaa30144436b163a6ecb777698f4f1
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064005"
---
# <a name="culture-insensitive-string-operations"></a>Niezależne od kultury operacje na ciągach

Operacje na ciągach, w których jest uwzględniana kultura, mogą okazać się przydatne w przypadku tworzenia aplikacji, które mają wyświetlać wyniki użytkownikom na podstawie kultury. Domyślnie metody uwzględniające kulturę uzyskują kulturę do użycia z <xref:System.Globalization.CultureInfo.CurrentCulture%2A> właściwości bieżącego wątku.

Czasami Operacje na ciągach zależnych od kultury nie są pożądane. Używanie operacji, w których jest uwzględniana kultura, gdy wyniki powinny być niezależne od kultury, może spowodować, że kod aplikacji przestanie działać w przypadku kultur z niestandardowymi mapowaniami wielkości liter i regułami sortowania. Aby zapoznać się z przykładem, zobacz sekcję ["porównania ciągów, które używają bieżącej kultury"](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) w artykule [najlepsze rozwiązania dotyczące używania ciągów](../base-types/best-practices-strings.md) .

To, czy w operacjach na ciągach powinna być uwzględniana kultura, zależy od tego, jak aplikacja używa wyników. W operacjach na ciągach, które wyświetlają wyniki użytkownikowi, zazwyczaj powinna być uwzględniana kultura. Na przykład jeśli aplikacja wyświetla posortowaną listę zlokalizowanych ciągów w polu listy, aplikacja powinna wykonać sortowanie z uwzględnieniem kultury.

W wynikach operacji na ciągach, które są używane wewnętrznie, zazwyczaj nie powinna być uwzględniana kultura. Ogólnie, jeśli aplikacja wykonuje operacje na nazwach plików, formatach trwałości lub informacjach symbolicznych, które nie są wyświetlane użytkownikowi, wyniki operacji na ciągach nie powinny ulegać zmianie w zależności od kultury. Na przykład jeśli aplikacja porównuje ciąg w celu ustalenia, czy jest on rozpoznawanym tagiem XML, w porównaniu nie powinna być uwzględniana kultura. Ponadto, jeśli decyzja dotycząca zabezpieczeń opiera się na wyniku porównania ciągów lub operacji zmiany wielkości liter, operacja powinna być niezależna od kultury, aby zapewnić, że wynik nie będzie miał wpływ na wartość <xref:System.Globalization.CultureInfo.CurrentCulture%2A> .

Bez względu na to, czy tworzysz aplikację, która zawiera kod do obsługi problemów dotyczących lokalizacji i globalizacji, należy pamiętać o metodach .NET, które domyślnie pobierają dane zależne od kultury.

## <a name="see-also"></a>Zobacz też

- [Globalizacja i lokalizacja](index.md)
