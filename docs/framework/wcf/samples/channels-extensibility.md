---
title: Rozszerzalność kanałów
ms.date: 03/30/2017
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
ms.openlocfilehash: 1a734c305e2a6f2fc759647ab5bdf380f7c7eeee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253844"
---
# <a name="channels-extensibility"></a><span data-ttu-id="d5afe-102">Rozszerzalność kanałów</span><span class="sxs-lookup"><span data-stu-id="d5afe-102">Channels Extensibility</span></span>

<span data-ttu-id="d5afe-103">Ta sekcja zawiera przykłady demonstrujące kanały niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="d5afe-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5afe-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="d5afe-104">In This Section</span></span>  

 [<span data-ttu-id="d5afe-105">Lokalny kanał</span><span class="sxs-lookup"><span data-stu-id="d5afe-105">Local Channel</span></span>](local-channel.md)  
 <span data-ttu-id="d5afe-106">Pokazuje kanał lokalny, kanał transportu WCF używany do komunikacji w ramach tej samej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d5afe-106">Demonstrates the local channel, a WCF transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="d5afe-107">Niezawodny bezpieczny profil</span><span class="sxs-lookup"><span data-stu-id="d5afe-107">Reliable Secure Profile</span></span>](reliable-secure-profile.md)  
 <span data-ttu-id="d5afe-108">Pokazuje, jak tworzyć usługi WCF i niezawodne bezpieczne profile (RSP).</span><span class="sxs-lookup"><span data-stu-id="d5afe-108">Demonstrates how to compose WCF and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="d5afe-109">Niestandardowy dyspozytor kanału</span><span class="sxs-lookup"><span data-stu-id="d5afe-109">Custom Channel Dispatcher</span></span>](custom-channel-dispatcher.md)  
 <span data-ttu-id="d5afe-110">Demonstruje sposób tworzenia stosu kanału w sposób niestandardowy przez implementację <xref:System.ServiceModel.ServiceHostBase> bezpośrednio i sposób tworzenia niestandardowego dyspozytora kanału w środowisku hosta sieci Web.</span><span class="sxs-lookup"><span data-stu-id="d5afe-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="d5afe-111">Kanał dzielący na fragmenty</span><span class="sxs-lookup"><span data-stu-id="d5afe-111">Chunking Channel</span></span>](chunking-channel.md)  
 <span data-ttu-id="d5afe-112">Pokazuje, jak ograniczyć ilość pamięci używanej do buforowania dużych komunikatów wysyłanych za pomocą programu WCF.</span><span class="sxs-lookup"><span data-stu-id="d5afe-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using WCF.</span></span>
  
 [<span data-ttu-id="d5afe-113">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="d5afe-113">HttpCookieSession</span></span>](httpcookiesession.md)  
 <span data-ttu-id="d5afe-114">Pokazuje, jak utworzyć niestandardowy kanał protokołu, aby używać plików cookie protokołu HTTP do zarządzania sesją.</span><span class="sxs-lookup"><span data-stu-id="d5afe-114">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="d5afe-115">Niestandardowy element przechwytujący komunikaty</span><span class="sxs-lookup"><span data-stu-id="d5afe-115">Custom Message Interceptor</span></span>](custom-message-interceptor.md)  
 <span data-ttu-id="d5afe-116">Demonstruje sposób implementacji elementu niestandardowego powiązania, który tworzy fabryki kanałów i odbiorników kanałów do przechwytywania wszystkich komunikatów przychodzących i wychodzących w określonym punkcie w stosie czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d5afe-116">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
