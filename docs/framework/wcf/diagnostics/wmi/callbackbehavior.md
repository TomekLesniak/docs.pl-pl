---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: cec9005a099247671dbebaacc0b242ca8d7a0144
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269651"
---
# <a name="callbackbehavior"></a><span data-ttu-id="7a7c0-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="7a7c0-102">CallbackBehavior</span></span>

<span data-ttu-id="7a7c0-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="7a7c0-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a7c0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7a7c0-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7a7c0-105">Metody</span><span class="sxs-lookup"><span data-stu-id="7a7c0-105">Methods</span></span>  

 <span data-ttu-id="7a7c0-106">Klasa CallbackBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7a7c0-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7a7c0-107">Properties</span></span>  

 <span data-ttu-id="7a7c0-108">Klasa CallbackBehavior ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="7a7c0-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="7a7c0-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="7a7c0-109">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="7a7c0-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7a7c0-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a7c0-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-112">W przypadku wartości true sesja jest automatycznie zamykana, gdy usługa zamyka sesję dupleksową.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="7a7c0-113">Obsługują</span><span class="sxs-lookup"><span data-stu-id="7a7c0-113">ConcurrencyMode</span></span>  

 <span data-ttu-id="7a7c0-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7a7c0-114">Data type: string</span></span>  
<span data-ttu-id="7a7c0-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-116">Określa, czy usługa obsługuje jeden wątek, wiele wątków lub wywołania współużytkowane.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="7a7c0-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="7a7c0-117">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="7a7c0-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7a7c0-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a7c0-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-120">Wartość określająca, czy w sieci należy wysyłać nieznane dane serializacji.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="7a7c0-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="7a7c0-121">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="7a7c0-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7a7c0-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a7c0-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-124">Po włączeniu szczegółowe informacje o wyjątkach wywołania zwrotnego są dołączone do błędów zwróconych do usługi.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="7a7c0-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="7a7c0-125">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="7a7c0-126">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7a7c0-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a7c0-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-128">Maksymalna liczba elementów dozwolona w serializowanym obiekcie.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="7a7c0-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="7a7c0-129">UseSynchronizationContext</span></span>  

 <span data-ttu-id="7a7c0-130">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7a7c0-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a7c0-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-132">Określa, czy do wybierania wątku wykonywania ma być używany bieżący kontekst synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="7a7c0-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="7a7c0-133">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="7a7c0-134">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7a7c0-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a7c0-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7a7c0-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a7c0-136">Określa, czy system lub aplikacja wymusza przetwarzanie nagłówka MustUnderstand protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a7c0-137">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7a7c0-137">Requirements</span></span>  
  
|<span data-ttu-id="7a7c0-138">PLIK</span><span class="sxs-lookup"><span data-stu-id="7a7c0-138">MOF</span></span>|<span data-ttu-id="7a7c0-139">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7a7c0-140">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="7a7c0-140">Namespace</span></span>|<span data-ttu-id="7a7c0-141">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7a7c0-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a7c0-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7a7c0-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
