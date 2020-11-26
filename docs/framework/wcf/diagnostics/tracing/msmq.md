---
title: Usługa MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 7ef31a188e1564da47ea1e7323cdd4cd5ef5be60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236679"
---
# <a name="msmq"></a><span data-ttu-id="034d3-102">Usługa MSMQ</span><span class="sxs-lookup"><span data-stu-id="034d3-102">MSMQ</span></span>

<span data-ttu-id="034d3-103">W aplikacji MSMQ żadne dodatkowe działanie nie jest transferowane z kolejki w kolejce do usługi MSMQ i z usługi MSMQ do kanału znajdującego się w kolejce.</span><span class="sxs-lookup"><span data-stu-id="034d3-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="034d3-104">Ponadto identyfikator wiadomości MSMQ i Identyfikator komunikatu protokołu SOAP (wraz z IDENTYFIKATORem działania, jeśli taki istnieje) są śledzone jako część śladów kanałów umieszczonych w kolejce podczas operacji wysyłania.</span><span class="sxs-lookup"><span data-stu-id="034d3-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="034d3-105">Identyfikator wiadomości MSMQ i Identyfikator komunikatu protokołu SOAP (wraz z IDENTYFIKATORem działania, jeśli taki istnieje) są śledzone jako część śladów kanałów umieszczonych w kolejce dla operacji odbioru.</span><span class="sxs-lookup"><span data-stu-id="034d3-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="034d3-106">Wymagane transfery dla operacji Receive są wykonywane podobnie jak w przypadku wszystkich innych operacji transportu (odbieraj bajty — >procesu > operacji).</span><span class="sxs-lookup"><span data-stu-id="034d3-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
