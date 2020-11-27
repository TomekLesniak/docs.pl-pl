---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: e39ca97bdefafee840206036f89e8b165609516a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263012"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="531e7-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="531e7-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>

<span data-ttu-id="531e7-103">Występuje, gdy nie można bezpiecznie zamknąć usługi i została przerwana.</span><span class="sxs-lookup"><span data-stu-id="531e7-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="531e7-104">Opis</span><span class="sxs-lookup"><span data-stu-id="531e7-104">Description</span></span>  

 <span data-ttu-id="531e7-105">Ten kod błędu pojawia się tylko w pliku dziennika.</span><span class="sxs-lookup"><span data-stu-id="531e7-105">This error code only appears in the log file.</span></span> <span data-ttu-id="531e7-106">Zwykle wskazuje to na błąd programowania, na przykład podczas próby zamknięcia usługi po wywołaniu metody Abort.</span><span class="sxs-lookup"><span data-stu-id="531e7-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="531e7-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="531e7-107">Troubleshooting</span></span>  

 <span data-ttu-id="531e7-108">Sprawdź kod źródłowy aplikacji.</span><span class="sxs-lookup"><span data-stu-id="531e7-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531e7-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="531e7-109">See also</span></span>

- [<span data-ttu-id="531e7-110">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="531e7-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="531e7-111">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="531e7-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="531e7-112">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="531e7-112">Administration and Diagnostics</span></span>](../index.md)
