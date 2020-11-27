---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: eecf2b0bf459fd14236c550e393149553183b3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267926"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="4b86d-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4b86d-102">LocalServiceSecuritySettings</span></span>

<span data-ttu-id="4b86d-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4b86d-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b86d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4b86d-104">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4b86d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="4b86d-105">Methods</span></span>  

 <span data-ttu-id="4b86d-106">Klasa LocalServiceSecuritySettings nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="4b86d-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4b86d-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="4b86d-107">Properties</span></span>  

 <span data-ttu-id="4b86d-108">Klasa LocalServiceSecuritySettings ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="4b86d-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="4b86d-109">Włączonej opcji DetectReplays</span><span class="sxs-lookup"><span data-stu-id="4b86d-109">DetectReplays</span></span>  

 <span data-ttu-id="4b86d-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="4b86d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4b86d-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-112">Wartość logiczna określająca, czy ataki powtarzające się na kanał są wykrywane i rozwiązywane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4b86d-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="4b86d-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="4b86d-113">InactivityTimeout</span></span>  

 <span data-ttu-id="4b86d-114">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-116">Maksymalna liczba oczekujących sesji bezpieczeństwa obsługiwanych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="4b86d-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="4b86d-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="4b86d-117">IssuedCookieLifetime</span></span>  

 <span data-ttu-id="4b86d-118">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-120">Obiekt TimeSpan określający okres istnienia wystawiony dla wszystkich nowych plików cookie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="4b86d-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="4b86d-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="4b86d-121">MaxCachedCookies</span></span>  

 <span data-ttu-id="4b86d-122">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="4b86d-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b86d-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-124">Maksymalna liczba plików cookie, które mogą być buforowane.</span><span class="sxs-lookup"><span data-stu-id="4b86d-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="4b86d-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="4b86d-125">MaxClockSkew</span></span>  

 <span data-ttu-id="4b86d-126">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-128">Obiekt TimeSpan określający maksymalną różnicę czasu między zegarami systemowymi dwóch osób komunikujących się.</span><span class="sxs-lookup"><span data-stu-id="4b86d-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="4b86d-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="4b86d-129">MaxPendingSessions</span></span>  

 <span data-ttu-id="4b86d-130">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="4b86d-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b86d-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-132">Maksymalna liczba oczekujących połączeń w usłudze.</span><span class="sxs-lookup"><span data-stu-id="4b86d-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="4b86d-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="4b86d-133">MaxStatefulNegotiations</span></span>  

 <span data-ttu-id="4b86d-134">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="4b86d-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b86d-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-136">Liczba negocjacji zabezpieczeń, które mogą być jednocześnie aktywne.</span><span class="sxs-lookup"><span data-stu-id="4b86d-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="4b86d-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="4b86d-137">NegotiationTimeout</span></span>  

 <span data-ttu-id="4b86d-138">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-140">Obiekt TimeSpan, który określa maksymalny czas trwania fazy negocjowania zabezpieczeń między serwerem a klientem.</span><span class="sxs-lookup"><span data-stu-id="4b86d-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="4b86d-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="4b86d-141">ReconnectTransportOnFailure</span></span>  

 <span data-ttu-id="4b86d-142">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="4b86d-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="4b86d-143">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-144">Wartość logiczna określająca, czy połączenia przy użyciu funkcji WS-Reliable Messaging próbują ponownie nawiązać połączenie po wystąpieniu błędów transportu.</span><span class="sxs-lookup"><span data-stu-id="4b86d-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="4b86d-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="4b86d-145">ReplayCacheSize</span></span>  

 <span data-ttu-id="4b86d-146">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="4b86d-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b86d-147">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-148">Liczba buforowanych identyfikatorów jednorazowych używanych do wykrywania powtórzeń.</span><span class="sxs-lookup"><span data-stu-id="4b86d-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="4b86d-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="4b86d-149">ReplayWindow</span></span>  

 <span data-ttu-id="4b86d-150">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-151">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-152">Obiekt TimeSpan określający czas, w którym identyfikatorów jednorazowych poszczególnych komunikatów są prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="4b86d-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="4b86d-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="4b86d-153">SessionKeyRenewalInterval</span></span>  

 <span data-ttu-id="4b86d-154">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-155">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-156">Obiekt TimeSpan, który określa czas, po którym inicjator odnawia klucz dla sesji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="4b86d-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="4b86d-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="4b86d-157">SessionKeyRolloverInterval</span></span>  

 <span data-ttu-id="4b86d-158">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-159">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-160">Obiekt TimeSpan, który określa przedział czasu, w którym poprzedni klucz sesji jest ważny w przypadku komunikatów przychodzących podczas odnawiania klucza.</span><span class="sxs-lookup"><span data-stu-id="4b86d-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="4b86d-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="4b86d-161">TimestampValidityDuration</span></span>  

 <span data-ttu-id="4b86d-162">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="4b86d-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="4b86d-163">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b86d-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b86d-164">Obiekt TimeSpan określający czas, w którym sygnatura czasowa jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="4b86d-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b86d-165">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4b86d-165">Requirements</span></span>  
  
|<span data-ttu-id="4b86d-166">PLIK</span><span class="sxs-lookup"><span data-stu-id="4b86d-166">MOF</span></span>|<span data-ttu-id="4b86d-167">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="4b86d-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4b86d-168">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="4b86d-168">Namespace</span></span>|<span data-ttu-id="4b86d-169">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4b86d-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b86d-170">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4b86d-170">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
