---
title: NativeActivity, klasa bazowa
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d875f62dacadb2baf6b5d7e93ddb2933aed9cdb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274962"
---
# <a name="nativeactivity-base-class"></a>NativeActivity, klasa bazowa

<xref:System.Activities.NativeActivity> jest klasą abstrakcyjną z chronionym konstruktorem. <xref:System.Activities.CodeActivity>Na przykład, <xref:System.Activities.NativeActivity> jest używany do pisania bezwzględnego zachowania przez implementację <xref:System.Activities.NativeActivity.Execute%2A> metody. W przeciwieństwie do <xref:System.Activities.CodeActivity> , <xref:System.Activities.NativeActivity> ma dostęp do wszystkich narażonych funkcji środowiska uruchomieniowego przepływu pracy za pomocą <xref:System.Activities.NativeActivityContext> obiektu przesłanego do <xref:System.Activities.NativeActivity.Execute%2A> metody.

## <a name="using-nativeactivitycontext"></a>Korzystanie z NativeActivityContext

 Dostęp do funkcji środowiska uruchomieniowego przepływu pracy można uzyskać z poziomu <xref:System.Activities.NativeActivity.Execute%2A> metody przy użyciu elementów członkowskich `context` parametru typu <xref:System.Activities.NativeActivityContext> . Dostępne są następujące funkcje <xref:System.Activities.NativeActivityContext> :

- Pobieranie i określanie argumentów i zmiennych.

- Planowanie działań podrzędnych przy użyciu <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>

- Przerywanie wykonywania działania przy użyciu <xref:System.Activities.NativeActivityContext.Abort%2A> .

- Anulowanie wykonywania elementu podrzędnego za pomocą <xref:System.Activities.NativeActivityContext.CancelChild%2A> i <xref:System.Activities.NativeActivityContext.CancelChildren%2A> .

- Dostęp do zakładek aktywności przy użyciu takich metod jak <xref:System.Activities.NativeActivityContext.CreateBookmark%2A> , <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> i <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A> .

- Niestandardowe funkcje śledzenia przy użyciu programu <xref:System.Activities.CodeActivityContext.Track%2A> .

- Dostęp do właściwości wykonywania działania i właściwości wartości przy użyciu <xref:System.Activities.CodeActivityContext.GetProperty%2A> i <xref:System.Activities.NativeActivityContext.GetValue%2A> .

- Planowanie akcji i funkcji działania przy użyciu <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> i <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A> .

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>Aby utworzyć niestandardowe działanie, które dziedziczy z natywnego

1. Otwórz Studio 2010.

2. Wybierz kolejno opcje **plik**, **Nowy** i **projekt**. Wybierz pozycję **Workflow 4,0** w obszarze **Visual C#** w oknie **typy projektów** , a następnie wybierz węzeł **V2010** . Wybierz pozycję **Biblioteka działań** w oknie **Szablony** . Nadaj nazwę nowej powitaniu projektu.

3. Kliknij prawym przyciskiem myszy pozycję zakończeniu. XAML w projekcie Hello i wybierz polecenie **Usuń**.

4. Kliknij prawym przyciskiem myszy projekt Hello i wybierz polecenie **Dodaj**, a następnie **klasy**. Nadaj nowej klasie nazwę HelloActivity.cs.

5. W pliku HelloActivity.cs Dodaj następujące `using` dyrektywy.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Uczyń nową klasę dziedziczą <xref:System.Activities.NativeActivity> przez dodanie klasy bazowej do deklaracji klasy.

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. Dodaj funkcję do klasy, dodając <xref:System.Activities.NativeActivity.Execute%2A> metodę.

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Zastąp <xref:System.Activities.NativeActivity.CacheMetadata%2A> metodę i Wywołaj odpowiednią metodę Add, aby umożliwić środowisko uruchomieniowe przepływu pracy znać zmienne, argumenty, elementy podrzędne i Delegaty działania niestandardowego. Aby uzyskać więcej informacji, zobacz <xref:System.Activities.NativeActivityMetadata> Klasa.

9. Użyj <xref:System.Activities.NativeActivityContext> obiektu, aby zaplanować zakładkę. Zobacz <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> , aby uzyskać szczegółowe informacje na temat tworzenia, planowania i wznawiania zakładki.

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
