---
title: Wywołania zwracające błędy
ms.date: 03/30/2017
ms.assetid: bb9e8045-6aeb-4b7f-a825-8283c44252a1
ms.openlocfilehash: cfd829c6229f4fb483e18cfcecf4d484fad64409
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271411"
---
# <a name="calls-faulted"></a><span data-ttu-id="cffc5-102">Wywołania zwracające błędy</span><span class="sxs-lookup"><span data-stu-id="cffc5-102">Calls Faulted</span></span>

<span data-ttu-id="cffc5-103">Nazwa licznika: wywołania z błędami</span><span class="sxs-lookup"><span data-stu-id="cffc5-103">Counter Name: Calls Faulted</span></span>  
  
## <a name="description"></a><span data-ttu-id="cffc5-104">Opis</span><span class="sxs-lookup"><span data-stu-id="cffc5-104">Description</span></span>  

 <span data-ttu-id="cffc5-105">Liczba wywołań tej operacji, które zwróciły błędy.</span><span class="sxs-lookup"><span data-stu-id="cffc5-105">Number of calls to this operation that returned faults.</span></span> <span data-ttu-id="cffc5-106">W aplikacjach Windows Communication Foundation (WCF) metody usługi komunikują przetwarzanie informacji o błędach przy użyciu komunikatów błędów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="cffc5-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="cffc5-107">Błędy protokołu SOAP to typy komunikatów, które są zawarte w metadanych dla operacji usługi, dlatego należy utworzyć kontrakt błędów, którego klienci mogą używać do bardziej niezawodnego lub interaktywnego wykonania.</span><span class="sxs-lookup"><span data-stu-id="cffc5-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="cffc5-108">Ponieważ błędy protokołu SOAP są wyrażane dla klientów w formularzu XML, są one wysoce interoperacyjne.</span><span class="sxs-lookup"><span data-stu-id="cffc5-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffc5-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cffc5-109">See also</span></span>

- [<span data-ttu-id="cffc5-110">Określanie i obsługa błędów w kontraktach i usługach</span><span class="sxs-lookup"><span data-stu-id="cffc5-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
