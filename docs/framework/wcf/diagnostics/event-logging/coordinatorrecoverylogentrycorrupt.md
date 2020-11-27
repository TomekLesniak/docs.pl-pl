---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295366"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="dbe7a-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="dbe7a-102">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="dbe7a-103">Identyfikator: 139</span><span class="sxs-lookup"><span data-stu-id="dbe7a-103">Id: 139</span></span>  
  
 <span data-ttu-id="dbe7a-104">Ważność: błąd</span><span class="sxs-lookup"><span data-stu-id="dbe7a-104">Severity: Error</span></span>  
  
 <span data-ttu-id="dbe7a-105">Kategoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="dbe7a-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="dbe7a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="dbe7a-106">Description</span></span>  

 <span data-ttu-id="dbe7a-107">To zdarzenie wskazuje, że wpis dziennika odzyskiwania koordynatora został uszkodzony i nie można go zdeserializować.</span><span class="sxs-lookup"><span data-stu-id="dbe7a-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="dbe7a-108">Przyczyną tego błędu może być utrata danych.</span><span class="sxs-lookup"><span data-stu-id="dbe7a-108">Data loss may result from this error.</span></span> <span data-ttu-id="dbe7a-109">Zdarzenie Wyświetla identyfikator transakcji, dane odzyskiwania (kodowane algorytmem Base64), wyjątek, nazwę procesu i identyfikator procesu.</span><span class="sxs-lookup"><span data-stu-id="dbe7a-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe7a-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dbe7a-110">See also</span></span>

- [<span data-ttu-id="dbe7a-111">Rejestrowanie zdarzeń</span><span class="sxs-lookup"><span data-stu-id="dbe7a-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="dbe7a-112">Informacje ogólne o zdarzeniach</span><span class="sxs-lookup"><span data-stu-id="dbe7a-112">Events General Reference</span></span>](events-general-reference.md)
