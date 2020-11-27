---
title: Komunikacja asynchroniczna
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: db5a8f415479967d7579357bd0c8058c7fb961c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255848"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="c8a53-102">Komunikacja asynchroniczna</span><span class="sxs-lookup"><span data-stu-id="c8a53-102">Asynchronous Communication</span></span>

<span data-ttu-id="c8a53-103">W tym przykładzie pokazano, jak komunikacja między dwiema różnymi usługami Windows Workflow Foundation (WF) odbywa się domyślnie asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="c8a53-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="c8a53-104">Demonstracje</span><span class="sxs-lookup"><span data-stu-id="c8a53-104">Demonstrates</span></span>  

 <span data-ttu-id="c8a53-105">Asynchroniczna komunikacja między [!INCLUDE[wf1](../../../../includes/wf1-md.md)] usługami.</span><span class="sxs-lookup"><span data-stu-id="c8a53-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="c8a53-106">Dyskusja</span><span class="sxs-lookup"><span data-stu-id="c8a53-106">Discussion</span></span>  

 <span data-ttu-id="c8a53-107">Ten przykład pokazuje, jak komunikacja między [!INCLUDE[wf1](../../../../includes/wf1-md.md)] aplikacjami odbywa się asynchronicznie przy użyciu działań dotyczących komunikatów dostarczonych przez .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8a53-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="c8a53-108">Ten przykład składa się z trzech następujących projektów.</span><span class="sxs-lookup"><span data-stu-id="c8a53-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="c8a53-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="c8a53-109">CreditCheckService</span></span>  
 <span data-ttu-id="c8a53-110">Ta usługa otrzymuje wynik kredytowy określonej osoby lub wartość elementu do pobrania, a następnie decyduje o tym, czy kredyt został udzielony.</span><span class="sxs-lookup"><span data-stu-id="c8a53-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="c8a53-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="c8a53-111">RentalApprovalService</span></span>  
 <span data-ttu-id="c8a53-112">Ta usługa otrzymuje aplikację od osoby, która jest w trakcie pewnego kredytu.</span><span class="sxs-lookup"><span data-stu-id="c8a53-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="c8a53-113">Ta usługa komunikuje się asynchronicznie z, `CreditCheckService` Aby określić, czy aplikacja kredytowa jest ważna.</span><span class="sxs-lookup"><span data-stu-id="c8a53-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="c8a53-114">Klient</span><span class="sxs-lookup"><span data-stu-id="c8a53-114">Client</span></span>  
 <span data-ttu-id="c8a53-115">Klient komunikuje się synchronicznie z informacją o tym, `RentalApprovalService` czy środki zostały zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="c8a53-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c8a53-116">Aby skonfigurować, skompilować i uruchomić przykład</span><span class="sxs-lookup"><span data-stu-id="c8a53-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c8a53-117">Kliknij prawym przyciskiem myszy rozwiązanie **AsynchronousCommunication** i wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="c8a53-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="c8a53-118">W obszarze **wspólne właściwości** wybierz pozycję **projekt startowy**, a następnie wybierz opcję **wiele projektów startowych**.</span><span class="sxs-lookup"><span data-stu-id="c8a53-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="c8a53-119">Przenieś **RentalApprovalService** do pierwszej pozycji na liście, a następnie **CreditCheckService**, po którym następuje **Klient**.</span><span class="sxs-lookup"><span data-stu-id="c8a53-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="c8a53-120">Ustaw akcję **startową** dla wszystkich trzech projektów.</span><span class="sxs-lookup"><span data-stu-id="c8a53-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="c8a53-121">Kliknij przycisk **OK**, a następnie naciśnij klawisz F5, aby uruchomić przykład.</span><span class="sxs-lookup"><span data-stu-id="c8a53-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c8a53-122">Przykłady mogą być już zainstalowane na komputerze.</span><span class="sxs-lookup"><span data-stu-id="c8a53-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c8a53-123">Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).</span><span class="sxs-lookup"><span data-stu-id="c8a53-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c8a53-124">Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady.</span><span class="sxs-lookup"><span data-stu-id="c8a53-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c8a53-125">Ten przykład znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="c8a53-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
