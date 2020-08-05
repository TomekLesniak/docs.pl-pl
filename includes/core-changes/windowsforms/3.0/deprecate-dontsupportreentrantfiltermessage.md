---
ms.openlocfilehash: 95aa243a5790d4201c7871e617dbe4ccafb7c1a1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556247"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage

`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.6.1, nie jest obsługiwany w Windows Forms na platformie .NET Core i .net 5,0 i nowszych.

#### <a name="change-description"></a>Zmień opis

Począwszy od .NET Framework 4.6.1, `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` przełącznik zgodności rozwiązuje możliwe wyjątki, <xref:System.IndexOutOfRangeException> gdy <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> komunikat jest wywoływany z implementacją niestandardową <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> . Aby uzyskać więcej informacji, zobacz Rozwiązywanie [problemów z niestandardowymi implementacjami IMessageFilter. PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` przełącznik nie jest obsługiwany.

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="recommended-action"></a>Zalecana akcja

Usuń przełącznik. Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.

#### <a name="category"></a>Kategoria

Windows Forms

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
