---
title: Przesyłanie zadania platformy .NET dla Apache Spark do usługi Azure HDInsight
description: Dowiedz się, jak przesłać zadanie platformy .NET dla Apache Spark do usługi Azure HDInsight przy użyciu platformy Spark — przesyłanie i Apache usługi Livy.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 74be4ecf33a9a881633da0630fa1c1a4bf0b19c6
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688166"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Przesyłanie zadania platformy .NET dla Apache Spark do usługi Azure HDInsight

Istnieją dwa sposoby wdrażania zadania programu .NET dla Apache Spark w usłudze HDInsight: `spark-submit` i Apache usługi Livy.

## <a name="deploy-using-spark-submit"></a>Wdrażanie przy użyciu platformy Spark — przesyłanie

Możesz użyć polecenia [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) do przesyłania zadań programu .net dla Apache Spark do usługi Azure HDInsight.

1. Przejdź do klastra usługi HDInsight Spark w Azure Portal, a następnie wybierz pozycję **SSH + logowanie do klastra**.

2. Skopiuj informacje logowania SSH i wklej nazwę logowania do terminalu. Zaloguj się do klastra przy użyciu hasła ustawionego podczas tworzenia klastra. Powinny pojawić się komunikaty z powitaniem do Ubuntu i Spark.

3. Użyj polecenia **Spark-Submit** , aby uruchomić aplikację w klastrze usługi HDInsight. Pamiętaj **, aby zastąpić obiekt** **mojekontomagazynu** i go w przykładowym skrypcie z rzeczywistymi nazwami kontenera obiektów blob i konta magazynu. Pamiętaj również, aby zastąpić plik JAR Microsoft-Spark wersją platformy Spark i platformy .NET dla Apache Spark są używane.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Wdrażanie przy użyciu oprogramowania Apache usługi Livy

Aby przesłać Apache Spark zadań do klastra Azure HDInsight Spark, można użyć oprogramowania [Apache usługi Livy](https://livy.incubator.apache.org/), interfejsu API REST Apache Spark. Aby uzyskać więcej informacji, zobacz [zadania zdalne z Apache usługi Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).

Następujące polecenie można uruchomić w systemie Linux przy użyciu `curl` :

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Następne kroki

* [Wprowadzenie do platformy .NET dla Apache Spark](../tutorials/get-started.md)
* [Wdrażanie aplikacji platformy .NET dla Apache Spark w usłudze Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Dokumentacja usługi HDInsight](/azure/hdinsight/)
