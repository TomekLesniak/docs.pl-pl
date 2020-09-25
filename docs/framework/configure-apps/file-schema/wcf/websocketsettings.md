---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 6cfddfb9ebfc7c3447af977e14738baabebc8fe9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177854"
---
# \<webSocketSettings>

<span data-ttu-id="27a09-101">Element konfiguracji służący do określania ustawień gniazda sieci Web.</span><span class="sxs-lookup"><span data-stu-id="27a09-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="27a09-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="27a09-102">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27a09-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="27a09-103">Attributes and Elements</span></span>  

 <span data-ttu-id="27a09-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="27a09-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27a09-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="27a09-105">Attributes</span></span>  
  
|<span data-ttu-id="27a09-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="27a09-106">Attribute</span></span>|<span data-ttu-id="27a09-107">Opis</span><span class="sxs-lookup"><span data-stu-id="27a09-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27a09-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="27a09-108">createNotificationOnConnection</span></span>|<span data-ttu-id="27a09-109">Określa, czy powiadomienie jest wysyłane po nawiązaniu połączenia.</span><span class="sxs-lookup"><span data-stu-id="27a09-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="27a09-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="27a09-110">disablePayloadMasking</span></span>|<span data-ttu-id="27a09-111">Określa, czy maskowanie gniazda sieci Web jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="27a09-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="27a09-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="27a09-112">keepAliveInterval</span></span>|<span data-ttu-id="27a09-113">Określa interwał utrzymywania aktywności.</span><span class="sxs-lookup"><span data-stu-id="27a09-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="27a09-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="27a09-114">maxPendingConnections</span></span>|<span data-ttu-id="27a09-115">Określa maksymalną liczbę połączeń oczekujących na wysłanie usługi.</span><span class="sxs-lookup"><span data-stu-id="27a09-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="27a09-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="27a09-116">receiveBufferSize</span></span>|<span data-ttu-id="27a09-117">Określa rozmiar buforu odbioru.</span><span class="sxs-lookup"><span data-stu-id="27a09-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="27a09-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="27a09-118">sendBufferSize</span></span>|<span data-ttu-id="27a09-119">Określa rozmiar buforu wysyłania.</span><span class="sxs-lookup"><span data-stu-id="27a09-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="27a09-120">Podprotokół</span><span class="sxs-lookup"><span data-stu-id="27a09-120">subProtocol</span></span>|<span data-ttu-id="27a09-121">Określa podprotokół gniazda sieci Web.</span><span class="sxs-lookup"><span data-stu-id="27a09-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="27a09-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="27a09-122">transportUsage</span></span>|<span data-ttu-id="27a09-123">Określa, kiedy należy używać gniazd sieci Web.</span><span class="sxs-lookup"><span data-stu-id="27a09-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="27a09-124">transportUsage — atrybut</span><span class="sxs-lookup"><span data-stu-id="27a09-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="27a09-125">Wartość</span><span class="sxs-lookup"><span data-stu-id="27a09-125">Value</span></span>|<span data-ttu-id="27a09-126">Opis</span><span class="sxs-lookup"><span data-stu-id="27a09-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="27a09-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="27a09-127">WhenDuplex</span></span>|<span data-ttu-id="27a09-128">Użyj protokołu gniazda sieci Web, gdy kontrakt jest w trybie dupleksu.</span><span class="sxs-lookup"><span data-stu-id="27a09-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="27a09-129">Zawsze</span><span class="sxs-lookup"><span data-stu-id="27a09-129">Always</span></span>|<span data-ttu-id="27a09-130">Zawsze używaj protokołu gniazda internetowego niezależnie od kontraktu.</span><span class="sxs-lookup"><span data-stu-id="27a09-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="27a09-131">Nigdy</span><span class="sxs-lookup"><span data-stu-id="27a09-131">Never</span></span>|<span data-ttu-id="27a09-132">Nigdy nie używaj protokołu gniazda sieci Web.</span><span class="sxs-lookup"><span data-stu-id="27a09-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27a09-133">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="27a09-133">Child Elements</span></span>  

 <span data-ttu-id="27a09-134">Brak</span><span class="sxs-lookup"><span data-stu-id="27a09-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27a09-135">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="27a09-135">Parent Elements</span></span>  
  
|<span data-ttu-id="27a09-136">Element</span><span class="sxs-lookup"><span data-stu-id="27a09-136">Element</span></span>|<span data-ttu-id="27a09-137">Opis</span><span class="sxs-lookup"><span data-stu-id="27a09-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="27a09-138">Określa protokół HttpBinding</span><span class="sxs-lookup"><span data-stu-id="27a09-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27a09-139">Przykład</span><span class="sxs-lookup"><span data-stu-id="27a09-139">Example</span></span>  

 <span data-ttu-id="27a09-140">Poniższy przykład pokazuje, jak używać \<webSocketSettings> elementu.</span><span class="sxs-lookup"><span data-stu-id="27a09-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="27a09-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="27a09-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="27a09-142">Powiązania</span><span class="sxs-lookup"><span data-stu-id="27a09-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="27a09-143">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="27a09-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="27a09-144">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="27a09-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
