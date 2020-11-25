---
title: 'Nieprzerwana zmiana: Blazor: funkcja ProtectedBrowserStorage została przeniesiona do platformy udostępnionej'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: ProtectedBrowserStorage funkcja została przeniesiona do platformy udostępnionej'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761479"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: funkcja ProtectedBrowserStorage została przeniesiona do platformy udostępnionej

W ramach wersji ASP.NET Core 5,0 RC2 `ProtectedBrowserStorage` funkcja została przeniesiona do ASP.NET Core udostępnionej platformy.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

## <a name="old-behavior"></a>Stare zachowanie

W ASP.NET Core 5,0 wersja zapoznawcza 8 funkcja jest dostępna jako część pakietu [Microsoft. AspNetCore. Components. Web. Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) , ale była użyteczna tylko w Blazor webassembly.

W ASP.NET Core 5,0 RC1 funkcja jest dostępna jako część pakietu [Microsoft. AspNetCore. Components. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) , który odwołuje się do `Microsoft.AspNetCore.App` udostępnionej platformy.

## <a name="new-behavior"></a>Nowe zachowanie

W ASP.NET Core 5,0 RC2 odwołanie do pakietu NuGet nie jest już potrzebne do odwoływania się do tej funkcji i korzystania z niej.

## <a name="reason-for-change"></a>Przyczyna zmiany

Przejście do udostępnionej struktury jest lepszym rozwiązaniem dla klientów środowiska użytkownika.

## <a name="recommended-action"></a>Zalecana akcja

W przypadku uaktualniania z ASP.NET Core 5,0 RC1 wykonaj następujące czynności:

1. Usuń `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` odwołanie do pakietu z projektu.
1. Zastąp element `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` pytaniem `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. Usuń wywołanie `AddProtectedBrowserStorage` z `Startup` klasy.

Jeśli uaktualniasz program ASP.NET Core 5,0 w wersji zapoznawczej 8, wykonaj następujące czynności:

1. Usuń `Microsoft.AspNetCore.Components.Web.Extensions` odwołanie do pakietu z projektu.
1. Zastąp element `using Microsoft.AspNetCore.Components.Web.Extensions;` pytaniem `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. Usuń wywołanie `AddProtectedBrowserStorage` z `Startup` klasy.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
