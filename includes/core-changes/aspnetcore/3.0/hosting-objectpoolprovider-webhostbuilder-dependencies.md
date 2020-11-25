---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032759"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hosting: ObjectPoolProvider usunięte z zależności WebHostBuilder

W ramach wprowadzania ASP.NET Core więcej opłat za odtwarzanie, `ObjectPoolProvider` została usunięta z głównego zestawu zależności. Zależne składniki są `ObjectPoolProvider` teraz dodawane do siebie.

Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 5944](https://github.com/dotnet/aspnetcore/issues/5944).

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="old-behavior"></a>Stare zachowanie

`WebHostBuilder``ObjectPoolProvider`Domyślnie jest dostępna w kontenerze di.

#### <a name="new-behavior"></a>Nowe zachowanie

`WebHostBuilder` nie zapewnia już `ObjectPoolProvider` domyślnego ustawienia w kontenerze di.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona, aby ASP.NET Core więcej opłat za odtwarzanie.

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli dany składnik wymaga programu, należy go `ObjectPoolProvider` dodać do swoich zależności za pośrednictwem `IServiceCollection` .

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
