---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: dba4abd74cdddeb2b641feec5902413fe0704b1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262297"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="8a343-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="8a343-102">ServiceDebugBehavior</span></span>

<span data-ttu-id="8a343-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="8a343-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a343-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8a343-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8a343-105">Metody</span><span class="sxs-lookup"><span data-stu-id="8a343-105">Methods</span></span>  

 <span data-ttu-id="8a343-106">Klasa ServiceDebugBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="8a343-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8a343-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="8a343-107">Properties</span></span>  

 <span data-ttu-id="8a343-108">Klasa ServiceDebugBehavior ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="8a343-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="8a343-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="8a343-109">HttpHelpPageEnabled</span></span>  

 <span data-ttu-id="8a343-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="8a343-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="8a343-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="8a343-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a343-112">Określa, czy usługa publikuje swoje WSDL pod adresem kontrolowanym przez `HttpGetUrl` atrybut.</span><span class="sxs-lookup"><span data-stu-id="8a343-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="8a343-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="8a343-113">HttpHelpPageUrl</span></span>  

 <span data-ttu-id="8a343-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="8a343-114">Data type: string</span></span>  
  
 <span data-ttu-id="8a343-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="8a343-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a343-116">Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a343-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="8a343-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="8a343-117">HttpsHelpPageEnabled</span></span>  

 <span data-ttu-id="8a343-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="8a343-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="8a343-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="8a343-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a343-120">Określa, czy usługa publikuje swoje WSDL za pośrednictwem protokołu HTTPS pod adresem kontrolowanym przez `HttpsGetUrl` atrybut.</span><span class="sxs-lookup"><span data-stu-id="8a343-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="8a343-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="8a343-121">HttpsHelpPageUrl</span></span>  

 <span data-ttu-id="8a343-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="8a343-122">Data type: string</span></span>  
  
 <span data-ttu-id="8a343-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="8a343-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a343-124">Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8a343-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="8a343-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="8a343-125">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="8a343-126">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="8a343-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="8a343-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="8a343-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a343-128">Określa, czy informacje o zarządzanych wyjątkach mają być dołączane do szczegółowych informacji o błędach SOAP zwracanych do klientów na potrzeby debugowania.</span><span class="sxs-lookup"><span data-stu-id="8a343-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a343-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8a343-129">Requirements</span></span>  
  
|<span data-ttu-id="8a343-130">PLIK</span><span class="sxs-lookup"><span data-stu-id="8a343-130">MOF</span></span>|<span data-ttu-id="8a343-131">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="8a343-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8a343-132">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="8a343-132">Namespace</span></span>|<span data-ttu-id="8a343-133">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8a343-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a343-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8a343-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
