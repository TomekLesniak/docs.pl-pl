---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032081"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes

W przypadku platformy .NET Core <xref:System.UnauthorizedAccessException> jest generowany, gdy wywołujący próbuje ustawić wartość atrybutu pliku, ale nie ma uprawnienia do zapisu.

#### <a name="change-description"></a>Zmień opis

W .NET Framework <xref:System.ArgumentException> jest generowany, gdy obiekt wywołujący próbuje ustawić wartość atrybutu pliku w programie, <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> ale nie ma uprawnienia do zapisu. W przypadku platformy .NET Core <xref:System.UnauthorizedAccessException> jest zgłaszany. (W programie .NET Core <xref:System.ArgumentException> jest nadal zgłaszane, jeśli obiekt wywołujący podejmie próbę ustawienia nieprawidłowego atrybutu pliku).

#### <a name="version-introduced"></a>Wprowadzona wersja

1,0

#### <a name="recommended-action"></a>Zalecana akcja

Zmodyfikuj wszelkie `catch` instrukcje, aby przechwycić <xref:System.UnauthorizedAccessException> zamiast lub, w razie potrzeby,, lub oprócz, <xref:System.ArgumentException> .

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
