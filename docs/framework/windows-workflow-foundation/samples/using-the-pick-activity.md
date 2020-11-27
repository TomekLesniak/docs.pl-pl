---
title: Używanie działania Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: df8570a61c7bfbfacc00b0896156135ecf2a0c32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267473"
---
# <a name="using-the-pick-activity"></a>Używanie działania Pick

Ten przykład pokazuje, jak używać <xref:System.Activities.Statements.Pick> działania.

 <xref:System.Activities.Statements.Pick>Działanie zapewnia modelowania kontroli opartej na zdarzeniach. Zachowuje się podobnie do instrukcji języka C# `switch` , która wykonuje tylko jedną z gałęzi w `switch` instrukcji. W przeciwieństwie do `switch` instrukcji, w której rozgałęzienie jest wykonywane na podstawie wartości, <xref:System.Activities.Statements.Pick> działanie wykonuje gałąź w oparciu o zakończenie działania.

 Ten przykład poprosi użytkownika o wpisanie nazwy w konsoli w danym okresie czasu. <xref:System.Activities.Statements.Pick>Działanie w przykładzie ma dwie gałęzie, które są wykonywane w zależności od tego, czy użytkownik wpisze swoją nazwę w ciągu 5 sekund. Jeśli użytkownik wpisze swoją nazwę w ciągu 5 sekund, wykonywana jest pierwsza gałąź, która zawiera `ReadLine` działanie niestandardowe; w przeciwnym razie inna gałąź jest wykonywana, która zawiera <xref:System.Activities.Statements.Delay> działanie. Po wpisaniu nazwy użytkownika w konsoli programu nazwa użytkownika jest drukowana w konsoli programu. Jeśli dane wejściowe nie zostaną wprowadzone w ciągu 5 sekund, Operacja przekroczyła limit czasu.

## <a name="demonstrates"></a>Demonstracje

 <xref:System.Activities.Statements.Pick> interakcyjn.

## <a name="discussion"></a>Dyskusja

 Przykład zawiera przepływ pracy projektanta i kodowany przepływ pracy.

 Przepływ pracy projektanta wersja projektanta przykład pokazuje, jak utworzyć przepływ pracy w projektancie. Dostępne są następujące pliki:

- Program.cs: zawiera `Main` funkcję, która wykonuje przykładowy przepływ pracy.

- ReadString.cs: niestandardowe działanie, które odczytuje niektóre dane wejściowe z konsoli.

- Sequence1. XAML: przepływ pracy utworzony przy użyciu projektanta, który używa funkcji pobrania.

 Kodowany przepływ pracy zakodowana wersja przykładu pokazuje, jak utworzyć przepływ pracy w projektancie. Dostępne są następujące pliki:

- Program.cs: zawiera `Main` funkcję, która wykonuje przykładowy przepływ pracy.

- ReadString.cs: niestandardowe działanie, które odczytuje niektóre dane wejściowe z konsoli.

#### <a name="to-use-this-sample"></a>Aby użyć tego przykładu

1. Za pomocą programu Visual Studio 2010 Otwórz plik rozwiązania do pobrania. sln.

2. Aby skompilować rozwiązanie, naciśnij klawisze CTRL + SHIFT + B.

3. Aby uruchomić rozwiązanie, naciśnij klawisz F5.

> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
