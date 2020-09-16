---
title: Wprowadzenie do platformy .NET Core
description: Znajdź zasoby, aby dowiedzieć się, jak tworzyć aplikacje .NET Core w systemach Windows, Linux i macOS.
author: adegeo
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 6106f66dfbbe382ee9f61eb8b7bda70ab9b72d0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538552"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="26661-103">Wprowadzenie do platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="26661-103">Get started with .NET Core</span></span>

<span data-ttu-id="26661-104">Ten artykuł zawiera informacje na temat rozpoczynania pracy z platformą .NET Core.</span><span class="sxs-lookup"><span data-stu-id="26661-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="26661-105">Program .NET Core można zainstalować w systemach Windows, Linux i macOS.</span><span class="sxs-lookup"><span data-stu-id="26661-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="26661-106">Możesz zakodować w ulubionym edytorze tekstów i tworzyć Międzyplatformowe biblioteki i aplikacje.</span><span class="sxs-lookup"><span data-stu-id="26661-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="26661-107">Jeśli nie masz pewności, co to jest platforma .NET Core lub jak odnosi się do innych technologii .NET, Zacznij od omówienia [programu .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) .</span><span class="sxs-lookup"><span data-stu-id="26661-107">If you're unsure what .NET Core is or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="26661-108">Po prostu, .NET Core to wieloplatformowa implementacja platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="26661-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="26661-109">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="26661-109">Create an application</span></span>

<span data-ttu-id="26661-110">Najpierw pobierz i zainstaluj [zestaw .NET Core SDK](https://dotnet.microsoft.com/download) na komputerze.</span><span class="sxs-lookup"><span data-stu-id="26661-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="26661-111">Następnie otwórz Terminal, taki jak **PowerShell**, **wiersza polecenia**lub **bash**.</span><span class="sxs-lookup"><span data-stu-id="26661-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="26661-112">Wprowadź następujące `dotnet` polecenia, aby utworzyć i uruchomić aplikację w języku C#:</span><span class="sxs-lookup"><span data-stu-id="26661-112">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="26661-113">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="26661-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="26661-114">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="26661-114">Congratulations!</span></span> <span data-ttu-id="26661-115">Utworzono prostą aplikację platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="26661-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="26661-116">Można również użyć [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (tylko Windows) lub [Visual Studio dla komputerów Mac](tutorials/with-visual-studio-mac.md) (tylko macOS), aby utworzyć aplikację platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="26661-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/with-visual-studio-mac.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="26661-117">Samouczki</span><span class="sxs-lookup"><span data-stu-id="26661-117">Tutorials</span></span>

<span data-ttu-id="26661-118">Zacznij opracowywać aplikacje platformy .NET Core, wykonując następujące Samouczki krok po kroku:</span><span class="sxs-lookup"><span data-stu-id="26661-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="26661-119">Windows</span><span class="sxs-lookup"><span data-stu-id="26661-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="26661-120">Tworzenie pierwszej aplikacji konsolowej .NET Core w programie Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="26661-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="26661-121">Kompilowanie biblioteki klas przy użyciu .NET Standard w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="26661-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="26661-122">Samouczek: Tworzenie aplikacji konsolowej platformy .NET Core przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="26661-122">Tutorial: Create a .NET Core console app using Visual Studio Code</span></span>](tutorials/with-visual-studio-code.md)

|   |   |
|---|---|
| <span data-ttu-id="26661-123">![ikona aparatu filmu wideo](./media/video-icon.png "Obejrzyj film")</span><span class="sxs-lookup"><span data-stu-id="26661-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="26661-124">Obejrzyj, [jak zainstalować i używać Visual Studio Code i środowiska .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) wideo w witrynie Channel 9.</span><span class="sxs-lookup"><span data-stu-id="26661-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="26661-125">![ikona aparatu filmu wideo](./media/video-icon.png "Obejrzyj film")</span><span class="sxs-lookup"><span data-stu-id="26661-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="26661-126">Obejrzyj wideo z programem [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) w serwisie YouTube.</span><span class="sxs-lookup"><span data-stu-id="26661-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="26661-127">Listę obsługiwanych wersji systemu Windows zawiera artykuł [zależności i wymagania dotyczące platformy .NET Core](./install/windows.md) .</span><span class="sxs-lookup"><span data-stu-id="26661-127">See the [.NET Core dependencies and requirements](./install/windows.md) article for a list of the supported Windows versions.</span></span>

# <a name="linux"></a>[<span data-ttu-id="26661-128">Linux</span><span class="sxs-lookup"><span data-stu-id="26661-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="26661-129">Zacznij opracowywać aplikacje platformy .NET Core, wykonując następujące Samouczki krok po kroku:</span><span class="sxs-lookup"><span data-stu-id="26661-129">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="26661-130">Samouczek: Tworzenie aplikacji konsolowej platformy .NET Core przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="26661-130">Tutorial: Create a .NET Core console app using Visual Studio Code</span></span>](tutorials/with-visual-studio-code.md)

|   |   |
|---|---|
| <span data-ttu-id="26661-131">![ikona aparatu filmu wideo](./media/video-icon.png "Obejrzyj film")</span><span class="sxs-lookup"><span data-stu-id="26661-131">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="26661-132">Obejrzyj film wideo [z wprowadzeniem do Visual Studio Code przy użyciu języków C# i .NET Core w systemie Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="26661-132">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="26661-133">Listę obsługiwanych dystrybucje i wersji systemu Linux znajduje się w artykule [zależności i wymagania dotyczące platformy .NET Core](./install/linux.md) .</span><span class="sxs-lookup"><span data-stu-id="26661-133">See the [.NET Core dependencies and requirements](./install/linux.md) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macos"></a>[<span data-ttu-id="26661-134">macOS</span><span class="sxs-lookup"><span data-stu-id="26661-134">macOS</span></span>](#tab/macos)

<span data-ttu-id="26661-135">Zacznij opracowywać aplikacje platformy .NET Core, wykonując następujące Samouczki krok po kroku:</span><span class="sxs-lookup"><span data-stu-id="26661-135">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="26661-136">Samouczek: Tworzenie aplikacji konsolowej platformy .NET Core przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="26661-136">Tutorial: Create a .NET Core console application using Visual Studio Code</span></span>](tutorials/with-visual-studio-code.md)
- [<span data-ttu-id="26661-137">Samouczek: Tworzenie aplikacji konsolowej platformy .NET Core przy użyciu Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="26661-137">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>](tutorials/with-visual-studio-mac.md)
- [<span data-ttu-id="26661-138">Kompilowanie biblioteki .NET Standard w macOS przy użyciu Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="26661-138">Build a .NET Standard library on macOS using Visual Studio for Mac</span></span>](tutorials/library-with-visual-studio-mac.md)

|   |   |
|---|---|
| <span data-ttu-id="26661-139">![ikona aparatu filmu wideo](media/video-icon.png "Obejrzyj film")</span><span class="sxs-lookup"><span data-stu-id="26661-139">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="26661-140">Obejrzyj film wideo [z wprowadzeniem do Visual Studio Code przy użyciu języków C# i .NET Core w systemie macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="26661-140">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="26661-141">Listę obsługiwanych wersji systemu OS X/macOS można znaleźć w artykule [zależności i wymagania dotyczące platformy .NET Core](./install/macos.md) .</span><span class="sxs-lookup"><span data-stu-id="26661-141">See the [.NET Core dependencies and requirements](./install/macos.md) article for a list of the supported OS X / macOS versions.</span></span>

---
