---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: c5bb7813a680c89eb90f4ccf4ed6f09a831c8095
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262206"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="dd291-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="dd291-102">XmlDictionaryReaderQuotas</span></span>

<span data-ttu-id="dd291-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="dd291-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd291-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dd291-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dd291-105">Metody</span><span class="sxs-lookup"><span data-stu-id="dd291-105">Methods</span></span>  

 <span data-ttu-id="dd291-106">Klasa XmlDictionaryReaderQuotas nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="dd291-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dd291-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="dd291-107">Properties</span></span>  

 <span data-ttu-id="dd291-108">Klasa XmlDictionaryReaderQuotas ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="dd291-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="dd291-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="dd291-109">MaxArrayLength</span></span>  

 <span data-ttu-id="dd291-110">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="dd291-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="dd291-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="dd291-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd291-112">Maksymalna dozwolona długość tablicy.</span><span class="sxs-lookup"><span data-stu-id="dd291-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="dd291-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="dd291-113">MaxBytesPerRead</span></span>  

 <span data-ttu-id="dd291-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="dd291-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="dd291-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="dd291-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd291-116">Maksymalna dozwolona liczba bajtów zwracana dla każdego odczytu.</span><span class="sxs-lookup"><span data-stu-id="dd291-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="dd291-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="dd291-117">MaxDepth</span></span>  

 <span data-ttu-id="dd291-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="dd291-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="dd291-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="dd291-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd291-120">Maksymalna głębokość zagnieżdżenia węzłów dla każdego odczytu.</span><span class="sxs-lookup"><span data-stu-id="dd291-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="dd291-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="dd291-121">MaxNameTableCharCount</span></span>  

 <span data-ttu-id="dd291-122">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="dd291-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="dd291-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="dd291-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd291-124">Maksymalna dozwolona liczba znaków w nazwie tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd291-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="dd291-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="dd291-125">MaxStringContentLength</span></span>  

 <span data-ttu-id="dd291-126">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="dd291-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="dd291-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="dd291-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd291-128">Maksymalna dozwolona liczba znaków w zawartości elementu XML.</span><span class="sxs-lookup"><span data-stu-id="dd291-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd291-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dd291-129">Requirements</span></span>  
  
|<span data-ttu-id="dd291-130">PLIK</span><span class="sxs-lookup"><span data-stu-id="dd291-130">MOF</span></span>|<span data-ttu-id="dd291-131">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="dd291-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dd291-132">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="dd291-132">Namespace</span></span>|<span data-ttu-id="dd291-133">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dd291-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd291-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dd291-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
