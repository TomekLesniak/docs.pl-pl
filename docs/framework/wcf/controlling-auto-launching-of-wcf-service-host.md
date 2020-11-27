---
title: Kontrolowanie automatycznego uruchamiania hosta programu WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2033e693003d0b50bcdada428e4a5f451b3ad67e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255081"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="54817-102">Kontrolowanie automatycznego uruchamiania hosta programu WCF</span><span class="sxs-lookup"><span data-stu-id="54817-102">Controlling Auto-launching of WCF Service Host</span></span>

<span data-ttu-id="54817-103">Można kontrolować możliwość uruchamiania Windows Communication Foundation (WcfSvcHost.exe) dla projektu biblioteki usług WCF w przypadku debugowania innego projektu w tym samym rozwiązaniu programu Visual Studio zawierającym wiele projektów.</span><span class="sxs-lookup"><span data-stu-id="54817-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="54817-104">Aby to zrobić, kliknij prawym przyciskiem myszy projekt usługi WCF w **Eksplorator rozwiązań**, wybierz polecenie **Właściwości**, a następnie kliknij kartę **Opcje WCF** . **Uruchom hosta usługi WCF podczas debugowania innego projektu w tym samym rozwiązaniu** pole wyboru jest domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="54817-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="54817-105">Możesz wyczyścić to pole, aby Host usługi WCF dla danego projektu nie był uruchamiany, gdy inny projekt jest debugowany w tym samym rozwiązaniu.</span><span class="sxs-lookup"><span data-stu-id="54817-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="54817-106">To zachowanie nie ma wpływu na Debugowanie F5 ani Dodaj odwołanie do usługi funkcji dla tego projektu.</span><span class="sxs-lookup"><span data-stu-id="54817-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="54817-107">Ta opcja jest dostępna dla następujących projektów:</span><span class="sxs-lookup"><span data-stu-id="54817-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="54817-108">Projekt biblioteki usług WCF.</span><span class="sxs-lookup"><span data-stu-id="54817-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="54817-109">Projekt biblioteki usługi sekwencyjnego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="54817-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="54817-110">Projekt biblioteki usługi przepływu pracy automatu Stanów.</span><span class="sxs-lookup"><span data-stu-id="54817-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="54817-111">Projekt biblioteki usługi zespolonej.</span><span class="sxs-lookup"><span data-stu-id="54817-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54817-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54817-112">See also</span></span>

- [<span data-ttu-id="54817-113">Host usługi WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="54817-113">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
