---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 97f22a01df84c39915f74fa7677e5dd18154b952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256225"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="977d6-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="977d6-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>

<span data-ttu-id="977d6-103">Nie można odebrać wiadomości kanałem HTTP.</span><span class="sxs-lookup"><span data-stu-id="977d6-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="977d6-104">Opis</span><span class="sxs-lookup"><span data-stu-id="977d6-104">Description</span></span>  

 <span data-ttu-id="977d6-105">Ten ślad może być emitowany jako ostrzeżenie lub błąd.</span><span class="sxs-lookup"><span data-stu-id="977d6-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="977d6-106">W obu przypadkach ślad jest emitowany, gdy nie znaleziono zgodnego odbiornika dla przychodzącego żądania HTTP, a żądanie HTTP zostanie odrzucone.</span><span class="sxs-lookup"><span data-stu-id="977d6-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="977d6-107">Może się tak zdarzyć, ponieważ czasownik HTTP żądania nie został rozpoznany przez żaden odbiornik HTTP lub żaden odbiornik nie nasłuchuje na adresie, którego dotyczy żądanie.</span><span class="sxs-lookup"><span data-stu-id="977d6-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="977d6-108">Ślad jest emitowany jako ostrzeżenie w przypadku samodzielnego użycia i jako błąd, gdy usługa jest hostowana w usługach IIS.</span><span class="sxs-lookup"><span data-stu-id="977d6-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="977d6-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="977d6-109">See also</span></span>

- [<span data-ttu-id="977d6-110">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="977d6-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="977d6-111">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="977d6-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="977d6-112">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="977d6-112">Administration and Diagnostics</span></span>](../index.md)
