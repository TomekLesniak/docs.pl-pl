---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: e3716d42d479bcbdfd900b4fd2e335576a71574b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295603"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="7e378-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="7e378-102">ServiceBehaviorAttribute</span></span>

<span data-ttu-id="7e378-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="7e378-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e378-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7e378-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7e378-105">Metody</span><span class="sxs-lookup"><span data-stu-id="7e378-105">Methods</span></span>  

 <span data-ttu-id="7e378-106">Klasa ServiceBehaviorAttribute nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="7e378-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7e378-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7e378-107">Properties</span></span>  

 <span data-ttu-id="7e378-108">Klasa ServiceBehaviorAttribute ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="7e378-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="7e378-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="7e378-109">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="7e378-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-112">Wskazuje, czy sesja ma być automatycznie zamykana, gdy klient zamknie sesję wyjściową.</span><span class="sxs-lookup"><span data-stu-id="7e378-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="7e378-113">Obsługują</span><span class="sxs-lookup"><span data-stu-id="7e378-113">ConcurrencyMode</span></span>  

 <span data-ttu-id="7e378-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7e378-114">Data type: string</span></span>  
<span data-ttu-id="7e378-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-116">Wskazuje, czy usługa obsługuje jeden wątek, wiele wątków lub wywołania współużytkowane.</span><span class="sxs-lookup"><span data-stu-id="7e378-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="7e378-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="7e378-117">ConfigurationName</span></span>  

 <span data-ttu-id="7e378-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7e378-118">Data type: string</span></span>  
  
 <span data-ttu-id="7e378-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-120">Nazwa konfiguracji usługi.</span><span class="sxs-lookup"><span data-stu-id="7e378-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="7e378-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="7e378-121">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="7e378-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-124">Określa, czy wysyłać nieznane dane serializacji do sieci.</span><span class="sxs-lookup"><span data-stu-id="7e378-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="7e378-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="7e378-125">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="7e378-126">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-128">Określa, czy informacje o zarządzanych wyjątkach mają być dołączane do szczegółowych informacji o błędach SOAP zwracanych do klientów na potrzeby debugowania.</span><span class="sxs-lookup"><span data-stu-id="7e378-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="7e378-129">Tryb InstanceContextmode</span><span class="sxs-lookup"><span data-stu-id="7e378-129">InstanceContextMode</span></span>  

 <span data-ttu-id="7e378-130">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7e378-130">Data type: string</span></span>  
  
 <span data-ttu-id="7e378-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-132">Określa, kiedy tworzony jest nowy obiekt usługi.</span><span class="sxs-lookup"><span data-stu-id="7e378-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="7e378-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="7e378-133">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="7e378-134">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="7e378-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="7e378-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-136">Maksymalna liczba elementów dozwolona w serializowanym obiekcie.</span><span class="sxs-lookup"><span data-stu-id="7e378-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="7e378-137">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7e378-137">Name</span></span>  

 <span data-ttu-id="7e378-138">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7e378-138">Data type: string</span></span>  
  
 <span data-ttu-id="7e378-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-140">Atrybut nazwy usługi w języku WSDL.</span><span class="sxs-lookup"><span data-stu-id="7e378-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="7e378-141">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="7e378-141">Namespace</span></span>  

 <span data-ttu-id="7e378-142">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7e378-142">Data type: string</span></span>  
  
 <span data-ttu-id="7e378-143">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-144">Docelowa przestrzeń nazw usługi w języku WSDL.</span><span class="sxs-lookup"><span data-stu-id="7e378-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="7e378-145">Ustawion</span><span class="sxs-lookup"><span data-stu-id="7e378-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  

 <span data-ttu-id="7e378-146">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-147">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-148">Określa, czy obiekt usługi jest odtwarzany po zakończeniu bieżącej transakcji.</span><span class="sxs-lookup"><span data-stu-id="7e378-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="7e378-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="7e378-149">TransactionAutoCompleteOnSessionClose</span></span>  

 <span data-ttu-id="7e378-150">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-151">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-152">Określa, czy oczekujące transakcje są kończone podczas zamykania bieżącej sesji.</span><span class="sxs-lookup"><span data-stu-id="7e378-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="7e378-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="7e378-153">TransactionIsolationLevel</span></span>  

 <span data-ttu-id="7e378-154">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7e378-154">Data type: string</span></span>  
  
 <span data-ttu-id="7e378-155">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-156">Określa poziom izolacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="7e378-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="7e378-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="7e378-157">TransactionTimeout</span></span>  

 <span data-ttu-id="7e378-158">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="7e378-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="7e378-159">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-160">Okres, w którym transakcja musi zostać zakończona.</span><span class="sxs-lookup"><span data-stu-id="7e378-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="7e378-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="7e378-161">UseSynchronizationContext</span></span>  

 <span data-ttu-id="7e378-162">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-163">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-164">Określa, czy używać bieżącego kontekstu synchronizacji do wybierania wykonywania wątku.</span><span class="sxs-lookup"><span data-stu-id="7e378-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="7e378-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="7e378-165">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="7e378-166">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="7e378-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="7e378-167">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7e378-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e378-168">Określa, czy system lub aplikacja wymusza przetwarzanie nagłówka MustUnderstand protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="7e378-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e378-169">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7e378-169">Requirements</span></span>  
  
|<span data-ttu-id="7e378-170">PLIK</span><span class="sxs-lookup"><span data-stu-id="7e378-170">MOF</span></span>|<span data-ttu-id="7e378-171">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="7e378-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7e378-172">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="7e378-172">Namespace</span></span>|<span data-ttu-id="7e378-173">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7e378-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e378-174">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7e378-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
