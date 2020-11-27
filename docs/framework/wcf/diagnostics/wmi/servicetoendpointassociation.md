---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273948"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="ab3d0-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="ab3d0-102">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="ab3d0-103">Mapuje usługę do punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="ab3d0-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab3d0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ab3d0-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ab3d0-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ab3d0-105">Methods</span></span>  

 <span data-ttu-id="ab3d0-106">Klasa ServiceToEndpointAssociation nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="ab3d0-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ab3d0-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ab3d0-107">Properties</span></span>  

 <span data-ttu-id="ab3d0-108">Klasa ServiceToEndpointAssociation ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="ab3d0-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ab3d0-109">ref</span><span class="sxs-lookup"><span data-stu-id="ab3d0-109">ref</span></span>  

 <span data-ttu-id="ab3d0-110">Typ danych: usługa</span><span class="sxs-lookup"><span data-stu-id="ab3d0-110">Data type: Service</span></span>  
  
 <span data-ttu-id="ab3d0-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ab3d0-111">Access type: Read-only</span></span>  
<span data-ttu-id="ab3d0-112">Kwalifikatory: klucz</span><span class="sxs-lookup"><span data-stu-id="ab3d0-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="ab3d0-113">Usługa skojarzona z punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="ab3d0-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ab3d0-114">ref</span><span class="sxs-lookup"><span data-stu-id="ab3d0-114">ref</span></span>  

 <span data-ttu-id="ab3d0-115">Typ danych: punkt końcowy</span><span class="sxs-lookup"><span data-stu-id="ab3d0-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="ab3d0-116">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ab3d0-116">Access type: Read-only</span></span>  
<span data-ttu-id="ab3d0-117">Kwalifikatory: klucz</span><span class="sxs-lookup"><span data-stu-id="ab3d0-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="ab3d0-118">Punkt końcowy skojarzony z usługą.</span><span class="sxs-lookup"><span data-stu-id="ab3d0-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab3d0-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ab3d0-119">Requirements</span></span>  
  
|<span data-ttu-id="ab3d0-120">PLIK</span><span class="sxs-lookup"><span data-stu-id="ab3d0-120">MOF</span></span>|<span data-ttu-id="ab3d0-121">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ab3d0-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ab3d0-122">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ab3d0-122">Namespace</span></span>|<span data-ttu-id="ab3d0-123">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ab3d0-123">Defined in root\ServiceModel</span></span>|
