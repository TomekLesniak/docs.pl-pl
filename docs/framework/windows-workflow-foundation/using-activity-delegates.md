---
title: Używanie delegatów działania
ms.date: 03/30/2017
ms.assetid: e33cf876-8979-440b-9b23-4a12d1139960
ms.openlocfilehash: 66a03187336475ed377fda032506cfa66d3daf58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293302"
---
# <a name="using-activity-delegates"></a>Używanie delegatów działania

Delegaty działań umożliwiają autorom działania udostępnianie wywołań zwrotnych z określonymi podpisami, dla których użytkownicy działania mogą udostępniać programy obsługi oparte na działaniach. Dostępne są dwa typy delegatów aktywności: służy <xref:System.Activities.ActivityAction%601> do definiowania delegatów działań, które nie mają wartości zwracanej, i służy <xref:System.Activities.ActivityFunc%601> do definiowania delegatów działań, które mają wartość zwracaną.

Delegaty działania są przydatne w scenariuszach, w których działanie podrzędne musi być ograniczone do posiadania określonego podpisu. Na przykład <xref:System.Activities.Statements.While> działanie może zawierać dowolny typ działania podrzędnego bez ograniczeń, ale treść <xref:System.Activities.Statements.ForEach%601> działania to <xref:System.Activities.ActivityAction%601> , a działanie podrzędne, które jest ostatecznie wykonywane przez, <xref:System.Activities.Statements.ForEach%601> musi mieć ten <xref:System.Activities.InArgument%601> sam typ elementów członkowskich kolekcji, których <xref:System.Activities.Statements.ForEach%601> Wyliczenie.

## <a name="using-activityaction"></a>Korzystanie z ActivityAction

Niektóre [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] działania wykorzystują akcje działania, takie jak <xref:System.Activities.Statements.Catch> działanie i <xref:System.Activities.Statements.ForEach%601> działanie. W każdym przypadku akcja działania reprezentuje lokalizację, w której autor przepływu pracy określa działanie, aby zapewnić żądane zachowanie podczas redagowania przepływu pracy przy użyciu jednej z tych działań. W poniższym przykładzie <xref:System.Activities.Statements.ForEach%601> działanie jest używane do wyświetlania tekstu w oknie konsoli. Treść <xref:System.Activities.Statements.ForEach%601> jest określana za pomocą <xref:System.Activities.ActivityAction%601> , która jest zgodna z typem, <xref:System.Activities.Statements.ForEach%601> który jest ciągiem. <xref:System.Activities.Statements.WriteLine>Działanie określone w elemencie <xref:System.Activities.ActivityDelegate.Handler%2A> ma jego <xref:System.Activities.Statements.WriteLine.Text%2A> argument powiązany z wartościami ciągu w kolekcji, które <xref:System.Activities.Statements.ForEach%601> wykonuje iteracja działania.

[!code-csharp[CFX_ActivityExample#6](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#6)]

ActionArgument jest używany do przepływu poszczególnych elementów w kolekcji do WriteLine. Po wywołaniu przepływu pracy następujące dane wyjściowe są wyświetlane w konsoli programu.

```console
HelloWorld.
```

W przykładach w tym temacie użyto składni inicjowania obiektu. Składnia inicjowania obiektu może być przydatnym sposobem tworzenia definicji przepływu pracy w kodzie, ponieważ zawiera hierarchiczny widok działań w przepływie pracy i pokazuje relację między działaniami. Nie ma potrzeby używania składni inicjowania obiektów podczas programistycznego tworzenia przepływów pracy. Poniższy przykład jest funkcjonalnie równoważny z poprzednim przykładem.

[!code-csharp[CFX_ActivityExample#7](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#7)]

Aby uzyskać więcej informacji na temat inicjatorów obiektów, zobacz [How to: Initialize obiektów bez wywoływania konstruktora (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) i [instrukcje: deklarowanie obiektu za pomocą inicjatora obiektów (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).

W poniższym przykładzie <xref:System.Activities.Statements.TryCatch> działanie jest używane w przepływie pracy. <xref:System.ApplicationException>Jest generowany przez przepływ pracy i jest obsługiwany przez <xref:System.Activities.Statements.Catch%601> działanie. Obsługa akcji działania działania <xref:System.Activities.Statements.Catch%601> jest <xref:System.Activities.Statements.WriteLine> działaniem, a szczegóły wyjątku są przepływane do niego przy użyciu `ex` <xref:System.Activities.DelegateInArgument%601> .

[!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]

Podczas tworzenia niestandardowego działania, które definiuje <xref:System.Activities.ActivityAction%601> , należy użyć <xref:System.Activities.Statements.InvokeAction%601> do modelowania wywołania tego elementu <xref:System.Activities.ActivityAction%601> . W tym przykładzie `WriteLineWithNotification` zdefiniowano działanie niestandardowe. To działanie składa się z <xref:System.Activities.Statements.Sequence> , która zawiera <xref:System.Activities.Statements.WriteLine> działanie, po którym następuje wywołanie, które <xref:System.Activities.Statements.InvokeAction%601> <xref:System.Activities.ActivityAction%601> przyjmuje jeden argument ciągu.

[!code-csharp[CFX_ActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#1)]

Gdy przepływ pracy jest tworzony przy użyciu `WriteLineWithNotification` działania, autor przepływu pracy określa żądaną logikę niestandardową w ramach akcji działania <xref:System.Activities.ActivityDelegate.Handler%2A> . W tym przykładzie zostanie utworzony przepływ pracy, który używa `WriteLineWithNotification` działania, a <xref:System.Activities.Statements.WriteLine> działanie jest używane jako <xref:System.Activities.ActivityDelegate.Handler%2A> .

[!code-csharp[CFX_ActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#2)]

Istnieje wiele wersji ogólnych <xref:System.Activities.Statements.InvokeAction%601> i <xref:System.Activities.ActivityAction%601> dostarczonych do przekazywania co najmniej jednego argumentu.

## <a name="using-activityfunc"></a>Korzystanie z ActivityFunc

<xref:System.Activities.ActivityAction%601> jest przydatne, gdy nie ma wartości wyniku działania i <xref:System.Activities.ActivityFunc%601> jest używana w przypadku zwrócenia wartości wyniku. Podczas tworzenia niestandardowego działania, które definiuje <xref:System.Activities.ActivityFunc%601> , należy użyć <xref:System.Activities.Expressions.InvokeFunc%601> do modelowania wywołania tego elementu <xref:System.Activities.ActivityFunc%601> . W poniższym przykładzie `WriteFillerText` zdefiniowano działanie. Aby podać tekst wypełniający, <xref:System.Activities.Expressions.InvokeFunc%601> jest określany jako argument typu integer i ma wynik ciąg. Po pobraniu tekstu Filler jest on wyświetlany w konsoli programu przy użyciu <xref:System.Activities.Statements.WriteLine> działania.

[!code-csharp[CFX_ActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#3)]

Aby podać tekst, należy użyć działania, które przyjmuje jeden `int` argument i ma wynik ciąg. Ten przykład pokazuje `TextGenerator` działanie spełniające te wymagania.

[!code-csharp[CFX_ActivityExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#4)]

Aby użyć `TextGenerator` działania z `WriteFillerText` działaniem, określ je jako <xref:System.Activities.ActivityDelegate.Handler%2A> .

[!code-csharp[CFX_ActivityExample#5](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#5)]
