---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 1b72b73f0d9d312fd54ea6a5517d55bf251c0e05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201476"
---
# \<binaryMessageEncoding>

<span data-ttu-id="8782b-101">Definiuje binarny koder komunikatów, który koduje wiadomości Windows Communication Foundation (WCF) w postaci binarnej w sieci.</span><span class="sxs-lookup"><span data-stu-id="8782b-101">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="8782b-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="8782b-102">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8782b-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8782b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8782b-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8782b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8782b-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8782b-105">Attributes</span></span>  
  
|<span data-ttu-id="8782b-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8782b-106">Attribute</span></span>|<span data-ttu-id="8782b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8782b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8782b-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="8782b-108">maxReadPoolSize</span></span>|<span data-ttu-id="8782b-109">Liczba całkowita, która określa, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.</span><span class="sxs-lookup"><span data-stu-id="8782b-109">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="8782b-110">Większe rozmiary puli sprawiają, że system jest bardziej odporny na obciążenia, a koszt większym zestawem roboczym.</span><span class="sxs-lookup"><span data-stu-id="8782b-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8782b-111">Wartość domyślna to 64.</span><span class="sxs-lookup"><span data-stu-id="8782b-111">The default is 64.</span></span>|  
|<span data-ttu-id="8782b-112">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="8782b-112">maxSessionSize</span></span>|<span data-ttu-id="8782b-113">Dodatnia liczba całkowita, która ustawia rozmiar (w bajtach) bufora używanego do kodowania.</span><span class="sxs-lookup"><span data-stu-id="8782b-113">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="8782b-114">Większy bufor zwiększa szybkość kodowania przy kosztach rozmiaru zestawu roboczego.</span><span class="sxs-lookup"><span data-stu-id="8782b-114">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="8782b-115">Wartość domyślna to 2048.</span><span class="sxs-lookup"><span data-stu-id="8782b-115">The default is 2048.</span></span>|  
|<span data-ttu-id="8782b-116">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="8782b-116">maxWritePoolSize</span></span>|<span data-ttu-id="8782b-117">Liczba całkowita, która określa, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="8782b-117">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="8782b-118">Większe rozmiary puli sprawiają, że system jest bardziej odporny na obciążenia, a koszt większym zestawem roboczym.</span><span class="sxs-lookup"><span data-stu-id="8782b-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8782b-119">Wartość domyślna to 16.</span><span class="sxs-lookup"><span data-stu-id="8782b-119">The default is 16.</span></span>|  
|<span data-ttu-id="8782b-120">Element MessageVersion</span><span class="sxs-lookup"><span data-stu-id="8782b-120">messageVersion</span></span>|<span data-ttu-id="8782b-121">Określa komunikat protokołu SOAP i wersje WS-Addressing, które są używane lub oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="8782b-121">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8782b-122">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8782b-122">Child Elements</span></span>  
  
|<span data-ttu-id="8782b-123">Element</span><span class="sxs-lookup"><span data-stu-id="8782b-123">Element</span></span>|<span data-ttu-id="8782b-124">Opis</span><span class="sxs-lookup"><span data-stu-id="8782b-124">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="8782b-125">Definiuje ograniczenia złożoności komunikatów protokołu SOAP, które mogą być przetwarzane przez punkty końcowe skonfigurowane za pomocą tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="8782b-125">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8782b-126">Ten element jest typu <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> .</span><span class="sxs-lookup"><span data-stu-id="8782b-126">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8782b-127">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8782b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8782b-128">Element</span><span class="sxs-lookup"><span data-stu-id="8782b-128">Element</span></span>|<span data-ttu-id="8782b-129">Opis</span><span class="sxs-lookup"><span data-stu-id="8782b-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="8782b-130">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="8782b-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8782b-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8782b-131">Remarks</span></span>  

 <span data-ttu-id="8782b-132">Kodowanie jest procesem przekształcania komunikatu w sekwencję bajtów.</span><span class="sxs-lookup"><span data-stu-id="8782b-132">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="8782b-133">Dekodowanie jest procesem wycofywania.</span><span class="sxs-lookup"><span data-stu-id="8782b-133">Decoding is the reverse process.</span></span> <span data-ttu-id="8782b-134">Windows Communication Foundation (WCF) zawiera trzy typy kodowania komunikatów protokołu SOAP: tekst, binarny i mechanizm optymalizacji transmisji wiadomości (MTOM).</span><span class="sxs-lookup"><span data-stu-id="8782b-134">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="8782b-135">`binaryMessageEncoding`Element określa format binarny platformy .NET dla języka XML i zawiera opcje umożliwiające określenie kodowania znaków oraz wersji protokołu SOAP i WS-Addressing, która ma zostać użyta.</span><span class="sxs-lookup"><span data-stu-id="8782b-135">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="8782b-136">Koder komunikatów binarnych koduje wiadomości Windows Communication Foundation (WCF) w postaci binarnej w sieci.</span><span class="sxs-lookup"><span data-stu-id="8782b-136">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="8782b-137">Chociaż to kodowanie skutkuje bardzo szybką transmisją komunikatów, współpraca oparta na standardach protokołu WS-\* zostanie utracona.</span><span class="sxs-lookup"><span data-stu-id="8782b-137">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8782b-138">Przykład</span><span class="sxs-lookup"><span data-stu-id="8782b-138">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="8782b-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8782b-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="8782b-140">Kodowanie komunikatu</span><span class="sxs-lookup"><span data-stu-id="8782b-140">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="8782b-141">Wybieranie kodera komunikatów</span><span class="sxs-lookup"><span data-stu-id="8782b-141">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="8782b-142">Powiązania</span><span class="sxs-lookup"><span data-stu-id="8782b-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8782b-143">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="8782b-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8782b-144">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="8782b-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
