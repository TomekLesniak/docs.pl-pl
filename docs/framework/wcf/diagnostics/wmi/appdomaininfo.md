---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: c5c44f4d8f6d93443802d5e1950c4d850976c5b6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291131"
---
# <a name="appdomaininfo"></a><span data-ttu-id="d00eb-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="d00eb-102">AppDomainInfo</span></span>

<span data-ttu-id="d00eb-103">Informacje o domenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="d00eb-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d00eb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d00eb-104">Syntax</span></span>  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d00eb-105">Metody</span><span class="sxs-lookup"><span data-stu-id="d00eb-105">Methods</span></span>  

 <span data-ttu-id="d00eb-106">Klasa AppDomainInfo nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="d00eb-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d00eb-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="d00eb-107">Properties</span></span>  

 <span data-ttu-id="d00eb-108">Klasa AppDomainInfo ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="d00eb-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="d00eb-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="d00eb-109">AppDomainId</span></span>  

 <span data-ttu-id="d00eb-110">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="d00eb-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="d00eb-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-112">Identyfikator domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d00eb-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="d00eb-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="d00eb-113">IsDefault</span></span>  

 <span data-ttu-id="d00eb-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="d00eb-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d00eb-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-116">Wskazuje, czy domena aplikacji jest domyślną domeną aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d00eb-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="d00eb-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="d00eb-117">LogMalformedMessages</span></span>  

 <span data-ttu-id="d00eb-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="d00eb-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="d00eb-119">Typ dostępu: odczyt/zapis</span><span class="sxs-lookup"><span data-stu-id="d00eb-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d00eb-120">Wartość określająca, czy źle sformułowane komunikaty są rejestrowane.</span><span class="sxs-lookup"><span data-stu-id="d00eb-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="d00eb-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="d00eb-121">LogMessagesAtServiceLevel</span></span>  

 <span data-ttu-id="d00eb-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="d00eb-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d00eb-123">Typ dostępu: odczyt/zapis</span><span class="sxs-lookup"><span data-stu-id="d00eb-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d00eb-124">Wartość określająca, czy komunikaty są śledzone na poziomie usługi (przed szyfrowaniem i transformacjemi związanymi z transportem).</span><span class="sxs-lookup"><span data-stu-id="d00eb-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="d00eb-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="d00eb-125">LogMessagesAtTransportLevel</span></span>  

 <span data-ttu-id="d00eb-126">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="d00eb-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d00eb-127">Typ dostępu: odczyt/zapis</span><span class="sxs-lookup"><span data-stu-id="d00eb-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d00eb-128">Wartość określająca, czy komunikaty są śledzone na poziomie transportu.</span><span class="sxs-lookup"><span data-stu-id="d00eb-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="d00eb-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="d00eb-129">MessageLoggingTraceListeners</span></span>  

 <span data-ttu-id="d00eb-130">Typ danych: tablica TraceListener</span><span class="sxs-lookup"><span data-stu-id="d00eb-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="d00eb-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-132">Detektory śledzenia kolekcji, które nasłuchują źródła śledzenia system. WMI. MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="d00eb-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d00eb-133">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d00eb-133">Name</span></span>  

 <span data-ttu-id="d00eb-134">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d00eb-134">Data type: string</span></span>  
  
 <span data-ttu-id="d00eb-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-136">Nazwa domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d00eb-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="d00eb-137">Liczniki wydajności</span><span class="sxs-lookup"><span data-stu-id="d00eb-137">PerformanceCounters</span></span>  

 <span data-ttu-id="d00eb-138">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d00eb-138">Data type: string</span></span>  
  
 <span data-ttu-id="d00eb-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-140">Zakres aktywnych liczników wydajności w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d00eb-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d00eb-141">Identyfikator procesu</span><span class="sxs-lookup"><span data-stu-id="d00eb-141">ProcessId</span></span>  

 <span data-ttu-id="d00eb-142">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="d00eb-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="d00eb-143">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-144">Identyfikator procesu.</span><span class="sxs-lookup"><span data-stu-id="d00eb-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="d00eb-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="d00eb-145">ServiceConfigPath</span></span>  

 <span data-ttu-id="d00eb-146">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d00eb-146">Data type: string</span></span>  
  
 <span data-ttu-id="d00eb-147">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-148">Ścieżka do konfiguracji usługi.</span><span class="sxs-lookup"><span data-stu-id="d00eb-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="d00eb-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="d00eb-149">TraceLevel</span></span>  

 <span data-ttu-id="d00eb-150">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="d00eb-150">Data type: string</span></span>  
  
 <span data-ttu-id="d00eb-151">Typ dostępu: odczyt/zapis</span><span class="sxs-lookup"><span data-stu-id="d00eb-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="d00eb-152">Poziom śledzenia źródła śledzenia system. WMI.</span><span class="sxs-lookup"><span data-stu-id="d00eb-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="d00eb-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="d00eb-153">ServiceModelTraceListeners</span></span>  

 <span data-ttu-id="d00eb-154">Typ danych: tablica TraceListener</span><span class="sxs-lookup"><span data-stu-id="d00eb-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="d00eb-155">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d00eb-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d00eb-156">Kolekcja odbiorników ze źródła śledzenia system. ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d00eb-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d00eb-157">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d00eb-157">Requirements</span></span>  
  
|<span data-ttu-id="d00eb-158">PLIK</span><span class="sxs-lookup"><span data-stu-id="d00eb-158">MOF</span></span>|<span data-ttu-id="d00eb-159">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="d00eb-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d00eb-160">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="d00eb-160">Namespace</span></span>|<span data-ttu-id="d00eb-161">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d00eb-161">Defined in root\ServiceModel</span></span>|
