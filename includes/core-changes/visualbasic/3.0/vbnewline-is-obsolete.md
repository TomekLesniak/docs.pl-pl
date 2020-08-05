---
ms.openlocfilehash: 072ed716910e2e1f1f98dbddc56d5bd097b75acc
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555916"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft. VisualBasic. Stałychs. vbNewLine jest przestarzała

<xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>Stała jest oznaczona jako [ \[ przestarzała \] ](xref:System.ObsoleteAttribute) począwszy od platformy .NET Core 3,0.

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET Core 3,0, [przestarzały](xref:System.ObsoleteAttribute) atrybut został zastosowany do <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> stałej. Użycie stałej powoduje wygenerowanie ostrzeżenia kompilatora. W .NET Framework i poprzednich wersjach programu .NET Core nie została oznaczona jako przestarzała.

Ta zmiana została wprowadzona w celu obsługi Visual Basic jako języka dla tworzenia wielu platform. <xref:Microsoft.VisualBasic.Constants.vbNewLine>Stała jest równoznaczna z `\r\n` sekwencją znaków nowego wiersza w systemie Windows. W systemach opartych na systemie UNIX znak nowego wiersza to `\n` .

#### <a name="recommended-action"></a>Zalecana akcja

Komunikat o [przestarzałym](xref:System.ObsoleteAttribute) atrybucie dla programu <xref:Microsoft.VisualBasic.Constants.vbNewLine> zawiera następujące zalecenia:

W przypadku powrotu karetki i wysuwu wiersza Użyj <xref:Microsoft.VisualBasic.Constants.vbCrLf> . W przypadku wiersza dla bieżącej platformy Użyj <xref:System.Environment.NewLine?displayProperty=nameWithType> .

#### <a name="category"></a>Kategoria

Visual Basic

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
