---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 9ec25138130311f8cdd9af8fb32a3e80fb33ed68
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258091"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="034d1-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="034d1-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>

<span data-ttu-id="034d1-103">Wymagany jest certyfikat klienta.</span><span class="sxs-lookup"><span data-stu-id="034d1-103">Client certificate is required.</span></span> <span data-ttu-id="034d1-104">W żądaniu nie znaleziono żadnego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="034d1-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="034d1-105">Opis</span><span class="sxs-lookup"><span data-stu-id="034d1-105">Description</span></span>  

 <span data-ttu-id="034d1-106">Ten ślad wskazuje, że odbiornik protokołu HTTPS otrzymał żądanie HTTPS, które nie zostało skojarzone z certyfikatem klienta.</span><span class="sxs-lookup"><span data-stu-id="034d1-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="034d1-107">Ponieważ odbiornik został skonfigurowany tak, aby wymagał certyfikatów klienta na wszystkich żądaniach HTTPS, odbiornik nie mógł zweryfikować autentyczności klienta.</span><span class="sxs-lookup"><span data-stu-id="034d1-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034d1-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="034d1-108">See also</span></span>

- [<span data-ttu-id="034d1-109">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="034d1-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="034d1-110">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="034d1-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="034d1-111">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="034d1-111">Administration and Diagnostics</span></span>](../index.md)
