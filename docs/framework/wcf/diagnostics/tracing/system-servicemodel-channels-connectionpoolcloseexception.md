---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286958"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="d287d-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="d287d-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>

<span data-ttu-id="d287d-103">Wystąpił wyjątek podczas zamykania połączeń z tej puli połączeń.</span><span class="sxs-lookup"><span data-stu-id="d287d-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d287d-104">Opis</span><span class="sxs-lookup"><span data-stu-id="d287d-104">Description</span></span>  

 <span data-ttu-id="d287d-105">Ten ślad poziomu błędu wskazuje, że wystąpił błąd podczas zamykania pul połączeń używanych przez funkcję puli połączeń Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d287d-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="d287d-106">Jedną z możliwych przyczyn jest to nieudane zamknięcie połączenia w puli lub zestaw połączeń w puli w ramach CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="d287d-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="d287d-107">Gdy ten wyjątek jest zgłaszany, wszystkie pozostałe niezamknięte połączenia w tej puli są przerywane; niezamknięte połączenia w innych pulach są porzucane.</span><span class="sxs-lookup"><span data-stu-id="d287d-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d287d-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d287d-108">See also</span></span>

- [<span data-ttu-id="d287d-109">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="d287d-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="d287d-110">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="d287d-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d287d-111">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="d287d-111">Administration and Diagnostics</span></span>](../index.md)
