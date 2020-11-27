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
# <a name="asynchronous-communication"></a>Komunikacja asynchroniczna

W tym przykładzie pokazano, jak komunikacja między dwiema różnymi usługami Windows Workflow Foundation (WF) odbywa się domyślnie asynchronicznie.  
  
## <a name="demonstrates"></a>Demonstracje  

 Asynchroniczna komunikacja między [!INCLUDE[wf1](../../../../includes/wf1-md.md)] usługami.  
  
## <a name="discussion"></a>Dyskusja  

 Ten przykład pokazuje, jak komunikacja między [!INCLUDE[wf1](../../../../includes/wf1-md.md)] aplikacjami odbywa się asynchronicznie przy użyciu działań dotyczących komunikatów dostarczonych przez .NET Framework.  
  
 Ten przykład składa się z trzech następujących projektów.  
  
 CreditCheckService  
 Ta usługa otrzymuje wynik kredytowy określonej osoby lub wartość elementu do pobrania, a następnie decyduje o tym, czy kredyt został udzielony.  
  
 RentalApprovalService  
 Ta usługa otrzymuje aplikację od osoby, która jest w trakcie pewnego kredytu. Ta usługa komunikuje się asynchronicznie z, `CreditCheckService` Aby określić, czy aplikacja kredytowa jest ważna.  
  
 Klient  
 Klient komunikuje się synchronicznie z informacją o tym, `RentalApprovalService` czy środki zostały zatwierdzone.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić przykład  
  
1. Kliknij prawym przyciskiem myszy rozwiązanie **AsynchronousCommunication** i wybierz polecenie **Właściwości**.  
  
2. W obszarze **wspólne właściwości** wybierz pozycję **projekt startowy**, a następnie wybierz opcję **wiele projektów startowych**.  
  
3. Przenieś **RentalApprovalService** do pierwszej pozycji na liście, a następnie **CreditCheckService**, po którym następuje **Klient**. Ustaw akcję **startową** dla wszystkich trzech projektów.  
  
4. Kliknij przycisk **OK**, a następnie naciśnij klawisz F5, aby uruchomić przykład.  
  
> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
