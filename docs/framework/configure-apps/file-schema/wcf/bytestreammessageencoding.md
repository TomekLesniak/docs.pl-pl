---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: e2b92b88c3e2a8abb14f58af90aab6e2e58ce14a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557297"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="527bc-101">Określa kodowanie komunikatu jako strumień bajtów z opcją określenia kodowania znaków.</span><span class="sxs-lookup"><span data-stu-id="527bc-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="527bc-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="527bc-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="527bc-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="527bc-103">Attributes and Elements</span></span>  
 <span data-ttu-id="527bc-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="527bc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="527bc-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="527bc-105">Attributes</span></span>  
  
|<span data-ttu-id="527bc-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="527bc-106">Attribute</span></span>|<span data-ttu-id="527bc-107">Opis</span><span class="sxs-lookup"><span data-stu-id="527bc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="527bc-108">Element MessageVersion</span><span class="sxs-lookup"><span data-stu-id="527bc-108">messageVersion</span></span>|<span data-ttu-id="527bc-109">Określa wersję SOAP komunikatów wysyłanych za pomocą powiązania.</span><span class="sxs-lookup"><span data-stu-id="527bc-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="527bc-110">Dla tej właściwości można ustawić tylko wartość wersji komunikatu <xref:System.ServiceModel.Channels.MessageVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="527bc-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="527bc-111">Koder komunikatów strumienia bajtów nie obsługuje żadnych innych wersji komunikatów.</span><span class="sxs-lookup"><span data-stu-id="527bc-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="527bc-112">Ten atrybut jest typu <xref:System.ServiceModel.Channels.MessageVersion> .</span><span class="sxs-lookup"><span data-stu-id="527bc-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="527bc-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="527bc-113">Child Elements</span></span>  
  
|<span data-ttu-id="527bc-114">Element</span><span class="sxs-lookup"><span data-stu-id="527bc-114">Element</span></span>|<span data-ttu-id="527bc-115">Opis</span><span class="sxs-lookup"><span data-stu-id="527bc-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="527bc-116">Definiuje ograniczenia złożoności komunikatów protokołu SOAP, które mogą być przetwarzane przez punkty końcowe skonfigurowane za pomocą tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="527bc-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="527bc-117">Ten element jest typu <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> .</span><span class="sxs-lookup"><span data-stu-id="527bc-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="527bc-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="527bc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="527bc-119">Element</span><span class="sxs-lookup"><span data-stu-id="527bc-119">Element</span></span>|<span data-ttu-id="527bc-120">Opis</span><span class="sxs-lookup"><span data-stu-id="527bc-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="527bc-121">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="527bc-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="527bc-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="527bc-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="527bc-123">Kodowanie komunikatu</span><span class="sxs-lookup"><span data-stu-id="527bc-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="527bc-124">Wybieranie kodera komunikatów</span><span class="sxs-lookup"><span data-stu-id="527bc-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="527bc-125">Powiązania</span><span class="sxs-lookup"><span data-stu-id="527bc-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="527bc-126">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="527bc-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="527bc-127">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="527bc-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
