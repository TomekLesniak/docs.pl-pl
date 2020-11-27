---
title: Przegląd przepływu komunikatu
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: cb2924b62fce62620b664efa34208deb12dd34b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285541"
---
# <a name="message-flow-overview"></a>Przegląd przepływu komunikatu

W systemie rozproszonym zawierającym połączone usługi należy określić związek przyczyn między usługami. Ważne jest, aby zrozumieć różne składniki, które były częścią przepływu żądania, aby zapewnić obsługę krytycznych scenariuszy, takich jak monitorowanie kondycji, rozwiązywanie problemów i analiza głównych przyczyn. Aby umożliwić korelację śladów między różnymi usługami, w .NET Framework 4 dodaliśmy obsługę za pomocą następujących funkcji:

- Śledzenie analityczne: wysoka wydajność i niska funkcja śledzenia szczegółowości przy użyciu funkcji Śledzenie zdarzeń systemu Windows (ETW).

- Kompleksowy model działań dla usług WCF/WF: Ta funkcja obsługuje korelację śladów generowanych przez <xref:System.ServiceModel> <xref:System.Workflow.ComponentModel> obszary nazw i.

- Śledzenie ETW dla WF: Ta funkcja używa rekordów śledzenia generowanych przez usługi WF w celu zapewnienia wglądu w bieżący stan i postęp przepływu pracy.

 Błędy zarejestrowane w rekordzie śledzenia lub śledzenia mogą służyć do znajdowania wad kodu lub niepoprawnie sformułowanych komunikatów. Właściwość ActivityId węzła korelacji w nagłówku komunikatu zdarzenia może służyć do określenia działania powodującego błąd. Aby włączyć śledzenie przepływu komunikatów według identyfikatora działania, zobacz [Konfigurowanie śledzenia przepływu komunikatów](./etw/configuring-message-flow-tracing.md). W tym temacie przedstawiono sposób włączania śledzenia przepływu komunikatów w projekcie utworzonym w samouczku Wprowadzenie.

### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>Aby włączyć śledzenie przepływu komunikatów w samouczku Wprowadzenie

1. Otwórz Podgląd zdarzeń, klikając przycisk **Start**, **Uruchom** i wprowadzając `eventvwr.exe` .

2. Jeśli nie włączono śledzenia analitycznego, rozwiń węzeł **Dzienniki aplikacji i usług**, **Microsoft**, **Windows**, **serwer aplikacji-aplikacje**. Wybierz **Widok**, **Pokaż dzienniki analityczne i debugowania**. Kliknij prawym przyciskiem myszy pozycję **analityczne** i wybierz pozycję **Włącz dziennik**. Pozostaw Podgląd zdarzeń otwarty, aby umożliwić wyświetlanie śladów.

3. Otwórz przykład utworzony w [samouczku wprowadzenie](../getting-started-tutorial.md) w programie Visual Studio 2012. Należy pamiętać, że aby można było utworzyć usługę, należy uruchomić program Visual Studio 2012 jako administrator. Jeśli masz zainstalowane przykłady WCF, możesz otworzyć [wprowadzenie](../samples/getting-started-sample.md), która zawiera ukończony projekt utworzony w samouczku.

4. Kliknij prawym przyciskiem myszy projekt **usługi** i wybierz polecenie **Dodaj**, **nowy element**. Wybierz pozycję **plik konfiguracji aplikacji** , a następnie kliknij przycisk **OK**.

5. Dodaj następujący kod do pliku App.Config utworzonego w poprzednim kroku.

    ```xml
    <system.serviceModel>
      <diagnostics>
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
      </diagnostics>
    </system.serviceModel>
    ```

6. Uruchom aplikację serwera bez debugowania, naciskając klawisze CTRL + F5. Aby wykonać projekt klienta, kliknij prawym przyciskiem myszy projekt **klienta** i wybierz polecenie **Debuguj**, **Uruchom nowe wystąpienie**.

7. Aby śledzić zdarzenia z klienta do serwera programu, Dodaj następujący plik do pliku konfiguracji aplikacji w projekcie klienta.

    ```xml
    <diagnostics>
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
    </diagnostics>
    ```

8. W Program.cs na kliencie Dodaj następującą instrukcję using.

    ```csharp
    using System.Diagnostics;
    ```

9. W metodzie Main w pliku program.cs w projekcie klienta ustaw identyfikator GUID śledzenia, który ma być propagowany w dzienniku zdarzeń.

    ```csharp
    Guid guid = Guid.NewGuid();
    Trace.CorrelationManager.ActivityId = guid;
    ```

10. Odśwież i przejrzyj dziennik **analityczny**  .  Poszukaj zdarzenia o IDENTYFIKATORze 220.  Wybierz zdarzenie, a następnie kliknij kartę **szczegóły** w okienku podglądu. To zdarzenie będzie zawierać identyfikator korelacji dla działania wywołującego.

    ```xml
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />
    ```

    > [!NOTE]
    > Wszystkie zdarzenia o tym samym identyfikatorze GUID w ActivityID są powiązane z jednym żądaniem. Może to służyć do skorelowania komunikatów od określonego klienta do określonej usługi. Jeśli klient wywołał inną usługę, ten sam Klient może być zidentyfikowany przez ActivityID.

11. W niektórych przypadkach ActivityID może zmienić pierwotny identyfikator GUID na nowy ActivityID. W takim przypadku jest emitowane zdarzenie transferu. Ten identyfikator zdarzenia to 499, a zdarzenie będzie zawierać następujące dane w nagłówku.

    ```xml
    <Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">
        <System>
            <Provider Name="Microsoft-Windows-Application Server-Applications" Guid="{c651f5f6-1c0d-492e-8ae1-b4efd7c9d503}" />
            <EventID>499</EventID>
            ...
            <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" RelatedActivityID="{85FC0930-9C49-42DA-804B-A7368104BD1B}" />
            ...
       </System>
    </Event>
    ```

    > [!NOTE]
    > Zdarzenie transferu rejestruje zmianę aktywnego ActivityID z identyfikatora GUID określonego jako ActivityID do identyfikatora GUID określonego jako RelatedActivityID. Po emisji zdarzenia transferu wszystkie zdarzenia będą zawierać nowy identyfikator GUID jako ActivityID.
