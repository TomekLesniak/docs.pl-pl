---
ms.openlocfilehash: 65fa5d8629ce8e426cf1623590a056e5cad0b91f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497325"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>Platforma .NET Interop będzie teraz w języku QueryInterface dla IAgileObject (interfejs WinRT)

#### <a name="details"></a>Szczegóły

W przypadku użycia zdarzenia WinRT z delegatem platformy .NET system Windows będzie QI do IAgileObject, począwszy od .NET Framework 4,8.  W poprzednich wersjach .NET Framework środowisko uruchomieniowe zakończy się niepowodzeniem i nie będzie mogło subskrybować tego zdarzenia.<ul><li>[x] Quirked</li></ul>

#### <a name="suggestion"></a>Sugestia

W przypadku włączenia QI na potrzeby wykonywania przerwań IAgileObject można wyłączyć ten kod, ustawiając poniższą konfigurację. <h4>Metoda 1: zmienna środowiskowa</h4> Ustaw następujące zmienne środowiskowe: Metoda COMPLUS_DisableCCWSupportIAgileObject = 1This ma wpływ na dowolne środowisko, które dziedziczy tę zmienną środowiskową. Może to być tylko jedna sesja konsoli lub może mieć wpływ na całą maszynę, jeśli zmienna środowiskowa jest ustawiona globalnie. W nazwie zmiennej środowiskowej nie jest rozróżniana wielkość liter. <h4>Metoda 2. Rejestr</h4> Korzystając z edytora rejestru (regedit.exe), Znajdź jeden z następujących podkluczy: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER \SOFTWARE\Microsoft.NETFrameworkThen Dodaj następujące: value Name: DisableCCWSupportIAgileObject Type: DWORD (32-bit) Value (zwane również REG_WORD) Value: 1You może użyć narzędzia REG.EXE systemu Windows, aby dodać tę wartość z poziomu wiersza polecenia lub skryptów. Przykład:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>W tym przypadku <code>HKLM</code> jest używany zamiast <code>HKEY_LOCAL_MACHINE</code> . Użyj <code>reg add /?</code> , aby wyświetlić pomoc dotyczącą tej składni. W nazwie wartości rejestru nie jest rozróżniana wielkość liter.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
