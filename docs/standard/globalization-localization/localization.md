---
title: Localization
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: e92184f48b2d2255138da5b2a6e7e2977a95e2e3
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93062961"
---
# <a name="localization"></a>Localization

Lokalizacja jest procesem tłumaczenia zasobów aplikacji w zlokalizowane wersje dla każdej kultury obsługiwanej przez aplikację. Krok lokalizacji należy przejść dopiero po ukończeniu kroku [Przegląd możliwości zlokalizowania](localizability-review.md) , aby sprawdzić, czy aplikacja globalna jest gotowa do lokalizacji.

Aplikacja, która jest gotowa do lokalizacji, jest oddzielona na dwa bloki koncepcyjne: blok zawierający wszystkie elementy interfejsu użytkownika i blok zawierający kod wykonywalny. Blok interfejsu użytkownika zawiera tylko lokalizowalnych elementów interfejsu użytkownika, takich jak ciągi, komunikaty o błędach, okna dialogowe, menu, osadzone zasoby obiektów i tak dalej dla kultury neutralnej. Blok kodu zawiera tylko kod aplikacji, który ma być używany przez wszystkie obsługiwane kultury. Środowisko uruchomieniowe języka wspólnego obsługuje model zasobów zestawu satelickiego, który oddziela kod wykonywalny aplikacji od jego zasobów. Aby uzyskać więcej informacji na temat implementowania tego modelu, zobacz [zasoby w programie .NET](../../framework/resources/index.md).

Dla każdej zlokalizowanej wersji aplikacji Dodaj nowy zestaw satelicki zawierający zlokalizowany blok interfejsu użytkownika przetłumaczony do odpowiedniego języka dla kultury docelowej. Blok kodu dla wszystkich kultur powinien pozostać taki sam. Kombinacja zlokalizowanej wersji bloku interfejsu użytkownika z blokiem kodu tworzy zlokalizowaną wersję aplikacji.

Zestaw Windows Software Development Kit (SDK) udostępnia Edytor zasobów Windows Forms (Winres.exe), który umożliwia szybkie lokalizowanie Windows Forms dla kultur docelowych. Aby uzyskać informacje dotyczące korzystania z tego narzędzia, zobacz [Winres.exe (Edytor zasobów Windows Forms)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).

## <a name="see-also"></a>Zobacz też

- [Globalizacja i lokalizacja](index.md)
- [Przegląd możliwości zlokalizowania](localizability-review.md)
- [Globalizacja](globalization.md)
- [Zasoby w aplikacjach klasycznych](../../framework/resources/index.md)
