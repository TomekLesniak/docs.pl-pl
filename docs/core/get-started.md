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
# <a name="get-started-with-net"></a><span data-ttu-id="45e4a-103">Wprowadzenie do platformy .NET</span><span class="sxs-lookup"><span data-stu-id="45e4a-103">Get started with .NET</span></span>

<span data-ttu-id="45e4a-104">W tym artykule przedstawiono sposób tworzenia i uruchamiania "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="45e4a-104">This article teaches you how to create and run a "Hello World!"</span></span> <span data-ttu-id="45e4a-105">Aplikacja platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="45e4a-105">.NET app.</span></span>

<span data-ttu-id="45e4a-106">Jeśli nie masz pewności, co to jest platforma .NET, Zacznij od [wprowadzenia do platformy .NET](introduction.md).</span><span class="sxs-lookup"><span data-stu-id="45e4a-106">If you're unsure what .NET is, start with the [.NET introduction](introduction.md).</span></span>

## <a name="create-an-application"></a><span data-ttu-id="45e4a-107">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="45e4a-107">Create an application</span></span>

<span data-ttu-id="45e4a-108">Najpierw pobierz i zainstaluj [zestaw SDK platformy .NET](https://dotnet.microsoft.com/download/dotnet-core) na komputerze.</span><span class="sxs-lookup"><span data-stu-id="45e4a-108">First, download and install the [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core) on your computer.</span></span>

<span data-ttu-id="45e4a-109">Następnie otwórz Terminal, taki jak **PowerShell**, **wiersza polecenia**lub **bash**.</span><span class="sxs-lookup"><span data-stu-id="45e4a-109">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="45e4a-110">Wprowadź następujące `dotnet` polecenia, aby utworzyć i uruchomić aplikację w języku C#:</span><span class="sxs-lookup"><span data-stu-id="45e4a-110">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="45e4a-111">Zobaczysz następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="45e4a-111">You see the following output:</span></span>

```output
Hello World!
```

<span data-ttu-id="45e4a-112">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="45e4a-112">Congratulations!</span></span> <span data-ttu-id="45e4a-113">Utworzono prostą aplikację platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="45e4a-113">You've created a simple .NET application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45e4a-114">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="45e4a-114">Next steps</span></span>

<span data-ttu-id="45e4a-115">Zacznij opracowywać aplikacje platformy .NET, wykonując instrukcje [krok po kroku](../standard/get-started.md) lub oglądając [wideo z programu .NET 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) w serwisie YouTube.</span><span class="sxs-lookup"><span data-stu-id="45e4a-115">Get started developing .NET applications by following a [step-by-step tutorial](../standard/get-started.md) or by watching [.NET 101 videos](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) on YouTube.</span></span>
