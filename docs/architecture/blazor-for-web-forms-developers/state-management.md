---
title: Zarządzanie stanem
description: Poznaj różne podejścia do zarządzania stanem w ASP.NET Web Forms i Blazor.
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: 2ca811f886c6a245ac16c2bd66a68ff16e5bfc44
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267727"
---
# <a name="state-management"></a>Zarządzanie stanem

Zarządzanie stanem to kluczowa koncepcja aplikacji formularzy sieci Web, ułatwiająca Wyświetlanie stanu widoku, stanu sesji, stanu aplikacji i funkcji ogłaszania zwrotnego. Te funkcje stanowe platformy umożliwiają ukrycie zarządzania stanem wymaganego dla aplikacji i umożliwiają deweloperom aplikacji skoncentrowanie się na dostarczaniu ich funkcjonalności. W przypadku ASP.NET Core i Blazor niektóre z tych funkcji zostały odłożone, a niektóre zostały całkowicie usunięte. W tym rozdziale opisano, jak zachować stan i zapewnić te same funkcje przy użyciu nowych funkcji w programie Blazor.

## <a name="request-state-management-with-viewstate"></a>Zażądaj zarządzania stanem za pomocą elementu ViewState

Podczas omawiania zarządzania stanami w aplikacji formularzy sieci Web wiele deweloperów będzie od razu traktować stan wyświetlania. W formularzach sieci Web stan wyświetlania służy do zarządzania stanem zawartości między żądaniami HTTP przez wysyłanie dużego zakodowanego bloku tekstu z powrotem do przeglądarki. Pole elementu ViewState może być przeciążone z zawartością strony zawierającej wiele elementów, co może potrwać kilka megabajtów.

W przypadku serwera Blazor aplikacja utrzymuje ciągłe połączenie z serwerem. Stan aplikacji nazywany *obwodem*jest przechowywany w pamięci serwera, gdy połączenie jest uznawane za aktywne. Stan zostanie usunięty tylko wtedy, gdy użytkownik nawiguje do aplikacji lub konkretnej strony w aplikacji. Wszystkie elementy członkowskie aktywnych składników są dostępne między interakcjami z serwerem.

Ta funkcja ma kilka zalet:

- Stan składnika jest łatwo dostępny i nie został odbudowany między interakcjami.
- Stan nie jest przesyłany do przeglądarki.

Istnieją jednak pewne wady dotyczące trwałości stanu składnika w pamięci, które należy wziąć pod uwagę:

- Jeśli serwer zostanie ponownie uruchomiony między żądaniem, stan zostanie utracony.
- Rozwiązanie równoważenia obciążenia serwera sieci Web aplikacji musi zawierać sesje programu Sticky, aby upewnić się, że wszystkie żądania z tej samej przeglądarki zwracają do tego samego serwera. Jeśli żądanie przejdzie do innego serwera, stan zostanie utracony.
- Trwałość stanu składnika na serwerze może prowadzić do wykorzystania pamięci na serwerze sieci Web.

Z powyższych powodów nie należy polegać tylko na stanie składnika, który znajduje się w pamięci na serwerze. Aplikacja powinna również zawierać zapasowe magazyny danych dla danych między żądaniami. Niektóre proste przykłady tej strategii:

- W aplikacji koszyka zakupów Utrwalaj zawartość nowych elementów dodanych do koszyka w rekordzie bazy danych. Jeśli stan serwera zostanie utracony, można go odtworzyć z rekordów bazy danych.
- W wieloczęściowym formularzu sieci Web użytkownicy będą oczekiwać, że aplikacja zapamięta wartości między każdym żądaniem. Zapisz dane między każdym z wpisów użytkownika w magazynie danych, tak aby mogły być pobierane i zmontowane do struktury odpowiedzi w postaci końcowej w przypadku zakończenia formularza wieloczęściowego.

Aby uzyskać dodatkowe informacje na temat zarządzania stanem w aplikacjach Blazor, zobacz [ASP.NET Core Blazor State Management](/aspnet/core/blazor/state-management).

## <a name="maintain-state-with-session"></a>Obsługa stanu przy użyciu sesji

Deweloperzy formularzy sieci Web mogą obsługiwać informacje o aktualnie działającym użytkowniku z <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> obiektem dictionary. Wystarczy dodać obiekt z kluczem ciągu do `Session` , a ten obiekt będzie dostępny w późniejszym czasie podczas interakcji użytkownika z aplikacją. Przy próbie wyeliminowania zarządzania współpracującego z protokołem HTTP, `Session` obiekt ułatwiający zachowanie stanu.

Sygnatura .NET Framework `Session` obiektu nie jest taka sama jak `Session` obiekt ASP.NET Core. Przed podjęciem decyzji o migracji i użyciu nowej funkcji stanu sesji należy wziąć pod uwagę [dokumentację nowej sesji ASP.NET Core](/dotnet/api/microsoft.aspnetcore.http.isession) .

Sesja jest dostępna na serwerze ASP.NET Core i Blazor, ale nie zaleca się ich używania na rzecz przechowywania danych w repozytorium danych. Stan sesji nie działa również, gdy osoby odwiedzające odrzuciją używanie plików cookie protokołu HTTP w aplikacji ze względu na kwestie związane z ochroną prywatności.

Konfiguracja ASP.NET Core i stanu sesji jest dostępna w temacie [Zarządzanie sesjami i Stanami w ASP.NET Core artykule](/aspnet/core/fundamentals/app-state#session-state).

## <a name="application-state"></a>Stan aplikacji

`Application`Obiekt w strukturze formularzy sieci Web zawiera ogromne repozytorium żądania dla wielu żądań na potrzeby współpracy z konfiguracją i stanem zakresu aplikacji. Stan aplikacji to idealne miejsce do przechowywania różnych właściwości konfiguracji aplikacji, do których odwołują się wszystkie żądania, niezależnie od użytkownika wysyłającego żądanie. Problem z `Application` obiektem był nietrwały na wielu serwerach. Stan obiektu aplikacji został utracony między ponownymi uruchomieniami.

W programie `Session` zaleca się, aby dane były przenoszone do trwałego magazynu zapasowego, do którego można uzyskać dostęp za pomocą wielu wystąpień serwera. Jeśli istnieją nietrwałe dane, które mają być dostępne między żądaniami i użytkownikami, można je łatwo zapisać w pojedynczej usłudze, która może zostać wprowadzona do składników, które wymagają tych informacji lub interakcji.

Konstrukcja obiektu do obsługi stanu aplikacji i jego zużycia może wyglądać podobnie do następującej implementacji:

```csharp
public class MyApplicationState
{
    public int VisitorCounter { get; private set; } = 0;

    public void IncrementCounter() => VisitorCounter += 1;
}
```

```csharp
app.AddSingleton<MyApplicationState>();
```

```razor
@inject MyApplicationState AppState

<label>Total Visitors: @AppState.VisitorCounter</label>
```

`MyApplicationState`Obiekt jest tworzony tylko raz na serwerze, a wartość `VisitorCounter` jest pobierana i wyprowadzana w etykiecie składnika. `VisitorCounter`Wartość powinna być utrwalana i pobierana z magazynu danych zapasowych w celu zapewnienia trwałości i skalowalności.

## <a name="in-the-browser"></a>W przeglądarce

Dane aplikacji mogą być również przechowywane po stronie klienta na urządzeniu użytkownika, aby były dostępne w przyszłości. Istnieją dwie funkcje przeglądarki, które umożliwiają trwałość danych w różnych zakresach przeglądarki użytkownika:

- `localStorage` — zakres do całej przeglądarki użytkownika. Jeśli strona zostanie ponownie załadowana, przeglądarka zostanie zamknięta i ponownie otwarta lub zostanie otwarta inna karta z tym samym adresem URL, a następnie `localStorage` jest on dostarczany przez przeglądarkę.
- `sessionStorage` — zakres na bieżącą kartę przeglądarki użytkownika. Po ponownym załadowaniu karty stan będzie się utrzymywał. Jednak jeśli użytkownik otworzy kolejną kartę do aplikacji lub zamknie i ponownie otworzy przeglądarkę, stan zostanie utracony.

Można napisać niestandardowy kod JavaScript w celu współdziałania z tymi funkcjami lub wiele pakietów NuGet, których można użyć w celu zapewnienia tej funkcji. Jeden taki pakiet to [Microsoft. AspNetCore. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage).

Aby uzyskać instrukcje dotyczące korzystania z tego pakietu do współpracy z programem `localStorage` i `sessionStorage` , zobacz artykuł dotyczący [zarządzania stanem Blazor](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) .

>[!div class="step-by-step"]
>[Poprzedni](pages-routing-layouts.md) 
> [Dalej](forms-validation.md)
