---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606794"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttributee eksporty jako ObsoleteAttribute i DeprecatedAttribute w scenariuszach WinMD

#### <a name="details"></a>Szczegóły

Podczas tworzenia biblioteki metadanych systemu Windows (plik. winmd) ten <xref:System.ObsoleteAttribute?displayProperty=fullName> atrybut jest eksportowany zarówno jako, jak <xref:System.ObsoleteAttribute?displayProperty=fullName> i [Windows. Foundation. DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute).

#### <a name="suggestion"></a>Sugestia

Ponowna kompilacja istniejącego kodu źródłowego korzystającego z <xref:System.ObsoleteAttribute?displayProperty=fullName> atrybutu może generować ostrzeżenia podczas korzystania z tego kodu z C++/CX lub JavaScript. nie zaleca się stosowania programów <xref:System.ObsoleteAttribute?displayProperty=fullName> i [Windows. Foundation. DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) do kodu w zarządzanych zestawach. może to spowodować wyświetlenie ostrzeżeń dotyczących kompilacji.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Edge        |
| Wersja | 4.5.1       |
| Typ    | Przekierowanie |
