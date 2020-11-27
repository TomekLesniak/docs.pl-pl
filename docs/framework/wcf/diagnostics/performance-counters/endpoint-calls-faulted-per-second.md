---
title: 'Punkt końcowy: Wywołania zwracające błędy na sekundę'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: e69e37de9605afd4806fd628088948d0d69291da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250167"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="c95d2-102">Punkt końcowy: Wywołania zwracające błędy na sekundę</span><span class="sxs-lookup"><span data-stu-id="c95d2-102">Endpoint: Calls Faulted Per Second</span></span>

<span data-ttu-id="c95d2-103">Nazwa licznika: wywołania z błędami na sekundę.</span><span class="sxs-lookup"><span data-stu-id="c95d2-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c95d2-104">Opis</span><span class="sxs-lookup"><span data-stu-id="c95d2-104">Description</span></span>  

 <span data-ttu-id="c95d2-105">Liczba wywołań, które zwróciły błędy do tego punktu końcowego w drugim.</span><span class="sxs-lookup"><span data-stu-id="c95d2-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="c95d2-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="c95d2-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c95d2-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="c95d2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="c95d2-108">W aplikacjach Windows Communication Foundation (WCF) metody usługi komunikują przetwarzanie informacji o błędach przy użyciu komunikatów błędów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="c95d2-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="c95d2-109">Błędy protokołu SOAP to typy komunikatów, które są zawarte w metadanych dla operacji usługi, dlatego należy utworzyć kontrakt błędów, którego klienci mogą używać do bardziej niezawodnego lub interaktywnego wykonania.</span><span class="sxs-lookup"><span data-stu-id="c95d2-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="c95d2-110">Ponieważ błędy protokołu SOAP są wyrażane dla klientów w formularzu XML, są one wysoce interoperacyjne.</span><span class="sxs-lookup"><span data-stu-id="c95d2-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95d2-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c95d2-111">See also</span></span>

- [<span data-ttu-id="c95d2-112">Określanie i obsługa błędów w kontraktach i usługach</span><span class="sxs-lookup"><span data-stu-id="c95d2-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
