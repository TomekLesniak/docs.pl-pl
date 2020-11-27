---
title: Usługa
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273285"
---
# <a name="service"></a><span data-ttu-id="c859a-102">Usługa</span><span class="sxs-lookup"><span data-stu-id="c859a-102">Service</span></span>

<span data-ttu-id="c859a-103">Usługa</span><span class="sxs-lookup"><span data-stu-id="c859a-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c859a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c859a-104">Syntax</span></span>  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c859a-105">Metody</span><span class="sxs-lookup"><span data-stu-id="c859a-105">Methods</span></span>  

 <span data-ttu-id="c859a-106">Klasa usługi nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="c859a-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c859a-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="c859a-107">Properties</span></span>  

 <span data-ttu-id="c859a-108">Klasa usługi ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="c859a-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="c859a-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="c859a-109">BaseAddresses</span></span>  

 <span data-ttu-id="c859a-110">Typ danych: tablica ciągów</span><span class="sxs-lookup"><span data-stu-id="c859a-110">Data type: string array</span></span>  
  
 <span data-ttu-id="c859a-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-112">Adresy podstawowe używane przez usługę.</span><span class="sxs-lookup"><span data-stu-id="c859a-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="c859a-113">Zachowania</span><span class="sxs-lookup"><span data-stu-id="c859a-113">Behaviors</span></span>  

 <span data-ttu-id="c859a-114">Typ danych: tablica zachowań</span><span class="sxs-lookup"><span data-stu-id="c859a-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="c859a-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-116">Zachowania skojarzone z tą usługą.</span><span class="sxs-lookup"><span data-stu-id="c859a-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="c859a-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="c859a-117">ConfigurationName</span></span>  

 <span data-ttu-id="c859a-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="c859a-118">Data type: string</span></span>  
  
 <span data-ttu-id="c859a-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c859a-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="c859a-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="c859a-121">CounterInstanceName</span></span>  

 <span data-ttu-id="c859a-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="c859a-122">Data type: string</span></span>  
  
 <span data-ttu-id="c859a-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-124">Nazwa wystąpienia liczników wydajności usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="c859a-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="c859a-125">DistinguishedName</span></span>  

 <span data-ttu-id="c859a-126">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="c859a-126">Data type: string</span></span>  
  
 <span data-ttu-id="c859a-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-128">Nazwa usługi pod adresem.</span><span class="sxs-lookup"><span data-stu-id="c859a-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="c859a-129">Rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="c859a-129">Extensions</span></span>  

 <span data-ttu-id="c859a-130">Typ danych: tablica ciągów</span><span class="sxs-lookup"><span data-stu-id="c859a-130">Data type: string array</span></span>  
  
 <span data-ttu-id="c859a-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-132">Konteksty wystąpienia dla rozszerzeń wystąpienia usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="c859a-133">Metadane</span><span class="sxs-lookup"><span data-stu-id="c859a-133">Metadata</span></span>  

 <span data-ttu-id="c859a-134">Typ danych: tablica ciągów</span><span class="sxs-lookup"><span data-stu-id="c859a-134">Data type: string array</span></span>  
  
 <span data-ttu-id="c859a-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-136">Ustawienia metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c859a-137">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c859a-137">Name</span></span>  

 <span data-ttu-id="c859a-138">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="c859a-138">Data type: string</span></span>  
  
 <span data-ttu-id="c859a-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-140">Unikatowa nazwa tej usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="c859a-141">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="c859a-141">Namespace</span></span>  

 <span data-ttu-id="c859a-142">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="c859a-142">Data type: string</span></span>  
  
 <span data-ttu-id="c859a-143">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-144">Przestrzeń nazw usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="c859a-145">Otworzyć</span><span class="sxs-lookup"><span data-stu-id="c859a-145">Opened</span></span>  

 <span data-ttu-id="c859a-146">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="c859a-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="c859a-147">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-148">Czas otwarcia usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="c859a-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="c859a-149">OutgoingChannels</span></span>  

 <span data-ttu-id="c859a-150">Typ danych: tablica kanałów</span><span class="sxs-lookup"><span data-stu-id="c859a-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="c859a-151">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-152">Kanały wychodzące z wystąpienia usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="c859a-153">Identyfikator procesu</span><span class="sxs-lookup"><span data-stu-id="c859a-153">ProcessId</span></span>  

 <span data-ttu-id="c859a-154">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="c859a-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="c859a-155">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="c859a-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c859a-156">Identyfikator procesu, który jest hostem usługi.</span><span class="sxs-lookup"><span data-stu-id="c859a-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c859a-157">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c859a-157">Requirements</span></span>  
  
|<span data-ttu-id="c859a-158">PLIK</span><span class="sxs-lookup"><span data-stu-id="c859a-158">MOF</span></span>|<span data-ttu-id="c859a-159">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="c859a-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c859a-160">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="c859a-160">Namespace</span></span>|<span data-ttu-id="c859a-161">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c859a-161">Defined in root\ServiceModel</span></span>|
