---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 921a880dad0d77558a70dff8a09f75c25a3cbb8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262284"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="5d5af-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="5d5af-102">ServiceMetadataBehavior</span></span>

<span data-ttu-id="5d5af-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="5d5af-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5af-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5d5af-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5d5af-105">Metody</span><span class="sxs-lookup"><span data-stu-id="5d5af-105">Methods</span></span>  

 <span data-ttu-id="5d5af-106">Klasa ServiceMetadataBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="5d5af-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5d5af-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="5d5af-107">Properties</span></span>  

 <span data-ttu-id="5d5af-108">Klasa ServiceMetadataBehavior ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="5d5af-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="5d5af-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="5d5af-109">ExternalMetadataLocation</span></span>  

 <span data-ttu-id="5d5af-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="5d5af-110">Data type: string</span></span>  
  
 <span data-ttu-id="5d5af-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="5d5af-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d5af-112">Ustawia lokalizację, w której usługa przekierowuje żądania metadanych.</span><span class="sxs-lookup"><span data-stu-id="5d5af-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="5d5af-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="5d5af-113">HttpGetEnabled</span></span>  

 <span data-ttu-id="5d5af-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="5d5af-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d5af-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="5d5af-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d5af-116">Określa, czy usługa publikuje swoje WSDL pod adresem kontrolowanym przez `HttpGetUrl` atrybut.</span><span class="sxs-lookup"><span data-stu-id="5d5af-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="5d5af-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="5d5af-117">HttpGetUrl</span></span>  

 <span data-ttu-id="5d5af-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="5d5af-118">Data type: string</span></span>  
  
 <span data-ttu-id="5d5af-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="5d5af-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d5af-120">Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="5d5af-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="5d5af-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="5d5af-121">HttpsGetEnabled</span></span>  

 <span data-ttu-id="5d5af-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="5d5af-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5d5af-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="5d5af-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d5af-124">Określa, czy usługa publikuje swoje WSDL za pośrednictwem protokołu HTTPS pod adresem kontrolowanym przez `HttpsGetUrl` atrybut.</span><span class="sxs-lookup"><span data-stu-id="5d5af-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="5d5af-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="5d5af-125">HttpsGetUrl</span></span>  

 <span data-ttu-id="5d5af-126">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="5d5af-126">Data type: string</span></span>  
  
 <span data-ttu-id="5d5af-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="5d5af-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d5af-128">Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5d5af-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d5af-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5d5af-129">Requirements</span></span>  
  
|<span data-ttu-id="5d5af-130">PLIK</span><span class="sxs-lookup"><span data-stu-id="5d5af-130">MOF</span></span>|<span data-ttu-id="5d5af-131">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="5d5af-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5d5af-132">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="5d5af-132">Namespace</span></span>|<span data-ttu-id="5d5af-133">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5d5af-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d5af-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5d5af-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
