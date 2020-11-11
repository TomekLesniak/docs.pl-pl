---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506881"
---

Pakiety dodane do źródeł Menedżera pakietów są nazywane w formacie włamywania: `{product}-{type}-{version}` .

- **iloczyn**\
Typ produktu .NET do zainstalowania. Prawidłowe opcje to:

  - dotnet
  - aspnetcore

- **Wprowadź**\
Wybiera zestaw SDK lub środowisko uruchomieniowe. Prawidłowe opcje to:

  - sdk
  - środowisko uruchomieniowe

- **Wersja**\
Wersja zestawu SDK lub środowiska uruchomieniowego do zainstalowania. Ten artykuł będzie zawsze zawierać instrukcje dotyczące najnowszej obsługiwanej wersji. Prawidłowe opcje to wszystkie wydane wersje, takie jak:

  - 5,0
  - 3,1
  - 3.0
  - 2.1

  Możliwe, że zestaw SDK/środowisko uruchomieniowe, które próbujesz pobrać, nie jest dostępny dla dystrybucji systemu Linux. Aby zapoznać się z listą obsługiwanych dystrybucji, zobacz temat [zależności i wymagania dotyczące platformy .NET Core](../linux.md).

### <a name="examples"></a>Przykłady

- Zainstaluj środowisko uruchomieniowe ASP.NET Core 5,0: `aspnetcore-runtime-5.0`
- Zainstaluj środowisko uruchomieniowe programu .NET Core 2,1: `dotnet-runtime-2.1`
- Zainstaluj zestaw .NET 5,0 SDK: `dotnet-sdk-5.0`
- Zainstaluj zestaw SDK platformy .NET Core 3,1: `dotnet-sdk-3.1`

### <a name="package-missing"></a>Brak pakietu

Jeśli kombinacja pakiet-wersja nie działa, jest niedostępna. Na przykład nie istnieje zestaw SDK ASP.NET Core, składniki zestawu SDK są dołączone do zestawu .NET SDK. Wartość `aspnetcore-sdk-2.2` jest niepoprawna i powinna być `dotnet-sdk-2.2` . Aby uzyskać listę dystrybucji systemu Linux obsługiwanych przez platformę .NET Core, zobacz [zależności i wymagania dotyczące platformy .NET](../linux.md).
