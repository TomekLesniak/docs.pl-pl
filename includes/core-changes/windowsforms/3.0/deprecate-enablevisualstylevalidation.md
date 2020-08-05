---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556223"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation

`Switch.System.Windows.Forms.EnableVisualStyleValidation`Przełącznik zgodności nie jest obsługiwany w Windows Forms na platformie .NET Core lub .net 5,0 i nowszych.

#### <a name="change-description"></a>Zmień opis

W .NET Framework `Switch.System.Windows.Forms.EnableVisualStyleValidation` przełącznik zgodności zezwala aplikacji na rezygnację z walidacji stylów wizualnych dostarczonych w postaci liczbowej.

W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.EnableVisualStyleValidation` przełącznik nie jest obsługiwany.

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="recommended-action"></a>Zalecana akcja

Usuń przełącznik. Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.

#### <a name="category"></a>Kategoria

Windows Forms

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- Brak

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
