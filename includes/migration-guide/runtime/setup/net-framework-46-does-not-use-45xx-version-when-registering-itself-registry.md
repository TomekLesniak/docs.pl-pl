---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496195"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>W .NET Framework 4,6 nie jest używana wersja 4.5. x. x podczas rejestrowania się w rejestrze

#### <a name="details"></a>Szczegóły

Ponieważ jeden z nich może oczekiwać, klucz wersji ustawiony w rejestrze (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code> ) dla .NET Framework 4,6 rozpoczyna się od "4,6", a nie "4,5". Aplikacje, które są zależne od tych kluczy rejestru, aby wiedzieć, które wersje .NET Framework są zainstalowane na komputerze, należy zaktualizować, aby zrozumieć, że 4,6 to nowa możliwa wersja i taka, która jest zgodna z poprzednimi wersjami 4.5. x.

#### <a name="suggestion"></a>Sugestia

Zaktualizuj aplikacje sondowania dla .NET Framework 4,5, wyszukując klucze rejestru 4,5, aby akceptować 4,6.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,6|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
