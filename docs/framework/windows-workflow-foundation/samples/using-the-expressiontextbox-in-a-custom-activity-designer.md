---
title: Używanie elementu ExpressionTextBox w projektancie działań niestandardowych
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: dfb53096be59abd9924a024880d4125ca774d4b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267497"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Używanie elementu ExpressionTextBox w projektancie działań niestandardowych

Ten przykład pokazuje, jak używać <xref:System.Activities.Presentation.View.ExpressionTextBox> w niestandardowym projektancie działań. Działanie niestandardowe, `MultiAssign` , przypisuje dwie wartości ciągu do dwóch zmiennych ciągu. Niektóre <xref:System.Activities.Presentation.View.ExpressionTextBox> formanty są powiązane z <xref:System.Activities.InArgument> s i z pewnymi powiązaniami z <xref:System.Activities.OutArgument> .

## <a name="sample-details"></a>Przykładowe szczegóły

 `ArgumentToExpressionConverter`Jest konwerterem typów używanym podczas wiązania wyrażeń z argumentami. Wartość `ConverterParameter` musi być ustawiona na `In` lub odpowiednio `Out` . `InOut` nie jest obsługiwana.

 Ten `UseLocationExpression` atrybut jest używany w `OutArgument` s, aby określić, że wyrażenie powinno być wyrażeniem L-wartości ("lewa wartość" lub "wartość lokalizacji"). W większości przypadków wyrażenie L-wartości jest prawidłowym identyfikatorem Visual Basic używanym do wskazania, że `OutArgument` zwracana jest nazwa zmiennej lub argumentu.

 `MaxLines`Atrybut jest ustawiony na jeden w tym przykładzie i `MinLines` nie jest ustawiony. Oznacza to, że <xref:System.Activities.Presentation.View.ExpressionTextBox> jest to stały rozmiar jednego wiersza niezależnie od ilości tekstu wpisanego przez użytkownika. Aby umożliwić <xref:System.Activities.Presentation.View.ExpressionTextBox> powiększanie się w celu dopasowania danych przez użytkownika, ustaw wartość `MaxLines` większą niż `MinLines` .

 Element ExpressionTextBox może być powiązany tylko z argumentami i nie można go powiązać z właściwościami środowiska CLR.

#### <a name="to-use-this-sample"></a>Aby użyć tego przykładu

1. Za pomocą programu Visual Studio 2010 Otwórz plik ExpressionTextBoxSample. sln.

2. Aby skompilować rozwiązanie, naciśnij klawisze CTRL + SHIFT + B.

#### <a name="to-run-this-sample"></a>Aby uruchomić ten przykład

1. Dodaj nową aplikację konsoli przepływu pracy do rozwiązania.

2. Dodaj odwołanie do projektu **ExpressionTextBoxSample** z nowego projektu aplikacji konsolowej przepływu pracy.

3. Skompiluj rozwiązanie.

4. Przeciągnij działanie **wieloprzypisane** z przybornika i upuść je w przepływie pracy.

> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [Tworzenie aplikacji przy użyciu Projektanta przepływu pracy](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
