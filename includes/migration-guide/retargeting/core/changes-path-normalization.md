---
ms.openlocfilehash: 7c4b9faf25853c1c7a546f06c329f6f153eef904
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606666"
---
### <a name="changes-in-path-normalization"></a>Zmiany normalizacji ścieżki

#### <a name="details"></a>Szczegóły

Począwszy od aplikacji przeznaczonych dla .NET Framework 4.6.2, sposób, w jaki środowisko uruchomieniowe normalizuje ścieżki, zostało zmienione. Normalizowanie ścieżki polega na zmodyfikowaniu ciągu, który identyfikuje ścieżkę lub plik, tak aby był zgodny z prawidłową ścieżką w docelowym systemie operacyjnym. Normalizacja zazwyczaj obejmuje:

- Separatory składników formę kanoniczną działa i katalogów.
- Zastosowanie bieżącego katalogu do ścieżki względnej.
- Ocenianie katalogu względnego (.) lub katalogu nadrzędnego (..) w ścieżce.
- Przycinanie określonych znaków.
Począwszy od aplikacji przeznaczonych dla .NET Framework 4.6.2, następujące zmiany normalizacji ścieżki są domyślnie włączone:
  - Środowisko uruchomieniowe odkłada do funkcji [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) systemu operacyjnego, aby znormalizować ścieżki.
- Normalizacja nie obejmuje już przecinania końców segmentów katalogów (takich jak spacja na końcu nazwy katalogu).
- Obsługa składni ścieżki urządzenia w pełnym zaufaniu, w tym `\\.\` i dla interfejsów API we/wy plików w mscorlib.dll, `\\?\` .
- Środowisko uruchomieniowe nie sprawdza poprawności ścieżek składni urządzeń.
- Obsługiwane jest użycie składni urządzenia w celu uzyskania dostępu do alternatywnych strumieni danych.
Te zmiany zwiększają wydajność, a jednocześnie umożliwiają uzyskanie dostępu do wcześniej niedostępnych ścieżek. Ta zmiana nie wpłynie na aplikacje, które są przeznaczone dla .NET Framework 4.6.1 i wcześniejszych wersji, ale działają na .NET Framework 4.6.2 lub nowszych.

#### <a name="suggestion"></a>Sugestia

Aplikacje przeznaczone dla .NET Framework 4.6.2 lub nowszych mogą zrezygnować z tej zmiany i użyć starszej normalizacji, dodając następujący element do `<runtime>` sekcji pliku konfiguracyjnego aplikacji:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

Aplikacje, które są przeznaczone dla .NET Framework 4.6.1 lub wcześniejszych, ale działają na .NET Framework 4.6.2 lub później, mogą umożliwić zmianę normalizacji ścieżki, dodając następujący wiersz do `<runtime>` sekcji pliku Application. Configuration:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Mały       |
| Wersja | 4.6.2       |
| Typ    | Przekierowanie |
