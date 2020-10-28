---
title: Używanie iniekcji zależności w programie .NET
description: Dowiedz się, jak używać iniekcji zależności w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/23/2020
ms.topic: tutorial
no-loc:
- ':::no-loc(Transient):::'
- ':::no-loc(Scoped):::'
- ':::no-loc(Singleton):::'
- ':::no-loc(Example):::'
ms.openlocfilehash: 589e15736c07b465fda308b04c91384a2502755c
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888586"
---
# <a name="tutorial-use-dependency-injection-in-net"></a><span data-ttu-id="fd885-103">Samouczek: używanie iniekcji zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="fd885-103">Tutorial: Use dependency injection in .NET</span></span>

<span data-ttu-id="fd885-104">W tym samouczku pokazano, jak używać [iniekcji zależności (di) w programie .NET](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="fd885-104">This tutorial shows how to use [dependency injection (DI) in .NET](dependency-injection.md).</span></span> <span data-ttu-id="fd885-105">Przy użyciu *rozszerzeń Microsoft* di jest obywatelem pierwszej klasy, gdzie usługi są dodawane i konfigurowane w <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> .</span><span class="sxs-lookup"><span data-stu-id="fd885-105">With *Microsoft Extensions* , DI is a first-class citizen where services are added and configured in an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="fd885-106"><xref:Microsoft.Extensions.Hosting.IHost>Interfejs uwidacznia <xref:System.IServiceProvider> wystąpienie, które działa jako kontener wszystkich zarejestrowanych usług.</span><span class="sxs-lookup"><span data-stu-id="fd885-106">The <xref:Microsoft.Extensions.Hosting.IHost> interface exposes the <xref:System.IServiceProvider> instance, which acts as a container of all the registered services.</span></span>

<span data-ttu-id="fd885-107">Ten samouczek zawiera informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="fd885-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="fd885-108">Tworzenie aplikacji konsolowej platformy .NET korzystającej z iniekcji zależności</span><span class="sxs-lookup"><span data-stu-id="fd885-108">Create a .NET console app that uses dependency injection</span></span>
> - <span data-ttu-id="fd885-109">Kompilowanie i Konfigurowanie [hosta ogólnego](generic-host.md)</span><span class="sxs-lookup"><span data-stu-id="fd885-109">Build and configure a [Generic Host](generic-host.md)</span></span>
> - <span data-ttu-id="fd885-110">Napisz kilka interfejsów i odpowiadające im implementacje</span><span class="sxs-lookup"><span data-stu-id="fd885-110">Write several interfaces and corresponding implementations</span></span>
> - <span data-ttu-id="fd885-111">Używaj okresu istnienia usługi i zakresu dla DI</span><span class="sxs-lookup"><span data-stu-id="fd885-111">Use service lifetime and scoping for DI</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd885-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="fd885-112">Prerequisites</span></span>

- <span data-ttu-id="fd885-113">[.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="fd885-113">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or later.</span></span>
- <span data-ttu-id="fd885-114">Znajomość tworzenia nowych aplikacji .NET i instalowania pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="fd885-114">Familiarity with creating new .NET applications and installing NuGet packages.</span></span>

## <a name="create-a-new-console-application"></a><span data-ttu-id="fd885-115">Utwórz nową aplikację konsolową</span><span class="sxs-lookup"><span data-stu-id="fd885-115">Create a new console application</span></span>

<span data-ttu-id="fd885-116">Za pomocą [nowego polecenia dotnet](../tools/dotnet-new.md) lub Kreatora nowego projektu środowiska IDE Utwórz nową aplikację konsolową .NET o nazwie **ConsoleDI. :::no-loc(Example):::** .</span><span class="sxs-lookup"><span data-stu-id="fd885-116">Using either the [dotnet new](../tools/dotnet-new.md) command or an IDE new project wizard, create a new .NET console application named **ConsoleDI.:::no-loc(Example):::** .</span></span> <span data-ttu-id="fd885-117">Dodaj pakiet NuGet [Microsoft. Extensions. host](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) do projektu.</span><span class="sxs-lookup"><span data-stu-id="fd885-117">Add the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package to the project.</span></span>

## <a name="add-interfaces"></a><span data-ttu-id="fd885-118">Dodaj interfejsy</span><span class="sxs-lookup"><span data-stu-id="fd885-118">Add interfaces</span></span>

<span data-ttu-id="fd885-119">Dodaj następujące interfejsy do katalogu głównego projektu:</span><span class="sxs-lookup"><span data-stu-id="fd885-119">Add the following interfaces to the project root directory:</span></span>

<span data-ttu-id="fd885-120">*IOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="fd885-120">*IOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

<span data-ttu-id="fd885-121">`IOperation`Interfejs definiuje pojedynczą `OperationId` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="fd885-121">The `IOperation` interface defines a single `OperationId` property.</span></span>

<span data-ttu-id="fd885-122">*:::no-loc(Transient):::Operation.cs*</span><span class="sxs-lookup"><span data-stu-id="fd885-122">*I:::no-loc(Transient):::Operation.cs*</span></span>

<span data-ttu-id="fd885-123">::: Code Language = "CSharp" source = "fragmenty kodu/Configuration/Console-di/I :::no-loc(Transient)::: Operation.cs"::</span><span class="sxs-lookup"><span data-stu-id="fd885-123">:::code language="csharp" source="snippets/configuration/console-di/I:::no-loc(Transient):::Operation.cs":::</span></span>

<span data-ttu-id="fd885-124">*:::no-loc(Scoped):::Operation.cs*</span><span class="sxs-lookup"><span data-stu-id="fd885-124">*I:::no-loc(Scoped):::Operation.cs*</span></span>

<span data-ttu-id="fd885-125">::: Code Language = "CSharp" source = "fragmenty kodu/Configuration/Console-di/I :::no-loc(Scoped)::: Operation.cs"::</span><span class="sxs-lookup"><span data-stu-id="fd885-125">:::code language="csharp" source="snippets/configuration/console-di/I:::no-loc(Scoped):::Operation.cs":::</span></span>

<span data-ttu-id="fd885-126">*:::no-loc(Singleton):::Operation.cs*</span><span class="sxs-lookup"><span data-stu-id="fd885-126">*I:::no-loc(Singleton):::Operation.cs*</span></span>

<span data-ttu-id="fd885-127">::: Code Language = "CSharp" source = "fragmenty kodu/Configuration/Console-di/I :::no-loc(Singleton)::: Operation.cs"::</span><span class="sxs-lookup"><span data-stu-id="fd885-127">:::code language="csharp" source="snippets/configuration/console-di/I:::no-loc(Singleton):::Operation.cs":::</span></span>

<span data-ttu-id="fd885-128">Wszystkie podinterfejsy `IOperation` nazwy mają swój przewidziany okres istnienia usługi.</span><span class="sxs-lookup"><span data-stu-id="fd885-128">All of the subinterfaces of `IOperation` name their intended service lifetime.</span></span> <span data-ttu-id="fd885-129">Na przykład " :::no-loc(Transient)::: " lub " :::no-loc(Singleton)::: ".</span><span class="sxs-lookup"><span data-stu-id="fd885-129">For example, ":::no-loc(Transient):::" or ":::no-loc(Singleton):::".</span></span>

## <a name="add-default-implementation"></a><span data-ttu-id="fd885-130">Dodaj implementację domyślną</span><span class="sxs-lookup"><span data-stu-id="fd885-130">Add default implementation</span></span>

<span data-ttu-id="fd885-131">Dodaj następującą implementację domyślną dla różnych operacji:</span><span class="sxs-lookup"><span data-stu-id="fd885-131">Add the following default implementation for the various operations:</span></span>

<span data-ttu-id="fd885-132">*DefaultOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="fd885-132">*DefaultOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

<span data-ttu-id="fd885-133">`DefaultOperation`Implementuje wszystkie nazwane interfejsy znacznika i inicjuje `OperationId` Właściwość do czterech ostatnich znaków nowego unikatowego identyfikatora globalnego (GUID).</span><span class="sxs-lookup"><span data-stu-id="fd885-133">The `DefaultOperation` implements all of the named marker interfaces and initializes the `OperationId` property to the last four characters of a new globally unique identifier (GUID).</span></span>

## <a name="add-service-that-requires-di"></a><span data-ttu-id="fd885-134">Dodaj usługę wymagającą DI</span><span class="sxs-lookup"><span data-stu-id="fd885-134">Add service that requires DI</span></span>

<span data-ttu-id="fd885-135">Dodaj następujący obiekt rejestratora operacji, który działa jako usługa aplikacji konsolowej:</span><span class="sxs-lookup"><span data-stu-id="fd885-135">Add the following operation logger object, which acts as a service to the console app:</span></span>

<span data-ttu-id="fd885-136">*OperationLogger.cs*</span><span class="sxs-lookup"><span data-stu-id="fd885-136">*OperationLogger.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

<span data-ttu-id="fd885-137">`OperationLogger`Definiuje konstruktora, który wymaga każdego z powyższych interfejsów znacznika, czyli,, `I:::no-loc(Transient):::Operation` `I:::no-loc(Scoped):::Operation` i `I:::no-loc(Singleton):::Operation` .</span><span class="sxs-lookup"><span data-stu-id="fd885-137">The `OperationLogger` defines a constructor that requires each of the aforementioned marker interfaces, that is; `I:::no-loc(Transient):::Operation`, `I:::no-loc(Scoped):::Operation`, and `I:::no-loc(Singleton):::Operation`.</span></span> <span data-ttu-id="fd885-138">Obiekt ujawnia pojedynczą metodę, która umożliwia konsumentowi zarejestrowanie operacji przy użyciu danego `scope` parametru.</span><span class="sxs-lookup"><span data-stu-id="fd885-138">The object exposes a single method that allows the consumer to log the operations with a given `scope` parameter.</span></span> <span data-ttu-id="fd885-139">Po wywołaniu `LogOperations` Metoda rejestruje unikatowy identyfikator każdej operacji przy użyciu ciągu zakresu i komunikatu.</span><span class="sxs-lookup"><span data-stu-id="fd885-139">When invoked, the `LogOperations` method logs each operation's unique identifier with the scope string and message.</span></span>

## <a name="register-services-for-di"></a><span data-ttu-id="fd885-140">Zarejestruj usługi dla DI</span><span class="sxs-lookup"><span data-stu-id="fd885-140">Register services for DI</span></span>

<span data-ttu-id="fd885-141">Zaktualizuj *program.cs* przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="fd885-141">Update *Program.cs* with the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

<span data-ttu-id="fd885-142">Aplikacja:</span><span class="sxs-lookup"><span data-stu-id="fd885-142">The app:</span></span>

- <span data-ttu-id="fd885-143">Tworzy <xref:Microsoft.Extensions.Hosting.IHostBuilder> wystąpienie z [domyślnymi ustawieniami spinacza](generic-host.md#default-builder-settings).</span><span class="sxs-lookup"><span data-stu-id="fd885-143">Creates an <xref:Microsoft.Extensions.Hosting.IHostBuilder> instance with the [default binder settings](generic-host.md#default-builder-settings).</span></span>
- <span data-ttu-id="fd885-144">Konfiguruje usługi i dodaje je wraz z odpowiednim okresem istnienia usługi.</span><span class="sxs-lookup"><span data-stu-id="fd885-144">Configures services and adds them with their corresponding service lifetime.</span></span>
- <span data-ttu-id="fd885-145">Wywołuje <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> i przypisuje wystąpienie elementu <xref:Microsoft.Extensions.Hosting.IHost> .</span><span class="sxs-lookup"><span data-stu-id="fd885-145">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> and assigns an instance of <xref:Microsoft.Extensions.Hosting.IHost>.</span></span>
- <span data-ttu-id="fd885-146">Wywołania `ExemplifyScoping` , przekazywanie w <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fd885-146">Calls `ExemplifyScoping`, passing in the <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.</span></span>

## <a name="conclusion"></a><span data-ttu-id="fd885-147">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="fd885-147">Conclusion</span></span>

<span data-ttu-id="fd885-148">Aplikacja wyświetli dane wyjściowe podobne do następującego przykładu:</span><span class="sxs-lookup"><span data-stu-id="fd885-148">The app displays output similar to the following example:</span></span>

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): I:::no-loc(Transient):::Operation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): I:::no-loc(Scoped):::Operation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): I:::no-loc(Singleton):::Operation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): I:::no-loc(Transient):::Operation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): I:::no-loc(Scoped):::Operation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): I:::no-loc(Singleton):::Operation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): I:::no-loc(Transient):::Operation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): I:::no-loc(Scoped):::Operation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): I:::no-loc(Singleton):::Operation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): I:::no-loc(Transient):::Operation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): I:::no-loc(Scoped):::Operation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): I:::no-loc(Singleton):::Operation [ 1586...Always the same         ]
```

<span data-ttu-id="fd885-149">W danych wyjściowych aplikacji można zobaczyć, że:</span><span class="sxs-lookup"><span data-stu-id="fd885-149">From the app output, you can see that:</span></span>

- <span data-ttu-id="fd885-150">:::no-loc(Transient)::: operacje są zawsze różne, nowe wystąpienie jest tworzone przy każdym pobieraniu usługi.</span><span class="sxs-lookup"><span data-stu-id="fd885-150">:::no-loc(Transient)::: operations are always different, a new instance is created with every retrieval of the service.</span></span>
- <span data-ttu-id="fd885-151">:::no-loc(Scoped)::: operacje zmieniają się tylko z nowym zakresem, ale są tego samego wystąpienia w zakresie.</span><span class="sxs-lookup"><span data-stu-id="fd885-151">:::no-loc(Scoped)::: operations change only with a new scope, but are the same instance within a scope.</span></span>
- <span data-ttu-id="fd885-152">:::no-loc(Singleton)::: operacje są zawsze takie same. nowe wystąpienie jest tworzone tylko raz.</span><span class="sxs-lookup"><span data-stu-id="fd885-152">:::no-loc(Singleton)::: operations are always the same, a new instance is only created once.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd885-153">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fd885-153">See also</span></span>

* [<span data-ttu-id="fd885-154">Wskazówki dotyczące wstrzykiwania zależności</span><span class="sxs-lookup"><span data-stu-id="fd885-154">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
* [<span data-ttu-id="fd885-155">Wstrzykiwanie zależności w ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fd885-155">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
