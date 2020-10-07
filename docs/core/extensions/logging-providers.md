---
title: Dostawcy rejestrowania w programie .NET
description: Dowiedz się, w jaki sposób interfejs API dostawcy rejestrowania jest używany w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/25/2020
ms.openlocfilehash: 4d4658b7ca892d101af32f5cf8ac48a4beabfb92
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804755"
---
# <a name="logging-providers-in-net"></a><span data-ttu-id="b9611-103">Dostawcy rejestrowania w programie .NET</span><span class="sxs-lookup"><span data-stu-id="b9611-103">Logging providers in .NET</span></span>

<span data-ttu-id="b9611-104">Dostawcy rejestrowania utrwalają dzienniki, z wyjątkiem `Console` dostawcy, które wyświetlają tylko dzienniki jako dane wyjściowe Standard.</span><span class="sxs-lookup"><span data-stu-id="b9611-104">Logging providers persist logs, except for the `Console` provider, which only displays logs as standard output.</span></span> <span data-ttu-id="b9611-105">Na przykład dostawca usługi Azure Application Insights przechowuje dzienniki w usłudze Azure Application Insights.</span><span class="sxs-lookup"><span data-stu-id="b9611-105">For example, the Azure Application Insights provider stores logs in Azure Application Insights.</span></span> <span data-ttu-id="b9611-106">Można włączyć wielu dostawców.</span><span class="sxs-lookup"><span data-stu-id="b9611-106">Multiple providers can be enabled.</span></span>

<span data-ttu-id="b9611-107">Domyślne szablony aplikacji programu .NET Worker:</span><span class="sxs-lookup"><span data-stu-id="b9611-107">The default .NET Worker app templates:</span></span>

- <span data-ttu-id="b9611-108">Użyj [hosta ogólnego](generic-host.md).</span><span class="sxs-lookup"><span data-stu-id="b9611-108">Use the [Generic Host](generic-host.md).</span></span>
- <span data-ttu-id="b9611-109">Wywołanie <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> , które dodaje następujących dostawców rejestrowania:</span><span class="sxs-lookup"><span data-stu-id="b9611-109">Call <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>, which adds the following logging providers:</span></span>
  - [<span data-ttu-id="b9611-110">Konsola</span><span class="sxs-lookup"><span data-stu-id="b9611-110">Console</span></span>](#console)
  - [<span data-ttu-id="b9611-111">Rozpocząć</span><span class="sxs-lookup"><span data-stu-id="b9611-111">Debug</span></span>](#debug)
  - [<span data-ttu-id="b9611-112">EventSource</span><span class="sxs-lookup"><span data-stu-id="b9611-112">EventSource</span></span>](#event-source)
  - <span data-ttu-id="b9611-113">[EventLog](#windows-eventlog): tylko system Windows</span><span class="sxs-lookup"><span data-stu-id="b9611-113">[EventLog](#windows-eventlog): Windows only</span></span>

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="12":::

<span data-ttu-id="b9611-114">Poprzedni kod przedstawia `Program` klasę utworzoną za pomocą szablonów aplikacji roboczych platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b9611-114">The preceding code shows the `Program` class created with the .NET Worker app templates.</span></span> <span data-ttu-id="b9611-115">W następnych sekcjach przedstawiono przykłady na podstawie szablonów aplikacji procesów roboczych platformy .NET, które korzystają z hosta ogólnego.</span><span class="sxs-lookup"><span data-stu-id="b9611-115">The next several sections provide samples based on the .NET Worker app templates, which use the Generic Host.</span></span>

<span data-ttu-id="b9611-116">Aby zastąpić domyślny zestaw dostawców rejestrowania dodanych przez `Host.CreateDefaultBuilder` , wywołaj `ClearProviders` i Dodaj żądanych dostawców rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="b9611-116">To override the default set of logging providers added by `Host.CreateDefaultBuilder`, call `ClearProviders` and add the logging providers you want.</span></span> <span data-ttu-id="b9611-117">Na przykład następujący kod:</span><span class="sxs-lookup"><span data-stu-id="b9611-117">For example, the following code:</span></span>

- <span data-ttu-id="b9611-118">Wywołuje, <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A> Aby usunąć wszystkie <xref:Microsoft.Extensions.Logging.ILoggerProvider> wystąpienia z konstruktora.</span><span class="sxs-lookup"><span data-stu-id="b9611-118">Calls <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A> to remove all the <xref:Microsoft.Extensions.Logging.ILoggerProvider> instances from the builder.</span></span>
- <span data-ttu-id="b9611-119">Dodaje dostawcę rejestrowania [konsoli](#console) .</span><span class="sxs-lookup"><span data-stu-id="b9611-119">Adds the [Console](#console) logging provider.</span></span>

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureLogging(logging =>
        {
            logging.ClearProviders();
            logging.AddConsole();
        });
```

<span data-ttu-id="b9611-120">Aby uzyskać dodatkowych dostawców, zobacz:</span><span class="sxs-lookup"><span data-stu-id="b9611-120">For additional providers, see:</span></span>

- <span data-ttu-id="b9611-121">[Wbudowani dostawcy rejestrowania](#built-in-logging-providers).</span><span class="sxs-lookup"><span data-stu-id="b9611-121">[Built-in logging providers](#built-in-logging-providers).</span></span>
- <span data-ttu-id="b9611-122">[Dostawcy rejestrowania innych firm](#third-party-logging-providers).</span><span class="sxs-lookup"><span data-stu-id="b9611-122">[Third-party logging providers](#third-party-logging-providers).</span></span>

## <a name="configure-a-service-that-depends-on-ilogger"></a><span data-ttu-id="b9611-123">Konfigurowanie usługi, która zależy od ILogger</span><span class="sxs-lookup"><span data-stu-id="b9611-123">Configure a service that depends on ILogger</span></span>

<span data-ttu-id="b9611-124">Aby skonfigurować usługę, która jest zależna od `ILogger<T>` programu, należy użyć iniekcji konstruktora lub dostarczyć metody fabryki.</span><span class="sxs-lookup"><span data-stu-id="b9611-124">To configure a service that depends on `ILogger<T>`, use constructor injection or provide a factory method.</span></span> <span data-ttu-id="b9611-125">Podejście metody fabryki jest zalecane tylko wtedy, gdy nie ma żadnych innych opcji.</span><span class="sxs-lookup"><span data-stu-id="b9611-125">The factory method approach is recommended only if there is no other option.</span></span> <span data-ttu-id="b9611-126">Rozważmy na przykład usługę, która wymaga `ILogger<T>` wystąpienia przez di:</span><span class="sxs-lookup"><span data-stu-id="b9611-126">For example, consider a service that needs an `ILogger<T>` instance provided by DI:</span></span>

```csharp
.ConfigureServices(services =>
    services.AddSingleton<IExampleService>(container =>
        new DefaultExampleService
        {
            Logger = container.GetRequiredService<ILogger<IExampleService>>()
        }));
```

<span data-ttu-id="b9611-127">Poprzedzający kod to [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2) , który jest uruchamiany po raz pierwszy, należy utworzyć wystąpienie `IExampleService` .</span><span class="sxs-lookup"><span data-stu-id="b9611-127">The preceding code is a [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2) that runs the first time the DI container needs to construct an instance of `IExampleService`.</span></span> <span data-ttu-id="b9611-128">W ten sposób można uzyskać dostęp do dowolnych zarejestrowanych usług.</span><span class="sxs-lookup"><span data-stu-id="b9611-128">You can access any of the registered services in this way.</span></span>

## <a name="built-in-logging-providers"></a><span data-ttu-id="b9611-129">Wbudowani dostawcy rejestrowania</span><span class="sxs-lookup"><span data-stu-id="b9611-129">Built-in logging providers</span></span>

<span data-ttu-id="b9611-130">Rozszerzenia firmy Microsoft obejmują następujących dostawców rejestrowania w ramach bibliotek środowiska uruchomieniowego:</span><span class="sxs-lookup"><span data-stu-id="b9611-130">Microsoft Extensions include the following logging providers as part of the runtime libraries:</span></span>

- [<span data-ttu-id="b9611-131">Konsola</span><span class="sxs-lookup"><span data-stu-id="b9611-131">Console</span></span>](#console)
- [<span data-ttu-id="b9611-132">Rozpocząć</span><span class="sxs-lookup"><span data-stu-id="b9611-132">Debug</span></span>](#debug)
- [<span data-ttu-id="b9611-133">EventSource</span><span class="sxs-lookup"><span data-stu-id="b9611-133">EventSource</span></span>](#event-source)
- [<span data-ttu-id="b9611-134">Elemencie</span><span class="sxs-lookup"><span data-stu-id="b9611-134">EventLog</span></span>](#windows-eventlog)

<span data-ttu-id="b9611-135">Następujący dostawcy rejestrowania są dostarczani przez firmę Microsoft, ale nie jako część bibliotek środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="b9611-135">The following logging providers are shipped by Microsoft, but not as part of the runtime libraries.</span></span> <span data-ttu-id="b9611-136">Muszą być zainstalowane jako dodatkowe pakiety NuGet.</span><span class="sxs-lookup"><span data-stu-id="b9611-136">They must be installed as additional NuGet packages.</span></span>

- [<span data-ttu-id="b9611-137">AzureAppServicesFile i AzureAppServicesBlob</span><span class="sxs-lookup"><span data-stu-id="b9611-137">AzureAppServicesFile and AzureAppServicesBlob</span></span>](#azure-app-service)
- [<span data-ttu-id="b9611-138">ApplicationInsights</span><span class="sxs-lookup"><span data-stu-id="b9611-138">ApplicationInsights</span></span>](#azure-application-insights)

### <a name="console"></a><span data-ttu-id="b9611-139">Konsola</span><span class="sxs-lookup"><span data-stu-id="b9611-139">Console</span></span>

<span data-ttu-id="b9611-140">`Console`Dostawca rejestruje dane wyjściowe w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="b9611-140">The `Console` provider logs output to the console.</span></span>

### <a name="debug"></a><span data-ttu-id="b9611-141">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="b9611-141">Debug</span></span>

<span data-ttu-id="b9611-142">`Debug`Dostawca zapisuje dane wyjściowe dziennika za pomocą klasy [System. Diagnostics. Debug](/dotnet/api/system.diagnostics.debug) .</span><span class="sxs-lookup"><span data-stu-id="b9611-142">The `Debug` provider writes log output by using the [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug) class.</span></span> <span data-ttu-id="b9611-143">Wywołania do `System.Diagnostics.Debug.WriteLine` zapisu dla `Debug` dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b9611-143">Calls to `System.Diagnostics.Debug.WriteLine` write to the `Debug` provider.</span></span>

<span data-ttu-id="b9611-144">W systemie Linux `Debug` Lokalizacja dziennika dostawcy jest zależna od dystrybucji i może być jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="b9611-144">On Linux, the `Debug` provider log location is distribution-dependent and may be one of the following:</span></span>

- <span data-ttu-id="b9611-145">*/var/log/message*</span><span class="sxs-lookup"><span data-stu-id="b9611-145">*/var/log/message*</span></span>
- <span data-ttu-id="b9611-146">*/var/log/syslog*</span><span class="sxs-lookup"><span data-stu-id="b9611-146">*/var/log/syslog*</span></span>

### <a name="event-source"></a><span data-ttu-id="b9611-147">Źródło zdarzeń</span><span class="sxs-lookup"><span data-stu-id="b9611-147">Event Source</span></span>

<span data-ttu-id="b9611-148">`EventSource`Dostawca zapisuje do międzyplatformowego źródła zdarzeń o nazwie `Microsoft-Extensions-Logging` .</span><span class="sxs-lookup"><span data-stu-id="b9611-148">The `EventSource` provider writes to a cross-platform event source with the name `Microsoft-Extensions-Logging`.</span></span> <span data-ttu-id="b9611-149">W systemie Windows Dostawca używa [funkcji ETW](/windows/win32/etw/event-tracing-portal).</span><span class="sxs-lookup"><span data-stu-id="b9611-149">On Windows, the provider uses [ETW](/windows/win32/etw/event-tracing-portal).</span></span>

#### <a name="dotnet-trace-tooling"></a><span data-ttu-id="b9611-150">narzędzia śledzenia dotnet</span><span class="sxs-lookup"><span data-stu-id="b9611-150">dotnet trace tooling</span></span>

<span data-ttu-id="b9611-151">Narzędzie do [śledzenia dotnet](../diagnostics/dotnet-trace.md) to międzyplatformowe narzędzie globalne interfejsu wiersza polecenia, które umożliwia zbieranie śladów programu .NET Core uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="b9611-151">The [dotnet-trace](../diagnostics/dotnet-trace.md) tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process.</span></span> <span data-ttu-id="b9611-152">Narzędzie zbiera <xref:Microsoft.Extensions.Logging.EventSource> dane dostawcy za pomocą <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource> .</span><span class="sxs-lookup"><span data-stu-id="b9611-152">The tool collects <xref:Microsoft.Extensions.Logging.EventSource> provider data using a <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>.</span></span>

<span data-ttu-id="b9611-153">Aby uzyskać instrukcje dotyczące instalacji, zobacz [dotnet-Trace](../diagnostics/dotnet-trace.md) .</span><span class="sxs-lookup"><span data-stu-id="b9611-153">See [dotnet-trace](../diagnostics/dotnet-trace.md) for installation instructions.</span></span> <span data-ttu-id="b9611-154">Aby zapoznać się z samouczkiem diagnostycznym korzystającym z programu `dotnet-trace` , zobacz [debugowanie wysokiego użycia procesora CPU w programie .NET Core](../diagnostics/debug-highcpu.md).</span><span class="sxs-lookup"><span data-stu-id="b9611-154">For a diagnostic tutorial using `dotnet-trace`, see [Debug high CPU usage in .NET Core](../diagnostics/debug-highcpu.md).</span></span>

### <a name="windows-eventlog"></a><span data-ttu-id="b9611-155">Dziennik zdarzeń systemu Windows</span><span class="sxs-lookup"><span data-stu-id="b9611-155">Windows EventLog</span></span>

<span data-ttu-id="b9611-156">`EventLog`Dostawca wysyła dane wyjściowe dziennika do dziennika zdarzeń systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="b9611-156">The `EventLog` provider sends log output to the Windows Event Log.</span></span> <span data-ttu-id="b9611-157">W przeciwieństwie do innych dostawców `EventLog` dostawca nie dziedziczy ***not*** domyślnych ustawień nienależących do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b9611-157">Unlike the other providers, the `EventLog` provider does ***not*** inherit the default non-provider settings.</span></span> <span data-ttu-id="b9611-158">Jeśli `EventLog` nie określono ustawień dziennika, domyślnie są one `LogLevel.Warning` .</span><span class="sxs-lookup"><span data-stu-id="b9611-158">If `EventLog` log settings aren't specified, they default to `LogLevel.Warning`.</span></span>

<span data-ttu-id="b9611-159">Aby rejestrować zdarzenia mniejsze niż <xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType> , jawnie ustaw poziom dziennika.</span><span class="sxs-lookup"><span data-stu-id="b9611-159">To log events lower than <xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType>, explicitly set the log level.</span></span> <span data-ttu-id="b9611-160">Poniższy przykład ustawia domyślny poziom dziennika dziennika zdarzeń <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="b9611-160">The following example sets the Event Log default log level to <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>:</span></span>

```json
"Logging": {
  "EventLog": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

<span data-ttu-id="b9611-161">[Przeciążania addeventlog](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions) można przekazać <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings> .</span><span class="sxs-lookup"><span data-stu-id="b9611-161">[AddEventLog overloads](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions) can pass in <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>.</span></span> <span data-ttu-id="b9611-162">Jeśli `null` lub nie zostanie określony, są używane następujące ustawienia domyślne:</span><span class="sxs-lookup"><span data-stu-id="b9611-162">If `null` or not specified, the following default settings are used:</span></span>

- <span data-ttu-id="b9611-163">`LogName`: "Aplikacja"</span><span class="sxs-lookup"><span data-stu-id="b9611-163">`LogName`: "Application"</span></span>
- <span data-ttu-id="b9611-164">`SourceName`: "Środowisko uruchomieniowe platformy .NET"</span><span class="sxs-lookup"><span data-stu-id="b9611-164">`SourceName`: ".NET Runtime"</span></span>
- <span data-ttu-id="b9611-165">`MachineName`: Nazwa komputera lokalnego jest używana.</span><span class="sxs-lookup"><span data-stu-id="b9611-165">`MachineName`: The local machine name is used.</span></span>

<span data-ttu-id="b9611-166">Poniższy kod zmienia `SourceName` wartość domyślną na `".NET Runtime"` `CustomLogs` :</span><span class="sxs-lookup"><span data-stu-id="b9611-166">The following code changes the `SourceName` from the default value of `".NET Runtime"` to `CustomLogs`:</span></span>

```csharp
public class Program
{
    public static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddEventLog(configuration =>
                    configuration.SourceName = "CustomLogs"));
}
```

### <a name="azure-app-service"></a><span data-ttu-id="b9611-167">Azure App Service</span><span class="sxs-lookup"><span data-stu-id="b9611-167">Azure App Service</span></span>

<span data-ttu-id="b9611-168">Pakiet [Microsoft. Extensions. Logging. AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) Provider zapisuje dzienniki w plikach tekstowych w systemie plików aplikacji Azure App Service i w usłudze [BLOB Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage) na koncie usługi Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="b9611-168">The [Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) provider package writes logs to text files in an Azure App Service app's file system and to [blob storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage) in an Azure Storage account.</span></span>

<span data-ttu-id="b9611-169">Pakiet dostawcy nie jest uwzględniony w bibliotekach środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="b9611-169">The provider package isn't included in the runtime libraries.</span></span> <span data-ttu-id="b9611-170">Aby użyć dostawcy, Dodaj pakiet dostawcy do projektu.</span><span class="sxs-lookup"><span data-stu-id="b9611-170">To use the provider, add the provider package to the project.</span></span>

<span data-ttu-id="b9611-171">Aby skonfigurować ustawienia dostawcy, użyj <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> i <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions> , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="b9611-171">To configure provider settings, use <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> and <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>, as shown in the following example:</span></span>

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddAzureWebAppDiagnostics())
            .ConfigureServices(services =>
                services.Configure<AzureFileLoggerOptions>(options =>
                {
                    options.FileName = "azure-diagnostics-";
                    options.FileSizeLimit = 50 * 1024;
                    options.RetainedFileCountLimit = 5;
                })
                .Configure<AzureBlobLoggerOptions>(options =>
                {
                    options.BlobName = "log.txt";
                }));
}
```

<span data-ttu-id="b9611-172">Po wdrożeniu do Azure App Service aplikacja korzysta z ustawień w sekcji [dzienniki App Service](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) na stronie **App Service** Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="b9611-172">When deployed to Azure App Service, the app uses the settings in the [App Service logs](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) section of the **App Service** page of the Azure portal.</span></span> <span data-ttu-id="b9611-173">Po zaktualizowaniu następujących ustawień zmiany zaczynają obowiązywać natychmiast, bez konieczności ponownego uruchomienia lub ponownej wdrożenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b9611-173">When the following settings are updated, the changes take effect immediately without requiring a restart or redeployment of the app.</span></span>

- <span data-ttu-id="b9611-174">**Rejestrowanie aplikacji (system plików)**</span><span class="sxs-lookup"><span data-stu-id="b9611-174">**Application Logging (Filesystem)**</span></span>
- <span data-ttu-id="b9611-175">**Rejestrowanie aplikacji (BLOB)**</span><span class="sxs-lookup"><span data-stu-id="b9611-175">**Application Logging (Blob)**</span></span>

<span data-ttu-id="b9611-176">Domyślną lokalizacją plików dziennika jest folder *D: \\ Home \\ \\ LogFiles* , a domyślna nazwa pliku to *diagnostics-yyyymmdd.txt*.</span><span class="sxs-lookup"><span data-stu-id="b9611-176">The default location for log files is in the *D:\\home\\LogFiles\\Application* folder, and the default file name is *diagnostics-yyyymmdd.txt*.</span></span> <span data-ttu-id="b9611-177">Domyślny limit rozmiaru pliku wynosi 10 MB, a domyślna maksymalna liczba zachowywanych plików to 2.</span><span class="sxs-lookup"><span data-stu-id="b9611-177">The default file size limit is 10 MB, and the default maximum number of files retained is 2.</span></span> <span data-ttu-id="b9611-178">Domyślną nazwą obiektu BLOB jest *{App-Name} {timestamp}/yyyy/mm/dd/hh/{guid} -applicationLog.txt*.</span><span class="sxs-lookup"><span data-stu-id="b9611-178">The default blob name is *{app-name}{timestamp}/yyyy/mm/dd/hh/{guid}-applicationLog.txt*.</span></span>

<span data-ttu-id="b9611-179">Ten dostawca rejestruje się tylko wtedy, gdy projekt jest uruchomiony w środowisku platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="b9611-179">This provider only logs when the project runs in the Azure environment.</span></span>

#### <a name="azure-log-streaming"></a><span data-ttu-id="b9611-180">Przesyłanie strumieniowe dzienników Azure</span><span class="sxs-lookup"><span data-stu-id="b9611-180">Azure log streaming</span></span>

<span data-ttu-id="b9611-181">Przesyłanie strumieniowe w usłudze Azure log obsługuje wyświetlanie dziennika w czasie rzeczywistym z:</span><span class="sxs-lookup"><span data-stu-id="b9611-181">Azure log streaming supports viewing log activity in real time from:</span></span>

- <span data-ttu-id="b9611-182">Serwer aplikacji</span><span class="sxs-lookup"><span data-stu-id="b9611-182">The app server</span></span>
- <span data-ttu-id="b9611-183">Serwer sieci Web</span><span class="sxs-lookup"><span data-stu-id="b9611-183">The web server</span></span>
- <span data-ttu-id="b9611-184">Śledzenie nieudanych żądań</span><span class="sxs-lookup"><span data-stu-id="b9611-184">Failed request tracing</span></span>

<span data-ttu-id="b9611-185">Aby skonfigurować przesyłanie strumieniowe dzienników Azure:</span><span class="sxs-lookup"><span data-stu-id="b9611-185">To configure Azure log streaming:</span></span>

- <span data-ttu-id="b9611-186">Przejdź do strony **dzienników App Service** ze strony portalu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b9611-186">Navigate to the **App Service logs** page from the app's portal page.</span></span>
- <span data-ttu-id="b9611-187">Ustaw **Rejestrowanie aplikacji (system plików)** na **włączone**.</span><span class="sxs-lookup"><span data-stu-id="b9611-187">Set **Application Logging (Filesystem)** to **On**.</span></span>
- <span data-ttu-id="b9611-188">Wybierz **poziom**dziennika.</span><span class="sxs-lookup"><span data-stu-id="b9611-188">Choose the log **Level**.</span></span> <span data-ttu-id="b9611-189">To ustawienie dotyczy tylko przesyłania strumieniowego dzienników Azure.</span><span class="sxs-lookup"><span data-stu-id="b9611-189">This setting only applies to Azure log streaming.</span></span>

<span data-ttu-id="b9611-190">Przejdź do strony **strumień dziennika** , aby wyświetlić dzienniki.</span><span class="sxs-lookup"><span data-stu-id="b9611-190">Navigate to the **Log Stream** page to view logs.</span></span> <span data-ttu-id="b9611-191">Zarejestrowane komunikaty są rejestrowane przy użyciu `ILogger` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="b9611-191">The logged messages are logged with the `ILogger` interface.</span></span>

### <a name="azure-application-insights"></a><span data-ttu-id="b9611-192">Azure Application Insights</span><span class="sxs-lookup"><span data-stu-id="b9611-192">Azure Application Insights</span></span>

<span data-ttu-id="b9611-193">Pakiet [Microsoft. Extensions. Logging. ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) Provider zapisuje dzienniki na [platformie Azure Application Insights](/azure/azure-monitor/app/cloudservices).</span><span class="sxs-lookup"><span data-stu-id="b9611-193">The [Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) provider package writes logs to [Azure Application Insights](/azure/azure-monitor/app/cloudservices).</span></span> <span data-ttu-id="b9611-194">Application Insights to usługa, która monitoruje aplikację internetową i udostępnia narzędzia do wykonywania zapytań i analizowania danych telemetrycznych.</span><span class="sxs-lookup"><span data-stu-id="b9611-194">Application Insights is a service that monitors a web app and provides tools for querying and analyzing the telemetry data.</span></span> <span data-ttu-id="b9611-195">Jeśli używasz tego dostawcy, możesz wysyłać zapytania i analizować dzienniki przy użyciu narzędzi Application Insights.</span><span class="sxs-lookup"><span data-stu-id="b9611-195">If you use this provider, you can query and analyze your logs by using the Application Insights tools.</span></span>

<span data-ttu-id="b9611-196">Więcej informacji można znaleźć w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="b9611-196">For more information, see the following resources:</span></span>

- [<span data-ttu-id="b9611-197">Omówienie usługi Application Insights</span><span class="sxs-lookup"><span data-stu-id="b9611-197">Application Insights overview</span></span>](/azure/application-insights/app-insights-overview)
- <span data-ttu-id="b9611-198">[ApplicationInsightsLoggerProvider for .NET Core ILogger](/azure/azure-monitor/app/ilogger) — Rozpocznij tutaj, jeśli chcesz zaimplementować dostawcę rejestrowania bez pozostałej części telemetrii Application Insights.</span><span class="sxs-lookup"><span data-stu-id="b9611-198">[ApplicationInsightsLoggerProvider for .NET Core ILogger logs](/azure/azure-monitor/app/ilogger) - Start here if you want to implement the logging provider without the rest of Application Insights telemetry.</span></span>
- <span data-ttu-id="b9611-199">[Karty rejestrowania Application Insights](/azure/azure-monitor/app/asp-net-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="b9611-199">[Application Insights logging adapters](/azure/azure-monitor/app/asp-net-trace-logs).</span></span>
- <span data-ttu-id="b9611-200">[Zainstaluj, skonfiguruj i zainicjuj samouczek Application INSIGHTS SDK](/learn/modules/instrument-web-app-code-with-application-insights) — interaktywny w witrynie Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="b9611-200">[Install, configure, and initialize the Application Insights SDK](/learn/modules/instrument-web-app-code-with-application-insights) - Interactive tutorial on the Microsoft Learn site.</span></span>

## <a name="third-party-logging-providers"></a><span data-ttu-id="b9611-201">Dostawcy rejestrowania innych firm</span><span class="sxs-lookup"><span data-stu-id="b9611-201">Third-party logging providers</span></span>

<span data-ttu-id="b9611-202">Oto kilka platform rejestrowania innych firm, które współpracują z różnymi obciążeniami platformy .NET:</span><span class="sxs-lookup"><span data-stu-id="b9611-202">Here are some third-party logging frameworks that work with various .NET workloads:</span></span>

- <span data-ttu-id="b9611-203">[ELMAH.IO](https://elmah.io) ([repozytorium GitHub](https://github.com/elmahio/Elmah.Io.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="b9611-203">[elmah.io](https://elmah.io) ([GitHub repo](https://github.com/elmahio/Elmah.Io.Extensions.Logging))</span></span>
- <span data-ttu-id="b9611-204">[Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html) ([repozytorium GitHub](https://github.com/mattwcole/gelf-extensions-logging))</span><span class="sxs-lookup"><span data-stu-id="b9611-204">[Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html) ([GitHub repo](https://github.com/mattwcole/gelf-extensions-logging))</span></span>
- <span data-ttu-id="b9611-205">[JSNLog](http://jsnlog.com) ([repozytorium GitHub](https://github.com/mperdeck/jsnlog))</span><span class="sxs-lookup"><span data-stu-id="b9611-205">[JSNLog](http://jsnlog.com) ([GitHub repo](https://github.com/mperdeck/jsnlog))</span></span>
- <span data-ttu-id="b9611-206">[KissLog.NET](https://kisslog.net) ([repozytorium GitHub](https://github.com/catalingavan/KissLog-net))</span><span class="sxs-lookup"><span data-stu-id="b9611-206">[KissLog.net](https://kisslog.net) ([GitHub repo](https://github.com/catalingavan/KissLog-net))</span></span>
- <span data-ttu-id="b9611-207">[Log4Net](https://logging.apache.org/log4net) ([repozytorium GitHub](https://github.com/apache/logging-log4net))</span><span class="sxs-lookup"><span data-stu-id="b9611-207">[Log4Net](https://logging.apache.org/log4net) ([GitHub repo](https://github.com/apache/logging-log4net))</span></span>
- <span data-ttu-id="b9611-208">[Loggr](https://loggr.net) ([repozytorium GitHub](https://github.com/imobile3/Loggr.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="b9611-208">[Loggr](https://loggr.net) ([GitHub repo](https://github.com/imobile3/Loggr.Extensions.Logging))</span></span>
- <span data-ttu-id="b9611-209">[NLOG](https://nlog-project.org) ([repozytorium GitHub](https://github.com/NLog/NLog.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="b9611-209">[NLog](https://nlog-project.org) ([GitHub repo](https://github.com/NLog/NLog.Extensions.Logging))</span></span>
- <span data-ttu-id="b9611-210">[Sentry](https://sentry.io/welcome) ([repozytorium GitHub](https://github.com/getsentry/sentry-dotnet))</span><span class="sxs-lookup"><span data-stu-id="b9611-210">[Sentry](https://sentry.io/welcome) ([GitHub repo](https://github.com/getsentry/sentry-dotnet))</span></span>
- <span data-ttu-id="b9611-211">[Serilog](https://serilog.net) ([repozytorium GitHub](https://github.com/serilog/serilog-sinks-console))</span><span class="sxs-lookup"><span data-stu-id="b9611-211">[Serilog](https://serilog.net) ([GitHub repo](https://github.com/serilog/serilog-sinks-console))</span></span>
- <span data-ttu-id="b9611-212">[Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging) ([repozytorium GitHub](https://github.com/googleapis/google-cloud-dotnet))</span><span class="sxs-lookup"><span data-stu-id="b9611-212">[Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging) ([GitHub repo](https://github.com/googleapis/google-cloud-dotnet))</span></span>

<span data-ttu-id="b9611-213">Niektóre struktury innych firm mogą wykonywać [Rejestrowanie semantyczne, znane także jako rejestrowanie strukturalne](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging).</span><span class="sxs-lookup"><span data-stu-id="b9611-213">Some third-party frameworks can perform [semantic logging, also known as structured logging](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging).</span></span>

<span data-ttu-id="b9611-214">Korzystanie z struktury innej firmy jest podobne do korzystania z jednego z wbudowanych dostawców:</span><span class="sxs-lookup"><span data-stu-id="b9611-214">Using a third-party framework is similar to using one of the built-in providers:</span></span>

1. <span data-ttu-id="b9611-215">Dodaj pakiet NuGet do projektu.</span><span class="sxs-lookup"><span data-stu-id="b9611-215">Add a NuGet package to your project.</span></span>
1. <span data-ttu-id="b9611-216">Wywoływanie `ILoggerFactory` `ILoggingBuilder` metody rozszerzenia lub dostarczonej przez platformę rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="b9611-216">Call an `ILoggerFactory` or `ILoggingBuilder` extension method provided by the logging framework.</span></span>

<span data-ttu-id="b9611-217">Aby uzyskać więcej informacji, zobacz dokumentację każdego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b9611-217">For more information, see each provider's documentation.</span></span> <span data-ttu-id="b9611-218">Dostawcy rejestrowania innych firm nie są obsługiwani przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9611-218">Third-party logging providers aren't supported by Microsoft.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9611-219">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b9611-219">See also</span></span>

- <span data-ttu-id="b9611-220">[Rejestrowanie w programie .NET](logging.md).</span><span class="sxs-lookup"><span data-stu-id="b9611-220">[Logging in .NET](logging.md).</span></span>
- <span data-ttu-id="b9611-221">[Zaimplementuj niestandardowego dostawcę rejestrowania w programie .NET](custom-logging-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b9611-221">[Implement a custom logging provider in .NET](custom-logging-provider.md).</span></span>
- <span data-ttu-id="b9611-222">[Rejestrowanie o wysokiej wydajności w programie .NET](high-performance-logging.md).</span><span class="sxs-lookup"><span data-stu-id="b9611-222">[High-performance logging in .NET](high-performance-logging.md).</span></span>
