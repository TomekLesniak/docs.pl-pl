---
ms.openlocfilehash: 56127309c5f5993ffc2e2faedd1f481e8131e094
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400638"
---
### <a name="textformatflagsmodifystring-is-obsolete"></a>TextFormatFlags. ModifyString jest przestarzała

<xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>Pole jest przestarzałe, jako ostrzeżenie i może zostać usunięte w przyszłej wersji platformy .NET.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> pole wyliczenia nie jest oznaczone jako przestarzałe. W programie .NET 5,0 i jego nowszych wersjach jest oznaczona jako ostrzeżenie jako zaprzestarzała. To pole może zostać usunięte w przyszłej wersji platformy .NET.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Przekazywanie ciągu do <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> przy użyciu <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> polecenia modyfikuje ciąg w niektórych sytuacjach. To zachowanie przerywa niezmienności obietnicę i może prowadzić do krytycznego uszkodzenia stanu środowiska uruchomieniowego platformy .NET.

#### <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0 RC1

#### <a name="recommended-action"></a>Zalecana akcja

Aktualizowanie dowolnego kodu, który jest zależny od <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> .

#### <a name="category"></a>Kategoria

Windows Forms

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

-->
