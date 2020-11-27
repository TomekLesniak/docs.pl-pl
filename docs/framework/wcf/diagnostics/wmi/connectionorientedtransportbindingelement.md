---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 3c69b73cc05a56a7556630de0f83675590442293
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274156"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="cf8a1-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cf8a1-102">ConnectionOrientedTransportBindingElement</span></span>

<span data-ttu-id="cf8a1-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cf8a1-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8a1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf8a1-104">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cf8a1-105">Metody</span><span class="sxs-lookup"><span data-stu-id="cf8a1-105">Methods</span></span>  

 <span data-ttu-id="cf8a1-106">Klasa ConnectionOrientedTransportBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf8a1-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="cf8a1-107">Properties</span></span>  

 <span data-ttu-id="cf8a1-108">Klasa ConnectionOrientedTransportBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="cf8a1-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="cf8a1-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="cf8a1-109">ChannelInitializationTimeout</span></span>  

 <span data-ttu-id="cf8a1-110">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="cf8a1-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="cf8a1-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-112">Obiekt TimeSpan określający, jak długo Inicjalizacja kanału ma zostać ukończona przed upływem limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="cf8a1-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="cf8a1-113">ConnectionBufferSize</span></span>  

 <span data-ttu-id="cf8a1-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="cf8a1-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="cf8a1-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-116">Rozmiar buforu używany do przesyłania fragmentu serializowanego komunikatu w sieci z klienta lub usługi.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="cf8a1-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="cf8a1-117">HostNameComparisonMode</span></span>  

 <span data-ttu-id="cf8a1-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="cf8a1-118">Data type: string</span></span>  
  
 <span data-ttu-id="cf8a1-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-120">Wartość wskazująca, czy nazwa hosta jest używana do uzyskiwania dostępu do usługi podczas dopasowywania identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="cf8a1-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="cf8a1-121">MaxBufferSize</span></span>  

 <span data-ttu-id="cf8a1-122">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="cf8a1-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="cf8a1-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-124">Maksymalny rozmiar buforu do użycia.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="cf8a1-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="cf8a1-125">MaxOutputDelay</span></span>  

 <span data-ttu-id="cf8a1-126">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="cf8a1-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="cf8a1-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-128">Maksymalny przedział czasu, przez który fragment komunikatu lub pełny komunikat może pozostawać w pamięci przed wysłaniem.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="cf8a1-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="cf8a1-129">MaxPendingAccepts</span></span>  

 <span data-ttu-id="cf8a1-130">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="cf8a1-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="cf8a1-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-132">Maksymalna liczba oczekujących asynchronicznych wątków akceptujących, które są dostępne do przetwarzania przychodzących połączeń z usługą.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="cf8a1-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="cf8a1-133">MaxPendingConnections</span></span>  

 <span data-ttu-id="cf8a1-134">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="cf8a1-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="cf8a1-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-136">Maksymalna liczba oczekujących połączeń.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="cf8a1-137">Elementy TransferMode</span><span class="sxs-lookup"><span data-stu-id="cf8a1-137">TransferMode</span></span>  

 <span data-ttu-id="cf8a1-138">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="cf8a1-138">Data type: string</span></span>  
  
 <span data-ttu-id="cf8a1-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="cf8a1-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf8a1-140">Wartość określająca, czy komunikaty są buforowane, czy przesyłane strumieniowo z transportem zorientowanym na połączenia.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf8a1-141">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cf8a1-141">Requirements</span></span>  
  
|<span data-ttu-id="cf8a1-142">PLIK</span><span class="sxs-lookup"><span data-stu-id="cf8a1-142">MOF</span></span>|<span data-ttu-id="cf8a1-143">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="cf8a1-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf8a1-144">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="cf8a1-144">Namespace</span></span>|<span data-ttu-id="cf8a1-145">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cf8a1-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf8a1-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cf8a1-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
