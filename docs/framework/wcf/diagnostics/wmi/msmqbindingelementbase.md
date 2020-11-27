---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 48d26bfa9074fd605e3545579f0bdc2744dfc7d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267862"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="29a16-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="29a16-102">MsmqBindingElementBase</span></span>

<span data-ttu-id="29a16-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="29a16-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a16-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="29a16-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="29a16-105">Metody</span><span class="sxs-lookup"><span data-stu-id="29a16-105">Methods</span></span>  

 <span data-ttu-id="29a16-106">Klasa MsmqBindingElementBase nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="29a16-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="29a16-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="29a16-107">Properties</span></span>  

 <span data-ttu-id="29a16-108">Klasa MsmqBindingElementBase ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="29a16-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="29a16-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="29a16-109">CustomDeadLetterQueue</span></span>  

 <span data-ttu-id="29a16-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="29a16-110">Data type: string</span></span>  
  
 <span data-ttu-id="29a16-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-112">Identyfikator URI, który zawiera lokalizację kolejki utraconych wiadomości dla każdej aplikacji, miejsce, w której znajdują się komunikaty, które wygasły lub które nie zostały przekazane.</span><span class="sxs-lookup"><span data-stu-id="29a16-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="29a16-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="29a16-113">DeadLetterQueue</span></span>  

 <span data-ttu-id="29a16-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="29a16-114">Data type: string</span></span>  
  
 <span data-ttu-id="29a16-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-116">Wartość wyliczenia wskazująca typ używanej kolejki utraconych wiadomości.</span><span class="sxs-lookup"><span data-stu-id="29a16-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="29a16-117">Trwałość</span><span class="sxs-lookup"><span data-stu-id="29a16-117">Durable</span></span>  

 <span data-ttu-id="29a16-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="29a16-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="29a16-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-120">Wartość wskazująca, czy komunikaty przetwarzane przez to powiązanie są trwałe czy nietrwałe.</span><span class="sxs-lookup"><span data-stu-id="29a16-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="29a16-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="29a16-121">ExactlyOnce</span></span>  

 <span data-ttu-id="29a16-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="29a16-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="29a16-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-124">Wartość logiczna wskazująca, czy komunikaty przetwarzane przez to powiązanie są odbierane dokładnie raz.</span><span class="sxs-lookup"><span data-stu-id="29a16-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="29a16-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="29a16-125">MaxRetryCycles</span></span>  

 <span data-ttu-id="29a16-126">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="29a16-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="29a16-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-128">Maksymalna liczba ponownych prób dostarczenia komunikatów do aplikacji odbiorczej.</span><span class="sxs-lookup"><span data-stu-id="29a16-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="29a16-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="29a16-129">ReceiveErrorHandling</span></span>  

 <span data-ttu-id="29a16-130">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="29a16-130">Data type: string</span></span>  
  
 <span data-ttu-id="29a16-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-132">Ustawienia obsługi skażonych komunikatów.</span><span class="sxs-lookup"><span data-stu-id="29a16-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="29a16-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="29a16-133">ReceiveRetryCount</span></span>  

 <span data-ttu-id="29a16-134">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="29a16-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="29a16-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-136">Maksymalna liczba natychmiastowych ponownych prób w komunikacie odczytywanym z kolejki aplikacji.</span><span class="sxs-lookup"><span data-stu-id="29a16-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="29a16-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="29a16-137">RetryCycleDelay</span></span>  

 <span data-ttu-id="29a16-138">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="29a16-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="29a16-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-140">Wartość wskazująca czas opóźnienia między kolejnymi próbami dostarczenia komunikatu, którego nie można było dostarczyć natychmiast.</span><span class="sxs-lookup"><span data-stu-id="29a16-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="29a16-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="29a16-141">TimeToLive</span></span>  

 <span data-ttu-id="29a16-142">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="29a16-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="29a16-143">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-144">Przedział czasu, który wskazuje, jak długo komunikaty przetwarzane przez to powiązanie mogą znajdować się w kolejce przed ich wygaśnięciem.</span><span class="sxs-lookup"><span data-stu-id="29a16-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="29a16-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="29a16-145">UseMsmqTracing</span></span>  

 <span data-ttu-id="29a16-146">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="29a16-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="29a16-147">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-148">Wartość logiczna wskazująca, czy komunikaty przetwarzane przez to powiązanie powinny być śledzone.</span><span class="sxs-lookup"><span data-stu-id="29a16-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="29a16-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="29a16-149">UseSourceJournal</span></span>  

 <span data-ttu-id="29a16-150">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="29a16-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="29a16-151">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="29a16-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29a16-152">Wartość logiczna wskazująca, czy kopie komunikatów przetwarzanych przez to powiązanie powinny być przechowywane w kolejce dziennika źródła.</span><span class="sxs-lookup"><span data-stu-id="29a16-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a16-153">Wymagania</span><span class="sxs-lookup"><span data-stu-id="29a16-153">Requirements</span></span>  
  
|<span data-ttu-id="29a16-154">PLIK</span><span class="sxs-lookup"><span data-stu-id="29a16-154">MOF</span></span>|<span data-ttu-id="29a16-155">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="29a16-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="29a16-156">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="29a16-156">Namespace</span></span>|<span data-ttu-id="29a16-157">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="29a16-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29a16-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="29a16-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
