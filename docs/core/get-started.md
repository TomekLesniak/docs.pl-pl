---
title: Wprowadzenie do platformy .NET
description: Utwórz aplikację platformy .NET Hello world.
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756094"
---
# <a name="get-started-with-net"></a>Wprowadzenie do platformy .NET

W tym artykule przedstawiono sposób tworzenia i uruchamiania "Hello world!" Aplikacja platformy .NET.

Jeśli nie masz pewności, co to jest platforma .NET, Zacznij od [wprowadzenia do platformy .NET](introduction.md).

## <a name="create-an-application"></a>Tworzenie aplikacji

Najpierw pobierz i zainstaluj [zestaw SDK platformy .NET](https://dotnet.microsoft.com/download/dotnet-core) na komputerze.

Następnie otwórz Terminal, taki jak **PowerShell**, **wiersza polecenia**lub **bash**. Wprowadź następujące `dotnet` polecenia, aby utworzyć i uruchomić aplikację w języku C#:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Zobaczysz następujące dane wyjściowe:

```output
Hello World!
```

Gratulacje! Utworzono prostą aplikację platformy .NET.

## <a name="next-steps"></a>Następne kroki

Zacznij opracowywać aplikacje platformy .NET, wykonując instrukcje [krok po kroku](../standard/get-started.md) lub oglądając [wideo z programu .NET 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) w serwisie YouTube.
