---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235119"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="621b5-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="621b5-102">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="621b5-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="621b5-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="621b5-104">Opis</span><span class="sxs-lookup"><span data-stu-id="621b5-104">Description</span></span>  

 <span data-ttu-id="621b5-105">Wątki zostały przełączone podczas przetwarzania komunikatu.</span><span class="sxs-lookup"><span data-stu-id="621b5-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="621b5-106">Przetwarzanie komunikatów można wstrzymać z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="621b5-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="621b5-107">Właściwość ConcurrencyMode jest pojedyncza lub współużytkowana, a usługa przetwarza inną wiadomość.</span><span class="sxs-lookup"><span data-stu-id="621b5-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="621b5-108">Transakcja jest włączona, a usługa przetwarza inną transakcję.</span><span class="sxs-lookup"><span data-stu-id="621b5-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="621b5-109">Kontekst synchronizacji nie jest bieżący.</span><span class="sxs-lookup"><span data-stu-id="621b5-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621b5-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="621b5-110">See also</span></span>

- [<span data-ttu-id="621b5-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="621b5-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="621b5-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="621b5-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="621b5-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="621b5-113">Administration and Diagnostics</span></span>](../index.md)
