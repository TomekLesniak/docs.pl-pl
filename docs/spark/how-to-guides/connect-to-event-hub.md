---
title: Połącz platformę .NET dla Apache Spark z platformą Azure Event Hubs
description: Dowiedz się, jak nawiązać połączenie z usługą Azure Event Hub z lokalnego programu .NET for Apache Spark instance.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 3956a8152feb743f205f29334f0d42b3165cb27b
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877890"
---
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a><span data-ttu-id="9adca-103">Połącz platformę .NET dla Apache Spark z platformą Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="9adca-103">Connect .NET for Apache Spark to Azure Event Hubs</span></span>

<span data-ttu-id="9adca-104">W tym artykule dowiesz się, jak połączyć aplikację [.net for Apache Spark](https://github.com/dotnet/spark) z usługą Azure Event Hubs, aby odczytywać i zapisywać strumienie Apache Kafka.</span><span class="sxs-lookup"><span data-stu-id="9adca-104">In this article, you will learn how to connect your [.NET for Apache Spark](https://github.com/dotnet/spark) application with Azure Event Hubs to read and write Apache Kafka streams.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9adca-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="9adca-105">Prerequisites</span></span>

1. <span data-ttu-id="9adca-106">Zapoznaj się z centrum zdarzeń Event Hubs przestrzeni nazw, aby zapoznać się z [tym dokumentem](https://docs.microsoft.com/azure/event-hubs/event-hubs-create) , aby zapoznać się z przewodnikiem krok po kroku na temat tego, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="9adca-106">Have an Event Hubs Namespace ready with an event hub, refer to [this document](https://docs.microsoft.com/azure/event-hubs/event-hubs-create) for a step-by-step guide on how to do that.</span></span> <span data-ttu-id="9adca-107">Pamiętaj, aby wybrać warstwę cenową standardowa podczas tworzenia przestrzeni nazw centrum zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="9adca-107">Make sure to select the Standard Pricing tier while creating the Event Hub Namespace.</span></span>

## <a name="what-is-azure-event-hubs"></a><span data-ttu-id="9adca-108">Co to jest usługa Azure Event Hubs?</span><span class="sxs-lookup"><span data-stu-id="9adca-108">What is Azure Event Hubs</span></span>

<span data-ttu-id="9adca-109">[Azure Event Hubs](https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-about) to usługa pozyskiwania danych Big Data i usługi pozyskiwania zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="9adca-109">[Azure Event Hubs](https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-about) is a big data streaming platform and event ingestion service.</span></span> <span data-ttu-id="9adca-110">Jest to w pełni zarządzana platforma jako usługa (PaaS), którą można łatwo zintegrować z [Apache Kafka](https://kafka.apache.org/) , aby zapewnić środowisko PaaS Kafka, bez konieczności zarządzania, konfigurowania lub uruchamiania własnych klastrów.</span><span class="sxs-lookup"><span data-stu-id="9adca-110">It is a fully managed Platform-as-a-Service (PaaS), that can easily integrate with [Apache Kafka](https://kafka.apache.org/) to give you the PaaS Kafka experience without having to manage, configure or run your own clusters.</span></span>

## <a name="connect-your-application-to-azure-event-hubs"></a><span data-ttu-id="9adca-111">Łączenie aplikacji z platformą Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="9adca-111">Connect your application to Azure Event Hubs</span></span>

1. <span data-ttu-id="9adca-112">Pobierz parametry połączenia usługi Event Hubs i w pełni kwalifikowaną nazwę domeny (FQDN) w celu późniejszego użycia.</span><span class="sxs-lookup"><span data-stu-id="9adca-112">Get the Event Hubs connection string and fully qualified domain name (FQDN) for later use.</span></span> <span data-ttu-id="9adca-113">Aby uzyskać instrukcje, zobacz [Get an Event Hubs connection string](https://docs.microsoft.com/azure/event-hubs/event-hubs-get-connection-string) (Pobieranie parametrów połączenia usługi Event Hubs).</span><span class="sxs-lookup"><span data-stu-id="9adca-113">For instructions, see [Get an Event Hubs connection string](https://docs.microsoft.com/azure/event-hubs/event-hubs-get-connection-string).</span></span>
2. <span data-ttu-id="9adca-114">Ustaw następujące konfiguracje ze szczegółami z przestrzeni nazw w kodzie, aby rozpocząć odczytywanie z Event Hubs dla Kafka:</span><span class="sxs-lookup"><span data-stu-id="9adca-114">Set the following configurations with details from your namespace in your code to start reading from Event Hubs for Kafka:</span></span>
    1. <span data-ttu-id="9adca-115">Zaktualizuj **BOOTSTRAP_SERVERS** i **EH_SASL** w aplikacji, takie jak:</span><span class="sxs-lookup"><span data-stu-id="9adca-115">Update **BOOTSTRAP_SERVERS** and **EH_SASL** in your application like so:</span></span>

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a><span data-ttu-id="9adca-116">Odczytaj ze strumienia centrum zdarzeń platformy Azure</span><span class="sxs-lookup"><span data-stu-id="9adca-116">Read from Azure Event Hub stream</span></span>

<span data-ttu-id="9adca-117">Teraz można rozpocząć przesyłanie strumieniowe za pomocą Event Hubs tak jak w przypadku Kafka.</span><span class="sxs-lookup"><span data-stu-id="9adca-117">You can now start streaming with Event Hubs as you would with Kafka.</span></span> <span data-ttu-id="9adca-118">Przykładowy kod, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="9adca-118">Sample code as shown below:</span></span>

```csharp
SparkSession spark = SparkSession
    .Builder()
    .AppName("Connect Event Hub")
    .GetOrCreate();

DataFrame df = spark
    .ReadStream()
    .Format("kafka")
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("subscribe", "spark-test")
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("kafka.request.timeout.ms", "60000")
    .Option("kafka.session.timeout.ms", "60000")
    .Option("failOnDataLoss", "false")
    .Load();

DataFrame dfWrite = df
    .WriteStream()
    .OutputMode("append")
    .Format("console")
    .Start();
```

## <a name="write-to-azure-event-hub-stream"></a><span data-ttu-id="9adca-119">Zapisz w strumieniu centrum zdarzeń platformy Azure</span><span class="sxs-lookup"><span data-stu-id="9adca-119">Write to Azure Event Hub stream</span></span>

<span data-ttu-id="9adca-120">Możesz również pisać do Event Hubs w taki sam sposób, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="9adca-120">You can also write to Event Hubs in the same way, as shown below:</span></span>

```csharp
// df is the DataFrame to write

df.WriteStream()
    .Format("kafka")
    .Option("topic", topics)
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("checkpointLocation", "./checkpoint")
    .Start();
```

## <a name="run-your-application"></a><span data-ttu-id="9adca-121">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="9adca-121">Run your application</span></span>

<span data-ttu-id="9adca-122">Aby można było uruchomić aplikację .NET for Apache Spark, należy zdefiniować `spark-sql-kafka-0-10` moduł jako część definicji kompilacji w projekcie platformy Spark, używając `libraryDependency` w tym `build.sbt` celu projektów SBT.</span><span class="sxs-lookup"><span data-stu-id="9adca-122">In order to run your .NET for Apache Spark application, you should define the `spark-sql-kafka-0-10` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="9adca-123">W przypadku środowisk Spark, takich jak `spark-submit` (lub `spark-shell` ) należy użyć `--packages` opcji wiersza polecenia, takiej jak:</span><span class="sxs-lookup"><span data-stu-id="9adca-123">For Spark environments such as `spark-submit` (or `spark-shell`) you should use the `--packages` command-line option like so:</span></span>

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> <span data-ttu-id="9adca-124">Upewnij się, że dołączasz wersję pakietu zgodnie z uruchomioną wersją platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="9adca-124">Make sure to include the package version in accordance with the version of Spark being run.</span></span>
