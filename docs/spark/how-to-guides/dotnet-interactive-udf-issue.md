---
title: Pisz i Wywołaj UDF w programie .NET dla środowisk interaktywnych Apache Spark.
description: Dowiedz się, jak pisać i wywoływać UDF w programie .NET dla Apache Spark Interactive shells.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: d07d757f9e47a84c75f46b190bdb613b8d2db7c1
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224135"
---
# <a name="write-and-call-udfs-in-net-for-apache-spark-interactive-environments"></a>Pisz i Wywołaj UDF w programie .NET dla środowisk interaktywnych Apache Spark

W tym artykule dowiesz się, jak używać funkcji zdefiniowanych przez użytkownika (UDF) w środowisku programu .NET dla Apache Spark Interactive.

## <a name="prerequisites"></a>Wymagania wstępne

1. Instalowanie [programu .NET Interactive](https://github.com/dotnet/interactive)
2. Zainstaluj [laboratorium Jupyter Lab](https://jupyter.org/)

## <a name="net-for-apache-spark-interactive-experience"></a>Środowisko interaktywne platformy .NET dla Apache Spark

[Platforma .NET dla Apache Spark](https://github.com/dotnet/spark) używa [programu .NET Interactive](https://devblogs.microsoft.com/dotnet/net-interactive-is-here-net-notebooks-preview-2/) , aby zapewnić obsługę środowiska interaktywnego w środowisku Spark. Aby dowiedzieć się, jak skonfigurować środowisko w celu wypróbowania programu .NET Interactive z notesami Jupyter, zobacz [repozytorium interaktywne platformy .NET](https://github.com/dotnet/interactive).

Zaleca się także zapoznanie się z [tym artykułem dotyczącym serializacji UDF w programie .NET](udf-guide.md) , aby Apache Spark zrozumieć, jakie UDF są i jak są serializowane w programie .net dla Apache Spark.
W tym przewodniku wykorzystano notesy Jupyter, które ilustrują sposób korzystania z UDF w interaktywnym środowisku.

## <a name="define-a-udf-in-net-interactive"></a>Definiowanie formatu UDF w programie .NET Interactive

W interaktywnym środowisku, komórka może być uważana za fragment kodu, który jest przesyłany jako część jednej iteracji [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop). Na przykład zapoznaj się z następującym notesem, aby zrozumieć, co oznacza:

![Jupyter Notebook komórki](./media/dotnet-interactive/dotnet-interactive-cells.png)

Każdy z tych bloków oznaczony przez czerwoną strzałkę jest jedną komórką lub jednym przesłanianiem kodu do platformy Spark. Teraz podczas definiowania elementu UDF, który odwołuje się do niestandardowego obiektu zdefiniowanego przez użytkownika, jest wymagane, aby format UDF został zdefiniowany w tej samej komórce, w której jest zdefiniowany obiekt, do którego się odwołuje. Spójrzmy na to, co wygląda jak na przykład:

![Praca w formacie UDF](./media/dotnet-interactive/working-udf.png)

## <a name="call-a-udf-on-a-dataframe"></a>Wywoływanie formatu UDF w ramce Dataframe

Podczas wywoływania wcześniej zdefiniowanego elementu UDF na tym komputerze `DataFrame` Ważne jest upewnienie się, że format UDF jest zdefiniowany w wcześniej przesłanej komórce przed wywołaniem go, jak można zobaczyć w poprzednim przykładzie.

Teraz zobaczmy, co się stanie, jeśli wywołamy funkcję UDF w tej samej komórce, w której jest zdefiniowana.

![Niepowodzenie wywołania UDF](./media/dotnet-interactive/udf_fails.png)

Powyższym wyróżnionym błędem jest fakt, że zestawy UDF muszą zostać najpierw skompilowane i wysłane do procesów roboczych, zanim będzie można je wywołać w ramce Dataframe.

Poniżej przedstawiono kilka istotnych kwestii, które należy wziąć pod uwagę podczas wdrażania UDF na platformie .NET dla Apache Spark interaktywnego środowiska (na przykład [notesów Azure Synapse](https://docs.microsoft.com/azure/synapse-analytics/spark/apache-spark-development-using-notebooks)).

## <a name="faqs"></a>Często zadawane pytania

1. **Dlaczego mój element UDF odwołujący się do niestandardowego obiektu zdefiniowanego przez użytkownika Zgłoś błąd `Type Submission#_ is not marked as serializable` ?**
    Środowisko .NET Interactive zawija każdą z tych komórek z klasą otoki numeru przesyłania komórki, aby jednoznacznie identyfikować każdą komórkę, która jest przesyłana. Jak opisano szczegółowo w [tym przewodniku](udf-guide.md), podczas serializacji elementu UDF, który odwołuje się do obiektu niestandardowego, jego obiekt docelowy jest również wybierany do serializacji, który w przypadku programu .NET Interactive jest opakowany przez klasę otoki komórki, w której jest zdefiniowany obiekt niestandardowy.
    Teraz zobaczmy, jak ma to wpływ na definicję formatu UDF w notesie:

    ![Błąd serializacji UDF](./media/dotnet-interactive/udf-serialization-error.png)

    Jak widać w przypadku `udf2_fails` , zobaczysz komunikat o błędzie informujący o tym, że typ `Submission#7` nie jest oznaczony jako możliwy do serializacji. jest to spowodowane tym, że program .NET Interactive zawija każdy obiekt zdefiniowany w komórce z `Submission#` klasą, która jest generowana na bieżąco i dlatego nie jest oznaczona jako `Serializable` .

    Z tego powodu jest wymagane, **aby element UDF odwołujący się do obiektu niestandardowego został zdefiniowany w tej samej komórce co ten obiekt**.

2. **Dlaczego zmienne nie są emitowane w programie .NET Interactive?**
    Ze względów opisanych wcześniej zmienne emisji nie działają w programie .NET Interactive. Warto zapoznać się z [tym przewodnikiem dotyczącym zmiennych emisji](broadcast-guide.md) , aby lepiej zrozumieć, jakie zmienne emisji są i jak ich używać. Zmienne emisji przyczyn nie współpracują ze scenariuszami interaktywnymi wynikają z tego, że projekt programu .NET Interactive jest dołączany do każdego obiektu zdefiniowanego w komórce z jego klasą przesłaniania, która nie jest oznaczona jako możliwa do serializacji, kończy się niepowodzeniem z wyjątkiem tego samego wyjątku jak pokazano wcześniej.
    Szczegółowemy nieco więcej z poniższym przykładem:

    ![Zmienne emisji kończą się niepowodzeniem](./media/dotnet-interactive/broadcast-fails.png)

    Zgodnie z zaleceniami w poprzednich sekcjach definiujemy zarówno format UDF, jak i obiekt, do którego się odwołuje (zmienna emisji w tym przypadku) w tej samej komórce, ale nadal widzimy `SerializationException` błąd podczas tworzenia wniosku o `Microsoft.Spark.Sql.Session` nieoznaczony jako możliwy do serializacji. Wynika to z faktu, że gdy kompilator próbuje serializować obiekt zmiennej emisji `bv` , odnajdzie jego nazwę do dołączenia do [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) obiektu `spark` , który musi być oznaczony jako możliwy do serializacji. Może to być bardziej łatwe dzięki przejęciu wglądu w kompilację z dekompilowanym zestawem tej komórki:

    ![Dekompilowany kod zestawu](./media/dotnet-interactive/decompiledAssembly.png)

    Jeśli oznaczemy [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) klasę jako `[Serializable]` , możemy to zrobić, ale nie jest to idealne rozwiązanie, ponieważ nie chcemy, aby użytkownik mógł serializować obiekt SparkSession, ponieważ może to prowadzić do niektórych brzmienia, niepożądanego zachowania. Jest to [znany problem](https://github.com/dotnet/spark/issues/619) i zostanie rozwiązany w przyszłych wersjach.
