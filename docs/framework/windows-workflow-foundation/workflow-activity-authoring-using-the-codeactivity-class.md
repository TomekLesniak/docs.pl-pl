---
title: Tworzenie działań przepływu pracy przy użyciu klasy elementu CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 714e0971a006db20d002b0f3a486533b1357fba7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293822"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>Tworzenie działań przepływu pracy przy użyciu klasy elementu CodeActivity

Działania utworzone przez dziedziczenie z <xref:System.Activities.CodeActivity> mogą implementować podstawowe zachowanie, zastępując <xref:System.Activities.CodeActivity.Execute%2A> metodę.

## <a name="using-codeactivitycontext"></a>Korzystanie z CodeActivityContext

 Dostęp do funkcji środowiska uruchomieniowego przepływu pracy można uzyskać z poziomu <xref:System.Activities.CodeActivity.Execute%2A> metody przy użyciu elementów członkowskich `context` parametru typu <xref:System.Activities.CodeActivityContext> . Dostępne są następujące funkcje <xref:System.Activities.CodeActivityContext> :

- Pobieranie i ustawianie wartości zmiennych i argumentów.

- Niestandardowe funkcje śledzenia przy użyciu programu <xref:System.Activities.CodeActivityContext.Track%2A> .

- Dostęp do właściwości wykonywania działania przy użyciu <xref:System.Activities.CodeActivityContext.GetProperty%2A> .

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>Aby utworzyć niestandardowe działanie, które dziedziczy z elementu CodeActivity

1. Otwórz program Visual Studio 2010.

2. Wybierz kolejno opcje **plik**, **Nowy** i **projekt**. Wybierz pozycję **Workflow 4,0** w obszarze **Visual C#** w oknie **typy projektów** , a następnie wybierz węzeł **V2010** . Wybierz pozycję **Biblioteka działań** w oknie **Szablony** . Nadaj nazwę nowej powitaniu projektu.

3. Kliknij prawym przyciskiem myszy pozycję zakończeniu. XAML w projekcie Hello i wybierz polecenie **Usuń**.

4. Kliknij prawym przyciskiem myszy projekt Hello i wybierz polecenie **Dodaj** , a następnie **klasy**. Nadaj nowej klasie nazwę HelloActivity.cs.

5. W pliku HelloActivity.cs Dodaj następujące `using` dyrektywy.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Uczyń nową klasę dziedziczą <xref:System.Activities.CodeActivity> przez dodanie klasy bazowej do deklaracji klasy.

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. Dodaj funkcję do klasy, dodając <xref:System.Activities.CodeActivity.Execute%2A> metodę.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Użyj, <xref:System.Activities.CodeActivityContext> Aby utworzyć rekord śledzenia.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
