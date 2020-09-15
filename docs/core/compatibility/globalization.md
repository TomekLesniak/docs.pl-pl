---
title: Zmiany dotyczące podziału globalizacji
description: Wyświetla listę istotnych zmian w globalizacji w programie .NET Core.
ms.date: 04/07/2020
ms.openlocfilehash: 93990d89204df1b2d7498e1d748378fae05598c3
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065071"
---
# <a name="globalization-breaking-changes"></a>Zmiany dotyczące podziału globalizacji

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | :-: |
| [Zmieniono kategorię Unicode dla niektórych znaków łacińskich 1](#unicode-category-changed-for-some-latin-1-characters) | 5,0 |
| [Interfejsy API globalizacji korzystają z bibliotek ICU w systemie Windows](#globalization-apis-use-icu-libraries-on-windows) | 5,0 |
| [StringInfo i TextElementEnumerator są teraz zgodne UAX29](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | 5,0 |
| [Ustawienia regionalne "C" są mapowane na niezmienne ustawienia regionalne](#c-locale-maps-to-the-invariant-locale) | 3,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [unicode-categories-for-latin1-chars](../../../includes/core-changes/globalization/5.0/unicode-categories-for-latin1-chars.md)]

***

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
