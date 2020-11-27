---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: f91e38ab88cd9f93e9bec0e3a6ca65254bc49570
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273324"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="ca5b4-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca5b4-102">ReliableSessionBindingElement</span></span>

<span data-ttu-id="ca5b4-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca5b4-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca5b4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ca5b4-104">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ca5b4-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ca5b4-105">Methods</span></span>  

 <span data-ttu-id="ca5b4-106">Klasa elementu ReliableSessionBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ca5b4-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ca5b4-107">Properties</span></span>  

 <span data-ttu-id="ca5b4-108">Klasa elementu ReliableSessionBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="ca5b4-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="ca5b4-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="ca5b4-109">AcknowledgementInterval</span></span>  

 <span data-ttu-id="ca5b4-110">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="ca5b4-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="ca5b4-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-112">Przedział czasu, przez który miejsce docelowe czeka przed wysłaniem potwierdzenia do źródła wiadomości w niezawodnych kanałach, które są tworzone przez fabrykę.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="ca5b4-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="ca5b4-113">FlowControlEnabled</span></span>  

 <span data-ttu-id="ca5b4-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="ca5b4-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ca5b4-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-116">Wartość logiczna określająca, czy włączono sterowanie przepływem.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="ca5b4-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="ca5b4-117">InactivityTimeout</span></span>  

 <span data-ttu-id="ca5b4-118">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="ca5b4-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="ca5b4-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-120">Określa maksymalny czas, przez który kanał zezwoli innemu nadawcy na wysyłanie komunikatów przed awarią kanału.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="ca5b4-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="ca5b4-121">MaxPendingChannels</span></span>  

 <span data-ttu-id="ca5b4-122">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="ca5b4-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="ca5b4-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-124">Maksymalna liczba kanałów oczekujących na akceptację odbiornika.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="ca5b4-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="ca5b4-125">MaxRetryCount</span></span>  

 <span data-ttu-id="ca5b4-126">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="ca5b4-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="ca5b4-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-128">Maksymalna liczba prób ponownego wysłania komunikatu przez niezawodny kanał, dla którego nie odebrano potwierdzenia, przez wywołanie `Send` jego podstawowego kanału.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="ca5b4-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="ca5b4-129">MaxTransferWindowSize</span></span>  

 <span data-ttu-id="ca5b4-130">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="ca5b4-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="ca5b4-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-132">Maksymalny rozmiar okna transferu dla niezawodnej sesji.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="ca5b4-133">Zamówione</span><span class="sxs-lookup"><span data-stu-id="ca5b4-133">Ordered</span></span>  

 <span data-ttu-id="ca5b4-134">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="ca5b4-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="ca5b4-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-136">Wartość logiczna określająca, czy komunikaty są gwarantowane w kolejności, w jakiej zostały wysłane.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="ca5b4-137">ReliableMessagingVersion określająca</span><span class="sxs-lookup"><span data-stu-id="ca5b4-137">ReliableMessagingVersion</span></span>  

 <span data-ttu-id="ca5b4-138">Typ danych: liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="ca5b4-138">Data type: integer</span></span>  
  
 <span data-ttu-id="ca5b4-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ca5b4-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca5b4-140">Liczba całkowita, która określa wersję protokołu WS-ReliableMessaging użytą w niezawodnej sesji.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5b4-141">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ca5b4-141">Requirements</span></span>  
  
|<span data-ttu-id="ca5b4-142">PLIK</span><span class="sxs-lookup"><span data-stu-id="ca5b4-142">MOF</span></span>|<span data-ttu-id="ca5b4-143">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ca5b4-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ca5b4-144">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ca5b4-144">Namespace</span></span>|<span data-ttu-id="ca5b4-145">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ca5b4-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca5b4-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ca5b4-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
