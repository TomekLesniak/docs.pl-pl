---
title: Zakładki — WF
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: 7a52823ff68d8f09895bb3a9323a57d3abccd823
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289116"
---
# <a name="bookmarks"></a>Zakładki

Zakładki to mechanizm, który umożliwia działanie pasywnego oczekiwania na dane wejściowe bez udziału w wątku przepływu pracy. Gdy działanie sygnalizuje, że oczekuje na bodźce, może utworzyć zakładkę. Wskazuje to, że środowisko uruchomieniowe nie powinno być uznawane za wykonane, nawet gdy aktualnie wykonywana Metoda (która została utworzona <xref:System.Activities.Bookmark> ) zwraca wartość.  
  
## <a name="bookmark-basics"></a>Podstawowe informacje o zakładkach  

 <xref:System.Activities.Bookmark>Reprezentuje punkt, w którym można wznowić wykonywanie (i za pomocą którego dane wejściowe można dostarczyć) w ramach wystąpienia przepływu pracy. Zazwyczaj <xref:System.Activities.Bookmark> otrzymujesz nazwę i zewnętrzny kod (hosta lub rozszerzenia) jest odpowiedzialny za wznawianie zakładki z odpowiednimi danymi. Gdy <xref:System.Activities.Bookmark> zostanie wznowiony, środowisko uruchomieniowe przepływu pracy planuje <xref:System.Activities.BookmarkCallback> delegata, który został skojarzony z tym <xref:System.Activities.Bookmark> w momencie jego tworzenia.  
  
## <a name="bookmark-options"></a>Opcje zakładki  

 <xref:System.Activities.BookmarkOptions>Klasa określa typ <xref:System.Activities.Bookmark> tworzonego elementu. Możliwe niewzajemnie wykluczające się wartości to <xref:System.Activities.BookmarkOptions.None> , <xref:System.Activities.BookmarkOptions.MultipleResume> , i <xref:System.Activities.BookmarkOptions.NonBlocking> . Użyj <xref:System.Activities.BookmarkOptions.None> , domyślnie, podczas tworzenia, <xref:System.Activities.Bookmark> który jest oczekiwany do wznowienia dokładnie jeden raz. Używany <xref:System.Activities.BookmarkOptions.MultipleResume> podczas tworzenia <xref:System.Activities.Bookmark> , który może być wznowiony wiele razy. Używany <xref:System.Activities.BookmarkOptions.NonBlocking> podczas tworzenia <xref:System.Activities.Bookmark> , który może nigdy nie zostać wznowiony. W przeciwieństwie do zakładek utworzonych przy użyciu domyślnego <xref:System.Activities.BookmarkOptions> , <xref:System.Activities.BookmarkOptions.NonBlocking> zakładki nie uniemożliwiają ukończenia działania.  
  
## <a name="bookmark-resumption"></a>Wznowienie zakładki  

 Zakładki można wznawiać przez kod poza przepływem pracy przy użyciu jednego z <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> przeciążeń. W tym przykładzie `ReadLine` tworzone jest działanie. Po wykonaniu `ReadLine` działanie tworzy <xref:System.Activities.Bookmark> , rejestruje wywołanie zwrotne, a następnie czeka na <xref:System.Activities.Bookmark> wznowienie. Gdy zostanie ono wznowione, `ReadLine` działanie przypisze dane, które zostały przesłane z <xref:System.Activities.Bookmark> do tego <xref:System.Activities.Activity%601.Result%2A> argumentu.  
  
```csharp  
public sealed class ReadLine : NativeActivity<string>  
{  
    [RequiredArgument]  
    public  InArgument<string> BookmarkName { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        // Create a Bookmark and wait for it to be resumed.  
        context.CreateBookmark(BookmarkName.Get(context),
            new BookmarkCallback(OnResumeBookmark));  
    }  
  
    // NativeActivity derived activities that do asynchronous operations by calling
    // one of the CreateBookmark overloads defined on System.Activities.NativeActivityContext
    // must override the CanInduceIdle property and return true.  
    protected override bool CanInduceIdle  
    {  
        get { return true; }  
    }  
  
    public void OnResumeBookmark(NativeActivityContext context, Bookmark bookmark, object obj)  
    {  
        // When the Bookmark is resumed, assign its value to  
        // the Result argument.  
        Result.Set(context, (string)obj);  
    }  
}  
```  
  
 W tym przykładzie zostanie utworzony przepływ pracy, który używa `ReadLine` działania do zbierania nazwy użytkownika i wyświetlania go w oknie konsoli. Aplikacja hosta wykonuje rzeczywistą ilość pracy zbierającej dane wejściowe i przekazuje ją do przepływu pracy przez wznowienie <xref:System.Activities.Bookmark> .  
  
```csharp  
Variable<string> name = new Variable<string>  
{  
    Name = "name"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        name  
    },  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "What is your name?"  
        },  
        new ReadLine()  
        {  
            BookmarkName = "UserName",  
            Result = name  
        },  
        new WriteLine()  
        {  
            Text = new InArgument<string>((env) => "Hello, " + name.Get(env))  
        }  
    }  
};  
  
AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
// Create the WorkflowApplication using the desired  
// workflow definition.  
WorkflowApplication wfApp = new WorkflowApplication(wf);  
  
// Handle the desired lifecycle events.  
wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
{  
    // Signal the host that the workflow is complete.  
    syncEvent.Set();  
};  
  
// Start the workflow.  
wfApp.Run();  
  
// Collect the user's name and resume the bookmark.  
// Bookmark resumption only occurs when the workflow  
// is idle. If a call to ResumeBookmark is made and the workflow  
// is not idle, ResumeBookmark blocks until the workflow becomes  
// idle before resuming the bookmark.  
wfApp.ResumeBookmark("UserName", Console.ReadLine());  
  
// Wait for Completed to arrive and signal that  
// the workflow is complete.  
syncEvent.WaitOne();  
```  
  
 Gdy `ReadLine` działanie jest wykonywane, tworzy <xref:System.Activities.Bookmark> nazwę, `UserName` a następnie czeka na wznowienie zakładki. Host zbiera wymagane dane, a następnie wznawia działanie <xref:System.Activities.Bookmark> . Przepływ pracy zostanie wznowiony, zostanie wyświetlona nazwa, a następnie zostanie zakończona. Należy pamiętać, że żaden kod synchronizacji nie jest wymagany w odniesieniu do wznowienia zakładki. <xref:System.Activities.Bookmark>Można wznowić tylko wtedy, gdy przepływ pracy jest bezczynny, a jeśli przepływ pracy nie jest bezczynny, wywołanie <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> bloków do momentu, gdy przepływ pracy przestanie być bezczynny.  
  
## <a name="bookmark-resumption-result"></a>Wynik wznowienia zakładki  

 <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> zwraca <xref:System.Activities.BookmarkResumptionResult> wartość wyliczenia wskazującą wyniki żądania wznowienia zakładki. Możliwe wartości zwracane to <xref:System.Activities.BookmarkResumptionResult.Success> , <xref:System.Activities.BookmarkResumptionResult.NotReady> , i <xref:System.Activities.BookmarkResumptionResult.NotFound> . Hosty i rozszerzenia mogą używać tej wartości, aby określić sposób dalszego działania.
