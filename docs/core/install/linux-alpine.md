---
title: Instalowanie platformy .NET na platformie Alpine-.NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET na platformie Alpine.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506836"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET na platformie Alpine

W tym artykule opisano sposób instalowania programu .NET w ramach platformy Alpine. Gdy wersja Alpine nie jest objęta wsparciem, platforma .NET nie jest już obsługiwana w tej wersji. Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Brak instalatorów dla Alpine. Musisz użyć [skryptu instalacji](#scripted-install) lub instrukcji [instalacji ręcznej](#manual-install) .

## <a name="supported-distributions"></a>Obsługiwane dystrybucje

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Alpine, w których są obsługiwane. Te wersje pozostają obsługiwane do momentu, aż wersja [platformy .NET osiągnie koniec okresu obsłudze](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Alp osiągnie koniec cyklu życia](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- ✔️ wskazuje, że wersja Alpine lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja Alpine lub .NET nie jest obsługiwana w tej wersji Alpine.
- Gdy zarówno wersja Alpine, jak i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Alpine  | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|-------- |---------------|---------------|----------------|
| ✔️ 3,12 | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ 3,11 | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ 3,10 | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌ 3,9  | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌ 3,8  | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |

Następujące wersje platformy .NET nie są już obsługiwane. Pliki do pobrania dla tych nadal są publikowane:

- 3.0
- 2.2
- 2,0

## <a name="dependencies"></a>Zależności

Platforma .NET w systemie Alpine Linux wymaga zainstalowanych następujących zależności:

- ICU — libs
- krb5 — libs
- libgcc
- libintl
- libssl 1.1 (Alpine v lub nowszy)
- libssl 1.0 (Alpine v 3.8 lub Lower)
- libstdc + +
- zlib

## <a name="scripted-install"></a>Instalacja z skryptami

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalacja ręczna

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Następne kroki

- [Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code](../tutorials/with-visual-studio-code.md)
