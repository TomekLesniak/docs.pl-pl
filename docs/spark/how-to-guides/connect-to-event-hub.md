---
title: Połącz platformę .NET dla Apache Spark z platformą Azure Event Hubs
description: Dowiedz się, jak nawiązać połączenie z usługą Azure Event Hub z lokalnego programu .NET for Apache Spark instance.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: c8fd10992e63674032af4148e0673a5330d9086c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223961"
---
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a>Połącz platformę .NET dla Apache Spark z platformą Azure Event Hubs

W tym artykule dowiesz się, jak połączyć aplikację [.net for Apache Spark](https://github.com/dotnet/spark) z usługą Azure Event Hubs, aby odczytywać i zapisywać strumienie Apache Kafka.

## <a name="prerequisites"></a>Wymagania wstępne

Przygotuj Event Hubs przestrzeń nazw z centrum zdarzeń. Aby zapoznać się z przewodnikiem krok po kroku, zobacz [Szybki Start: tworzenie centrum zdarzeń przy użyciu Azure Portal](/azure/event-hubs/event-hubs-create). Pamiętaj, aby wybrać warstwę cenową standardowa podczas tworzenia przestrzeni nazw centrum zdarzeń.

## <a name="what-is-azure-event-hubs"></a>Co to jest usługa Azure Event Hubs?

[Azure Event Hubs](/azure/event-hubs/event-hubs-about) to platforma przesyłania strumieniowego i usługa pozyskiwania zdarzeń. Jest to w pełni zarządzana platforma jako usługa (PaaS), którą można łatwo zintegrować z [Apache Kafka](https://kafka.apache.org/) , aby zapewnić obsługę PaaS Kafka bez konieczności zarządzania, konfigurowania lub uruchamiania własnych klastrów.

## <a name="connect-your-application-to-azure-event-hubs"></a>Łączenie aplikacji z platformą Azure Event Hubs

1. Pobierz parametry połączenia usługi Event Hubs i w pełni kwalifikowaną nazwę domeny (FQDN) w celu późniejszego użycia. Aby uzyskać instrukcje, zobacz [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Pobieranie parametrów połączenia usługi Event Hubs).
2. Ustaw następujące konfiguracje ze szczegółami z przestrzeni nazw w kodzie, aby rozpocząć odczytywanie z Event Hubs dla Kafka:
    1. Zaktualizuj **BOOTSTRAP_SERVERS** i **EH_SASL** w aplikacji, takie jak:

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a>Odczytaj ze strumienia centrum zdarzeń platformy Azure

Teraz można rozpocząć przesyłanie strumieniowe za pomocą Event Hubs tak jak w przypadku Kafka. Przykładowy kod, jak pokazano poniżej:

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

## <a name="write-to-azure-event-hub-stream"></a>Zapisz w strumieniu centrum zdarzeń platformy Azure

Możesz również pisać do Event Hubs w taki sam sposób, jak pokazano poniżej:

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

## <a name="run-your-application"></a>Uruchamianie aplikacji

Aby uruchomić platformę .NET dla aplikacji Apache Spark, zdefiniuj `spark-sql-kafka-0-10` moduł jako część definicji kompilacji w projekcie platformy Spark, używając `libraryDependency` w tym `build.sbt` celu projektów SBT. W przypadku środowisk Spark, takich jak `spark-submit` (lub `spark-shell` ), użyj `--packages` opcji wiersza polecenia, takiej jak:

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> Upewnij się, że dołączasz wersję pakietu zgodnie z uruchomioną wersją platformy Spark.
