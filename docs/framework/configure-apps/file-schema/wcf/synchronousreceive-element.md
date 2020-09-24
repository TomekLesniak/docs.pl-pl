---
title: <synchronousReceive>, element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 2073d115dd87d513a6e48b8b585fed4b49d5bb32
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157177"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="b7d9c-102">\<synchronousReceive>, element</span><span class="sxs-lookup"><span data-stu-id="b7d9c-102">\<synchronousReceive> element</span></span>

<span data-ttu-id="b7d9c-103">Ten element konfiguracji służy do określania zachowania w czasie wykonywania w przypadku otrzymywania wiadomości w usłudze lub aplikacji klienckiej.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="b7d9c-104">Nie ma żadnych atrybutów ani elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="b7d9c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b7d9c-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7d9c-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="b7d9c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b7d9c-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7d9c-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="b7d9c-108">Attributes</span></span>  

 <span data-ttu-id="b7d9c-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b7d9c-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="b7d9c-110">Child Elements</span></span>  

 <span data-ttu-id="b7d9c-111">Brak.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7d9c-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="b7d9c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b7d9c-113">Element</span><span class="sxs-lookup"><span data-stu-id="b7d9c-113">Element</span></span>|<span data-ttu-id="b7d9c-114">Opis</span><span class="sxs-lookup"><span data-stu-id="b7d9c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b7d9c-115">Określa zachowanie punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d9c-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b7d9c-116">Remarks</span></span>  

 <span data-ttu-id="b7d9c-117">Użyj tego zachowania, aby nakazać odbiornikowi kanału użycie synchronicznego odbioru zamiast domyślnego, asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="b7d9c-118">Windows Communication Foundation (WCF) wystawia nowy wątek do pompy dla każdego zaakceptowanego kanału.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="b7d9c-119">Jeśli istnieje wiele kanałów, istnieje możliwość uruchomienia poza wątkiem.</span><span class="sxs-lookup"><span data-stu-id="b7d9c-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d9c-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b7d9c-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
