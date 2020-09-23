---
title: Inny dziennik zdarzeń zarejestrował już źródło o tej nazwie
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: 333c28036e2d1b7514c7370b98ff70a6d195a9dd
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058394"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="6a9b4-102">Inny dziennik zdarzeń zarejestrował już źródło o tej nazwie</span><span class="sxs-lookup"><span data-stu-id="6a9b4-102">Another event log has already registered a source with this name</span></span>

<span data-ttu-id="6a9b4-103">Podjęto próbę zapisania wpisu w dzienniku zdarzeń, w którym określone źródło jest zarejestrowane w innym dzienniku zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="6a9b4-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="6a9b4-104">Należy ustawić <xref:System.Diagnostics.EventLog.Source%2A> Właściwość <xref:System.Diagnostics.EventLog> wystąpienia składnika, zanim składnik zapisze wpis w dzienniku.</span><span class="sxs-lookup"><span data-stu-id="6a9b4-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="6a9b4-105">W takim przypadku system sprawdza, czy określone źródło jest zarejestrowane w dzienniku zdarzeń, do którego składnik jest zapisywany, i wywołuje w <xref:System.Diagnostics.EventLog.CreateEventSource%2A> razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="6a9b4-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6a9b4-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="6a9b4-106">To correct this error</span></span>  
  
1. <span data-ttu-id="6a9b4-107">Usuń skojarzenie źródła z pierwszym dziennikiem przy użyciu <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> metody lub.</span><span class="sxs-lookup"><span data-stu-id="6a9b4-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="6a9b4-108">Zarejestruj źródło w nowym dzienniku.</span><span class="sxs-lookup"><span data-stu-id="6a9b4-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9b4-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6a9b4-109">See also</span></span>

- [<span data-ttu-id="6a9b4-110">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="6a9b4-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
