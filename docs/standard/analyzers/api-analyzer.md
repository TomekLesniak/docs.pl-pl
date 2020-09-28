---
title: Analizator interfejsów API platformy .NET
description: Dowiedz się, jak Analizator interfejsu API platformy .NET może pomóc w wykrywaniu przestarzałych interfejsów API i problemów ze zgodnością platformy.
author: oliag
ms.date: 02/20/2020
ms.technology: dotnet-standard
ms.openlocfilehash: f1268d5f208e19f1b69ed487370fb4c96723a204
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406248"
---
# <a name="net-api-analyzer"></a>Analizator interfejsów API platformy .NET

Analizator interfejsu API platformy .NET to Analizator Roslyn, który wykrywa potencjalne zagrożenia zgodności dla interfejsów API języka C# na różnych platformach i wykrywa wywołania przestarzałych interfejsów API. Może być przydatne dla wszystkich deweloperów C# na dowolnym etapie opracowywania.

Analizator interfejsu API jest dostarczany jako pakiet NuGet [Microsoft. dotnet. analizatory. zgodność](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/). Po odwoływaniu się do niego w projekcie program automatycznie monitoruje kod i wskazuje na problematyczne użycie interfejsu API. Możesz również uzyskać sugestie dotyczące możliwych poprawek, klikając żarówkę. Menu rozwijane zawiera opcję pomijania ostrzeżeń.

> [!NOTE]
> Analizator interfejsu API platformy .NET jest nadal w wersji wstępnej.

## <a name="prerequisites"></a>Wymagania wstępne

- Program Visual Studio 2017 lub jego nowsze wersje lub Visual Studio dla komputerów Mac (wszystkie wersje).

## <a name="discover-deprecated-apis"></a>Odkryj przestarzałe interfejsy API

### <a name="what-are-deprecated-apis"></a>Co to są przestarzałe interfejsy API?

Rodzina .NET to zestaw dużych produktów, które są stale uaktualniane, aby lepiej spełniały potrzeby klientów. Jest to naturalne, aby zastąpić niektóre interfejsy API i zamienić je na nowe. Interfejs API jest uznawany za przestarzały, gdy istnieje lepsza alternatywa. Jednym ze sposobów, aby poinformować, że interfejs API jest przestarzały i nie powinien być używany, to Oznacz go <xref:System.ObsoleteAttribute> atrybutem. Wadą tego podejścia jest to, że istnieje tylko jeden identyfikator diagnostyczny dla wszystkich przestarzałych interfejsów API (dla języka C#, [CS0612](../../csharp/misc/cs0612.md)). Oznacza to, że:

- Nie jest możliwe posiadanie dedykowanych dokumentów dla każdego przypadku.
- Nie można pominąć pewnej kategorii ostrzeżeń. Możesz pominąć wszystkie lub żadne z nich.
- Aby poinformować użytkowników o nowym zaniechaniu, należy zaktualizować zestaw lub pakiet docelowy, do którego istnieje odwołanie.

Analizator interfejsu API korzysta z kodów błędów specyficznych dla interfejsu API, które zaczynają się od DE (co oznacza błąd zaniechania), co umożliwia kontrolę nad wyświetlaniem indywidualnych ostrzeżeń. Przestarzałe interfejsy API identyfikowane przez analizator są zdefiniowane w repozytorium [dotnet/platform-COMPAT](https://github.com/dotnet/platform-compat) .

### <a name="add-the-api-analyzer-to-your-project"></a>Dodawanie analizatora interfejsu API do projektu

1. Otwórz program Visual Studio.
2. Otwórz projekt, w którym chcesz uruchomić Analizator.
3. W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**. (Ta opcja jest również dostępna w menu **projekt** ).
4. Na karcie Menedżer pakietów NuGet:
   1. Wybierz pozycję "nuget.org" jako źródło pakietu.
   2. Przejdź do karty **przeglądanie** .
   3. Wybierz pozycję **Uwzględnij wersję wstępną**.
   4. Wyszukaj element **Microsoft. dotnet. analizatory. zgodność**.
   5. Wybierz ten pakiet z listy.
   6. Wybierz przycisk **Instaluj** .
   7. Wybierz przycisk **OK** w oknie dialogowym **Podgląd zmian** , a następnie **Wybierz przycisk** Akceptuję w oknie dialogowym **akceptacji licencji** , jeśli zgadzasz się z postanowieniami licencyjnymi dotyczącymi wymienionych pakietów.

### <a name="use-the-api-analyzer"></a>Korzystanie z analizatora interfejsu API

Gdy przestarzały interfejs API, taki jak <xref:System.Net.WebClient> , jest używany w kodzie, Analizator interfejsu API podświetla go przy użyciu zielonej linii falistej. Po umieszczeniu wskaźnika myszy na wywołaniu interfejsu API żarówka jest wyświetlana z informacjami o zaniechaniu interfejsu API, jak w poniższym przykładzie:

![Zrzut ekranu interfejsu API klienta WebClient z zieloną linią falistej i żarówką po lewej stronie.](media/api-analyzer/green-squiggle.jpg)

Okno **Lista błędów** zawiera ostrzeżenia o UNIKATOWYm identyfikatorze na przestarzały interfejs API, jak pokazano w poniższym przykładzie ( `DE004` ):

![Zrzut ekranu okna Lista błędów przedstawiający identyfikator i opis ostrzeżenia.](media/api-analyzer/warnings-id-and-descriptions.jpg "Okno Lista błędów, które zawiera ostrzeżenia.")

Klikając identyfikator, przejdź do strony sieci Web ze szczegółowymi informacjami o tym, dlaczego interfejs API był przestarzały i sugestie dotyczące alternatywnych interfejsów API, których można użyć.

Wszystkie ostrzeżenia można pominąć przez kliknięcie prawym przyciskiem myszy wyróżnionego elementu członkowskiego i wybranie polecenia **Pomiń \<diagnostic ID> **. Istnieją dwa sposoby pomijania ostrzeżeń:

- [lokalnie (w źródle)](#suppress-warnings-locally)
- [globalnie (w pliku pominięć)](#suppress-warnings-globally) — zalecane

### <a name="suppress-warnings-locally"></a>Pomijaj ostrzeżenia lokalnie

Aby pominąć ostrzeżenia lokalnie, kliknij prawym przyciskiem myszy element członkowski, dla którego chcesz pominąć ostrzeżenia, a następnie wybierz polecenie **szybkie akcje i refaktoryzacje**  >  ** \<diagnostic ID> Pomijaj *Identyfikator diagnostyczny***  >  **w źródle**. Dyrektywa preprocesora ostrzegawczego [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) jest dodawana do kodu źródłowego w zdefiniowanym zakresie: ![ zrzut ekranu przedstawiający kod z funkcją #pragma warning Disable.](media/api-analyzer/suppress-in-source.jpg)

### <a name="suppress-warnings-globally"></a>Pomijaj ostrzeżenia globalnie

Aby pominąć ostrzeżenia globalnie, kliknij prawym przyciskiem myszy element członkowski, dla którego chcesz pominąć ostrzeżenia, a następnie wybierz polecenie **szybkie akcje i refaktoryzacje**  >  ** \<diagnostic ID> Pomiń *Identyfikator diagnostyczny***  >  **w pliku pomijania**.

![Zrzut ekranu przedstawiający menu dostępne po kliknięciu prawym przyciskiem myszy z opcjami, które umożliwiają pominięcie ostrzeżenia w programie Visual Studio.](media/api-analyzer/suppress-in-sup-file.jpg)

Plik *GlobalSuppressions.cs* jest dodawany do projektu po pierwszym pominięciu. Do tego pliku są dołączane nowe, globalne pomijania.

![Zrzut ekranu przedstawiający plik GlobalSuppressions.cs w Eksplorator rozwiązań.](media/api-analyzer/suppression-file.jpg)

Globalne pomijanie jest zalecanym sposobem zapewnienia spójności użycia interfejsu API między projektami.

## <a name="discover-cross-platform-issues"></a>Odkryj problemy dotyczące wielu platform

> [!NOTE]
> W programie .NET 5,0 wprowadzono [analizatora zgodności platformy](platform-compat-analyzer.md) jako zamiennik tej funkcji. Analizator zgodności platformy jest dołączony do zestawu .NET SDK (nie trzeba go instalować oddzielnie) i jest domyślnie włączony.

Podobnie jak w przypadku przestarzałych interfejsów API, Analizator identyfikuje wszystkie interfejsy API, które nie są dla wielu platform. Na przykład <xref:System.Console.WindowWidth?displayProperty=nameWithType> program działa w systemie Windows, ale nie w systemie Linux i macOS. Identyfikator diagnostyki jest wyświetlany w oknie **Lista błędów** . Możesz pominąć to ostrzeżenie, klikając prawym przyciskiem myszy i wybierając polecenie **szybkie akcje i refaktoryzacje**. W przeciwieństwie do przypadków wycofania, w których są dostępne dwie opcje (można nadal korzystać z przestarzałego elementu członkowskiego i pomijać ostrzeżenia lub nie używać ich wcale), tutaj jeśli tworzysz kod tylko dla niektórych platform, możesz pominąć wszystkie ostrzeżenia dla wszystkich innych platform, które nie są planowane do uruchamiania kodu. Aby to zrobić, wystarczy edytować plik projektu i dodać `PlatformCompatIgnore` Właściwość, która wyświetla listę wszystkich platform do zignorowania. Akceptowane są następujące wartości: `Linux` , `macOS` , i `Windows` .

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;macOS</PlatformCompatIgnore>
</PropertyGroup>
```

Jeśli Twój kod jest przeznaczony dla wielu platform i chcesz skorzystać z interfejsu API nieobsługiwanego przez niektóre z nich, możesz zabezpieczyć tę część kodu za pomocą `if` instrukcji:

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

Można również wykonać warunkowe kompilowanie na platformę docelową/system operacyjny, ale obecnie trzeba to zrobić [ręcznie](../frameworks.md#how-to-specify-a-target-framework).

## <a name="supported-diagnostics"></a>Obsługiwana Diagnostyka

Obecnie Analizator obsługuje następujące przypadki:

- Użycie interfejsu API .NET Standard, który zgłasza <xref:System.PlatformNotSupportedException> (PC001).
- Użycie interfejsu API .NET Standard, który nie jest dostępny w .NET Framework 4.6.1 (PC002).
- Użycie natywnego interfejsu API, który nie istnieje w platformy UWP (PC003).
- Użycie interfejsów API Delegate. BeginInvoke i EndInvoke (PC004).
- Użycie interfejsu API, który jest oznaczony jako przestarzały (rozxxxx).

## <a name="ci-machine"></a>Komputer CI

Wszystkie te diagnostyki są dostępne nie tylko w środowisku IDE, ale również w wierszu polecenia w ramach konstruowania projektu, który obejmuje serwer CI.

## <a name="configuration"></a>Konfigurowanie

Użytkownik decyduje o sposobie traktowania diagnostyki: w postaci ostrzeżeń, błędów, sugestii lub wyłączania. Na przykład jako architekt można zdecydować, że problemy ze zgodnością powinny być traktowane jako błędy, wywołania niektórych przestarzałych interfejsów API generują ostrzeżenia, podczas gdy inne tylko generują sugestie. Można ją skonfigurować osobno według identyfikatora diagnostyki i projektu. W tym celu w **Eksplorator rozwiązań**przejdź do węzła **zależności** w ramach projektu. Rozwiń węzeł **Dependencies**  >  **analizatory**zależności węzłów  >  **Microsoft. dotnet. analizatory. zgodność**. Kliknij prawym przyciskiem myszy identyfikator diagnostyczny, wybierz pozycję **Ustaw ważność zestawu reguł** i wybierz żądaną opcję.

![Zrzut ekranu przedstawiający Eksplorator rozwiązań wyświetlania diagnostyki i wyskakujących okienek z ważnością zestawu reguł.](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a>Zobacz także

- Wprowadzenie do wpisu w blogu [analizatora interfejsu API](https://devblogs.microsoft.com/dotnet/introducing-api-analyzer/) .
- Wideo z pokazem [interfejsu API Analyzer](https://youtu.be/eeBEahYXGd0) w serwisie YouTube.
- [Analizator zgodności platformy](platform-compat-analyzer.md)
