---
title: Lokalizacja
ms.date: 03/30/2017
helpviewer_keywords:
- culture, localization
- application development [.NET], localization
- globalization [.NET], localization
- code blocks
- international applications [.NET], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 5d47d002c714ea80b6f94c810f2dca726c273134
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829833"
---
# <a name="localization"></a>Lokalizacja

Lokalizacja jest procesem tłumaczenia zasobów aplikacji w zlokalizowane wersje dla każdej kultury obsługiwanej przez aplikację. Krok lokalizacji należy przejść dopiero po ukończeniu kroku [Przegląd możliwości zlokalizowania](localizability-review.md) , aby sprawdzić, czy aplikacja globalna jest gotowa do lokalizacji.

Aplikacja, która jest gotowa do lokalizacji, jest oddzielona na dwa bloki koncepcyjne: blok zawierający wszystkie elementy interfejsu użytkownika i blok zawierający kod wykonywalny. Blok interfejsu użytkownika zawiera tylko lokalizowalnych elementów interfejsu użytkownika, takich jak ciągi, komunikaty o błędach, okna dialogowe, menu, osadzone zasoby obiektów i tak dalej dla kultury neutralnej. Blok kodu zawiera tylko kod aplikacji, który ma być używany przez wszystkie obsługiwane kultury. Środowisko uruchomieniowe języka wspólnego obsługuje model zasobów zestawu satelickiego, który oddziela kod wykonywalny aplikacji od jego zasobów. Aby uzyskać więcej informacji na temat implementowania tego modelu, zobacz [zasoby w programie .NET](../../framework/resources/index.md).

Dla każdej zlokalizowanej wersji aplikacji Dodaj nowy zestaw satelicki zawierający zlokalizowany blok interfejsu użytkownika przetłumaczony do odpowiedniego języka dla kultury docelowej. Blok kodu dla wszystkich kultur powinien pozostać taki sam. Kombinacja zlokalizowanej wersji bloku interfejsu użytkownika z blokiem kodu tworzy zlokalizowaną wersję aplikacji.

Zestaw Windows Software Development Kit (SDK) udostępnia Edytor zasobów Windows Forms (Winres.exe), który umożliwia szybkie lokalizowanie Windows Forms dla kultur docelowych. Aby uzyskać informacje dotyczące korzystania z tego narzędzia, zobacz [Winres.exe (Edytor zasobów Windows Forms)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).

## <a name="see-also"></a>Zobacz także

- [Globalizacja i lokalizacja](index.md)
- [Przegląd możliwości zlokalizowania](localizability-review.md)
- [Globalizacja](globalization.md)
- [Zasoby w aplikacjach klasycznych](../../framework/resources/index.md)
