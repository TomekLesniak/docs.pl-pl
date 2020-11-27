---
title: 'Punkt końcowy: Wywołania zwracające błędy'
ms.date: 03/30/2017
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
ms.openlocfilehash: da8f771e93a9457944046dfe84a1a7a455388d77
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250128"
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="03fd4-102">Punkt końcowy: Wywołania zwracające błędy</span><span class="sxs-lookup"><span data-stu-id="03fd4-102">Endpoint: Calls Faulted</span></span>

<span data-ttu-id="03fd4-103">Nazwa licznika: wywołania są błędne.</span><span class="sxs-lookup"><span data-stu-id="03fd4-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="03fd4-104">Opis</span><span class="sxs-lookup"><span data-stu-id="03fd4-104">Description</span></span>  

 <span data-ttu-id="03fd4-105">Liczba wywołań tego punktu końcowego, które zwróciły błędy.</span><span class="sxs-lookup"><span data-stu-id="03fd4-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="03fd4-106">W aplikacjach Windows Communication Foundation (WCF) metody usługi komunikują przetwarzanie informacji o błędach przy użyciu komunikatów błędów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="03fd4-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="03fd4-107">Błędy protokołu SOAP to typy komunikatów, które są zawarte w metadanych dla operacji usługi, dlatego należy utworzyć kontrakt błędów, którego klienci mogą używać do bardziej niezawodnego lub interaktywnego wykonania.</span><span class="sxs-lookup"><span data-stu-id="03fd4-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="03fd4-108">Ponieważ błędy protokołu SOAP są wyrażane dla klientów w formularzu XML, są one wysoce interoperacyjne.</span><span class="sxs-lookup"><span data-stu-id="03fd4-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03fd4-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="03fd4-109">See also</span></span>

- [<span data-ttu-id="03fd4-110">Określanie i obsługa błędów w kontraktach i usługach</span><span class="sxs-lookup"><span data-stu-id="03fd4-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
