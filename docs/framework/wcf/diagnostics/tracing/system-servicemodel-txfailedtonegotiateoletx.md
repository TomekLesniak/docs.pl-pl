---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7b468a57409e9a473a5bbf8e3324435e65e8c60b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295317"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="32541-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="32541-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>

<span data-ttu-id="32541-103">Nie można ukończyć negocjacji protokołu OleTransactions dla określonego kontekstu koordynacji.</span><span class="sxs-lookup"><span data-stu-id="32541-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="32541-104">Opis</span><span class="sxs-lookup"><span data-stu-id="32541-104">Description</span></span>  

 <span data-ttu-id="32541-105">Śledzone w przypadku, gdy transakcja przychodząca z informacjami OleTx nie może używać dołączonych informacji OleTx i zostanie przywrócona w zamian przy użyciu protokołu WS-AT.</span><span class="sxs-lookup"><span data-stu-id="32541-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="32541-106">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="32541-106">Troubleshooting</span></span>  

 <span data-ttu-id="32541-107">Wskazuje potencjalny problem z komunikacją RPC usługi MSDTC między maszynami.</span><span class="sxs-lookup"><span data-stu-id="32541-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="32541-108">Jeśli wiele z tych śladów jest wyświetlanych w dzienniku, może wynikać drastyczne zmniejszenie wydajności.</span><span class="sxs-lookup"><span data-stu-id="32541-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="32541-109">Jeśli OleTx nie jest wymagana, ustaw wartość `OleTxUpgradeEnabled` 0 w konfiguracji rejestru WS-AT.</span><span class="sxs-lookup"><span data-stu-id="32541-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32541-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="32541-110">See also</span></span>

- [<span data-ttu-id="32541-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="32541-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="32541-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="32541-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="32541-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="32541-113">Administration and Diagnostics</span></span>](../index.md)
