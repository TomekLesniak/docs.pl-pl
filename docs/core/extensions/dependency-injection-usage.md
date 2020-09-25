---
title: Używanie iniekcji zależności w programie .NET
description: Dowiedz się, jak używać iniekcji zależności w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/23/2020
ms.topic: tutorial
ms.openlocfilehash: f2298cb0be6d555a7636903dc251f022a6a62a43
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247909"
---
# <a name="tutorial-use-dependency-injection-in-net"></a><span data-ttu-id="f323e-103">Samouczek: używanie iniekcji zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="f323e-103">Tutorial: Use dependency injection in .NET</span></span>

<span data-ttu-id="f323e-104">W tym samouczku pokazano, jak używać [iniekcji zależności (di) w programie .NET](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="f323e-104">This tutorial shows how to use [dependency injection (DI) in .NET](dependency-injection.md).</span></span> <span data-ttu-id="f323e-105">Przy użyciu *rozszerzeń Microsoft*di jest obywatelem pierwszej klasy, gdzie usługi są dodawane i konfigurowane w <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> .</span><span class="sxs-lookup"><span data-stu-id="f323e-105">With *Microsoft Extensions*, DI is a first-class citizen where services are added and configured in an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="f323e-106"><xref:Microsoft.Extensions.Hosting.IHost>Interfejs uwidacznia <xref:System.IServiceProvider> wystąpienie, które działa jako kontener wszystkich zarejestrowanych usług.</span><span class="sxs-lookup"><span data-stu-id="f323e-106">The <xref:Microsoft.Extensions.Hosting.IHost> interface exposes the <xref:System.IServiceProvider> instance, which acts as a container of all the registered services.</span></span>

<span data-ttu-id="f323e-107">Ten samouczek zawiera informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="f323e-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="f323e-108">Tworzenie aplikacji konsolowej platformy .NET korzystającej z iniekcji zależności</span><span class="sxs-lookup"><span data-stu-id="f323e-108">Create a .NET console app that uses dependency injection</span></span>
> - <span data-ttu-id="f323e-109">Kompilowanie i Konfigurowanie [hosta ogólnego](generic-host.md)</span><span class="sxs-lookup"><span data-stu-id="f323e-109">Build and configure a [Generic Host](generic-host.md)</span></span>
> - <span data-ttu-id="f323e-110">Napisz kilka interfejsów i odpowiadające im implementacje</span><span class="sxs-lookup"><span data-stu-id="f323e-110">Write several interfaces and corresponding implementations</span></span>
> - <span data-ttu-id="f323e-111">Używaj okresu istnienia usługi i zakresu dla DI</span><span class="sxs-lookup"><span data-stu-id="f323e-111">Use service lifetime and scoping for DI</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f323e-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f323e-112">Prerequisites</span></span>

- <span data-ttu-id="f323e-113">[.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) lub nowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="f323e-113">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="f323e-114">Zintegrowane środowisko programistyczne (IDE), [Visual Studio, Visual Studio Code lub Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com) są prawidłowymi opcjami.</span><span class="sxs-lookup"><span data-stu-id="f323e-114">An Integrated Development Environment (IDE), [Visual Studio, Visual Studio Code, or Visual Studio for Mac](https://visualstudio.microsoft.com) are all valid choices.</span></span>
- <span data-ttu-id="f323e-115">Znajomość tworzenia nowych aplikacji .NET i instalowania pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="f323e-115">Familiarity with creating new .NET applications and installing NuGet packages.</span></span>

## <a name="create-a-new-console-application"></a><span data-ttu-id="f323e-116">Utwórz nową aplikację konsolową</span><span class="sxs-lookup"><span data-stu-id="f323e-116">Create a new console application</span></span>

<span data-ttu-id="f323e-117">Za pomocą [nowego polecenia dotnet](../tools/dotnet-new.md) lub Kreatora nowego projektu środowiska IDE Utwórz nową aplikację konsolową .NET o nazwie **ConsoleDI. example**.</span><span class="sxs-lookup"><span data-stu-id="f323e-117">Using either the [dotnet new](../tools/dotnet-new.md) command or an IDE new project wizard, create a new .NET console application named **ConsoleDI.Example**.</span></span> <span data-ttu-id="f323e-118">Dodaj pakiet NuGet [Microsoft. Extensions. host](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) do projektu.</span><span class="sxs-lookup"><span data-stu-id="f323e-118">Add the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package to the project.</span></span>

## <a name="add-interfaces"></a><span data-ttu-id="f323e-119">Dodaj interfejsy</span><span class="sxs-lookup"><span data-stu-id="f323e-119">Add interfaces</span></span>

<span data-ttu-id="f323e-120">Dodaj następujące interfejsy do katalogu głównego projektu:</span><span class="sxs-lookup"><span data-stu-id="f323e-120">Add the following interfaces to the project root directory:</span></span>

<span data-ttu-id="f323e-121">*IOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="f323e-121">*IOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

<span data-ttu-id="f323e-122">`IOperation`Interfejs definiuje pojedynczą `OperationId` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="f323e-122">The `IOperation` interface defines a single `OperationId` property.</span></span>

<span data-ttu-id="f323e-123">*ITransientOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="f323e-123">*ITransientOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::

<span data-ttu-id="f323e-124">*IScopedOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="f323e-124">*IScopedOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::

<span data-ttu-id="f323e-125">*ISingletonOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="f323e-125">*ISingletonOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::

<span data-ttu-id="f323e-126">Wszystkie podinterfejsy `IOperation` nazwy mają swój przewidziany okres istnienia usługi.</span><span class="sxs-lookup"><span data-stu-id="f323e-126">All of the subinterfaces of `IOperation` name their intended service lifetime.</span></span> <span data-ttu-id="f323e-127">Na przykład "przejściowe" lub "pojedyncze".</span><span class="sxs-lookup"><span data-stu-id="f323e-127">For example, "Transient" or "Singleton".</span></span>

## <a name="add-default-implementation"></a><span data-ttu-id="f323e-128">Dodaj implementację domyślną</span><span class="sxs-lookup"><span data-stu-id="f323e-128">Add default implementation</span></span>

<span data-ttu-id="f323e-129">Dodaj następującą implementację domyślną dla różnych operacji:</span><span class="sxs-lookup"><span data-stu-id="f323e-129">Add the following default implementation for the various operations:</span></span>

<span data-ttu-id="f323e-130">*DefaultOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="f323e-130">*DefaultOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

<span data-ttu-id="f323e-131">`DefaultOperation`Implementuje wszystkie interfejsy nazwanego/znacznika i inicjuje `OperationId` Właściwość dla ostatnich czterech znaków nowego unikatowego identyfikatora globalnego (GUID).</span><span class="sxs-lookup"><span data-stu-id="f323e-131">The `DefaultOperation` implements all of the named/marker interfaces and initializes the `OperationId` property to the last four characters of a new globally unique identifier (GUID).</span></span>

## <a name="add-service-that-requires-di"></a><span data-ttu-id="f323e-132">Dodaj usługę wymagającą DI</span><span class="sxs-lookup"><span data-stu-id="f323e-132">Add service that requires DI</span></span>

<span data-ttu-id="f323e-133">Dodaj następujący obiekt rejestratora operacji, który działa jako usługa dla aplikacji konsolowej:</span><span class="sxs-lookup"><span data-stu-id="f323e-133">Add the following operation logger object, which acts as a service to your console application:</span></span>

<span data-ttu-id="f323e-134">*OperationLogger.cs*</span><span class="sxs-lookup"><span data-stu-id="f323e-134">*OperationLogger.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

<span data-ttu-id="f323e-135">`OperationLogger`Definiuje konstruktora, który wymaga każdego z powyższych interfejsów znacznika, czyli,, `ITransientOperation` `IScopedOperation` i `ISingletonOperation` .</span><span class="sxs-lookup"><span data-stu-id="f323e-135">The `OperationLogger` defines a constructor that requires each of the aforementioned marker interfaces, that is; `ITransientOperation`, `IScopedOperation`, and `ISingletonOperation`.</span></span> <span data-ttu-id="f323e-136">Obiekt ujawnia pojedynczą metodę, która umożliwia konsumentowi zarejestrowanie operacji przy użyciu danego `scope` parametru.</span><span class="sxs-lookup"><span data-stu-id="f323e-136">The object exposes a single method that allows the consumer to log the operations with a given `scope` parameter.</span></span> <span data-ttu-id="f323e-137">Po wywołaniu `LogOperations` Metoda będzie rejestrować unikatowy identyfikator każdej operacji z ciągiem zakresu i komunikatem.</span><span class="sxs-lookup"><span data-stu-id="f323e-137">When invoked, the `LogOperations` method will log each operation's unique identifier with the scope string and message.</span></span>

## <a name="register-services-for-di"></a><span data-ttu-id="f323e-138">Zarejestruj usługi dla DI</span><span class="sxs-lookup"><span data-stu-id="f323e-138">Register services for DI</span></span>

<span data-ttu-id="f323e-139">Na koniec Zaktualizuj plik *program.cs* tak, aby był zgodny z następującymi:</span><span class="sxs-lookup"><span data-stu-id="f323e-139">Finally, update the *Program.cs* file to match following:</span></span>

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

<span data-ttu-id="f323e-140">Aplikacja:</span><span class="sxs-lookup"><span data-stu-id="f323e-140">The application:</span></span>

- <span data-ttu-id="f323e-141">Tworzy <xref:Microsoft.Extensions.Hosting.IHostBuilder> wystąpienie z [domyślnymi ustawieniami spinacza](generic-host.md#default-builder-settings).</span><span class="sxs-lookup"><span data-stu-id="f323e-141">Creates an <xref:Microsoft.Extensions.Hosting.IHostBuilder> instance with the [default binder settings](generic-host.md#default-builder-settings).</span></span>
- <span data-ttu-id="f323e-142">Konfiguruje usługi i dodaje je wraz z odpowiednim okresem istnienia usługi.</span><span class="sxs-lookup"><span data-stu-id="f323e-142">Configures services and adds them with their corresponding service lifetime.</span></span>
- <span data-ttu-id="f323e-143">Wywołuje <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> i przypisuje wystąpienie elementu <xref:Microsoft.Extensions.Hosting.IHost> .</span><span class="sxs-lookup"><span data-stu-id="f323e-143">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> and assigns an instance of <xref:Microsoft.Extensions.Hosting.IHost>.</span></span>
- <span data-ttu-id="f323e-144">Wywołania `ExemplifyScoping` , przekazywanie w <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f323e-144">Calls `ExemplifyScoping`, passing in the <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.</span></span>

## <a name="conclusion"></a><span data-ttu-id="f323e-145">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="f323e-145">Conclusion</span></span>

<span data-ttu-id="f323e-146">Aplikacja generuje dane wyjściowe podobne do następującego przykładu:</span><span class="sxs-lookup"><span data-stu-id="f323e-146">The application produces output similar to the following example:</span></span>

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

<span data-ttu-id="f323e-147">W danych wyjściowych aplikacji można zobaczyć, że:</span><span class="sxs-lookup"><span data-stu-id="f323e-147">From the application output, you can see that:</span></span>

- <span data-ttu-id="f323e-148">Operacje przejściowe są zawsze różne, co oznacza, że nowe wystąpienie jest tworzone przy każdym pobieraniu usługi.</span><span class="sxs-lookup"><span data-stu-id="f323e-148">Transient operations are always different, meaning a new instance is created with every retrieval of the service.</span></span>
- <span data-ttu-id="f323e-149">Operacje w zakresie zmieniają się tylko z nowym zakresem, ale są tego samego wystąpienia w zakresie.</span><span class="sxs-lookup"><span data-stu-id="f323e-149">Scoped operations change only with a new scope, but are the same instance within a scope.</span></span>
- <span data-ttu-id="f323e-150">Operacje pojedyncze są zawsze takie same, co oznacza, że nowe wystąpienie jest tworzone tylko raz.</span><span class="sxs-lookup"><span data-stu-id="f323e-150">Singleton operations are always the same, meaning a new instance is only created once.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f323e-151">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="f323e-151">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f323e-152">Wskazówki dotyczące iniekcji zależności</span><span class="sxs-lookup"><span data-stu-id="f323e-152">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
