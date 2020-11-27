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
# <a name="using-the-pick-activity"></a><span data-ttu-id="a7ce1-102">Używanie działania Pick</span><span class="sxs-lookup"><span data-stu-id="a7ce1-102">Using the Pick Activity</span></span>

<span data-ttu-id="a7ce1-103">Ten przykład pokazuje, jak używać <xref:System.Activities.Statements.Pick> działania.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="a7ce1-104"><xref:System.Activities.Statements.Pick>Działanie zapewnia modelowania kontroli opartej na zdarzeniach.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="a7ce1-105">Zachowuje się podobnie do instrukcji języka C# `switch` , która wykonuje tylko jedną z gałęzi w `switch` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="a7ce1-106">W przeciwieństwie do `switch` instrukcji, w której rozgałęzienie jest wykonywane na podstawie wartości, <xref:System.Activities.Statements.Pick> działanie wykonuje gałąź w oparciu o zakończenie działania.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="a7ce1-107">Ten przykład poprosi użytkownika o wpisanie nazwy w konsoli w danym okresie czasu.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="a7ce1-108"><xref:System.Activities.Statements.Pick>Działanie w przykładzie ma dwie gałęzie, które są wykonywane w zależności od tego, czy użytkownik wpisze swoją nazwę w ciągu 5 sekund.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="a7ce1-109">Jeśli użytkownik wpisze swoją nazwę w ciągu 5 sekund, wykonywana jest pierwsza gałąź, która zawiera `ReadLine` działanie niestandardowe; w przeciwnym razie inna gałąź jest wykonywana, która zawiera <xref:System.Activities.Statements.Delay> działanie.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="a7ce1-110">Po wpisaniu nazwy użytkownika w konsoli programu nazwa użytkownika jest drukowana w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="a7ce1-111">Jeśli dane wejściowe nie zostaną wprowadzone w ciągu 5 sekund, Operacja przekroczyła limit czasu.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a7ce1-112">Demonstracje</span><span class="sxs-lookup"><span data-stu-id="a7ce1-112">Demonstrates</span></span>

 <span data-ttu-id="a7ce1-113"><xref:System.Activities.Statements.Pick> interakcyjn.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-113"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="a7ce1-114">Dyskusja</span><span class="sxs-lookup"><span data-stu-id="a7ce1-114">Discussion</span></span>

 <span data-ttu-id="a7ce1-115">Przykład zawiera przepływ pracy projektanta i kodowany przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-115">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="a7ce1-116">Przepływ pracy projektanta wersja projektanta przykład pokazuje, jak utworzyć przepływ pracy w projektancie.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-116">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="a7ce1-117">Dostępne są następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="a7ce1-117">The following files are included:</span></span>

- <span data-ttu-id="a7ce1-118">Program.cs: zawiera `Main` funkcję, która wykonuje przykładowy przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-118">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="a7ce1-119">ReadString.cs: niestandardowe działanie, które odczytuje niektóre dane wejściowe z konsoli.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-119">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="a7ce1-120">Sequence1. XAML: przepływ pracy utworzony przy użyciu projektanta, który używa funkcji pobrania.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-120">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="a7ce1-121">Kodowany przepływ pracy zakodowana wersja przykładu pokazuje, jak utworzyć przepływ pracy w projektancie.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-121">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="a7ce1-122">Dostępne są następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="a7ce1-122">The following files are included:</span></span>

- <span data-ttu-id="a7ce1-123">Program.cs: zawiera `Main` funkcję, która wykonuje przykładowy przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-123">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="a7ce1-124">ReadString.cs: niestandardowe działanie, które odczytuje niektóre dane wejściowe z konsoli.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-124">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="a7ce1-125">Aby użyć tego przykładu</span><span class="sxs-lookup"><span data-stu-id="a7ce1-125">To use this sample</span></span>

1. <span data-ttu-id="a7ce1-126">Za pomocą programu Visual Studio 2010 Otwórz plik rozwiązania do pobrania. sln.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-126">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="a7ce1-127">Aby skompilować rozwiązanie, naciśnij klawisze CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-127">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="a7ce1-128">Aby uruchomić rozwiązanie, naciśnij klawisz F5.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-128">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7ce1-129">Przykłady mogą być już zainstalowane na komputerze.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a7ce1-130">Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).</span><span class="sxs-lookup"><span data-stu-id="a7ce1-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a7ce1-131">Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a7ce1-132">Ten przykład znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="a7ce1-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
