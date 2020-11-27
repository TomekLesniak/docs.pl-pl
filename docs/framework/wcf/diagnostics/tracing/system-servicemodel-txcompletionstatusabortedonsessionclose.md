---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 0d8c77d01351b0c62e0186e5aee69ca70aebe15e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274325"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="39bfe-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="39bfe-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>

<span data-ttu-id="39bfe-103">Określona transakcja została przerwana, ponieważ została zakończona, gdy sesja została zamknięta i TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute będący została ustawiona na wartość false.</span><span class="sxs-lookup"><span data-stu-id="39bfe-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="39bfe-104">Opis</span><span class="sxs-lookup"><span data-stu-id="39bfe-104">Description</span></span>  

 <span data-ttu-id="39bfe-105">Śledzone, jeśli bieżąca aktywna sesja została zamknięta i transakcja nie została ukończona, a TransactionAutoCompleteOnSessionClose jest ustawiona na `false` .</span><span class="sxs-lookup"><span data-stu-id="39bfe-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="39bfe-106">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="39bfe-106">Troubleshooting</span></span>  

 <span data-ttu-id="39bfe-107">Ten ślad wskazuje potencjalną usterkę aplikacji, która powinna zostać zbadana.</span><span class="sxs-lookup"><span data-stu-id="39bfe-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bfe-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="39bfe-108">See also</span></span>

- [<span data-ttu-id="39bfe-109">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="39bfe-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="39bfe-110">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="39bfe-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="39bfe-111">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="39bfe-111">Administration and Diagnostics</span></span>](../index.md)
