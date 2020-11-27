---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 3bcf205964a22cdb418d0158e5ee6439169538ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273987"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="9396a-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="9396a-102">ServiceThrottlingBehavior</span></span>

<span data-ttu-id="9396a-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="9396a-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9396a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9396a-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9396a-105">Metody</span><span class="sxs-lookup"><span data-stu-id="9396a-105">Methods</span></span>  

 <span data-ttu-id="9396a-106">Klasa elementu ServiceThrottlingBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="9396a-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9396a-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="9396a-107">Properties</span></span>  

 <span data-ttu-id="9396a-108">Klasa elementu ServiceThrottlingBehavior ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="9396a-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="9396a-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="9396a-109">MaxConcurrentCalls</span></span>  

 <span data-ttu-id="9396a-110">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="9396a-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="9396a-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="9396a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9396a-112">Maksymalna liczba komunikatów aktywnie przetwarzanych w ramach wszystkich obiektów dyspozytora w ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="9396a-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="9396a-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="9396a-113">MaxConcurrentInstances</span></span>  

 <span data-ttu-id="9396a-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="9396a-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9396a-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="9396a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9396a-116">Maksymalna liczba obiektów usługi, które mogą być wykonywane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="9396a-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="9396a-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="9396a-117">MaxConcurrentSessions</span></span>  

 <span data-ttu-id="9396a-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="9396a-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="9396a-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="9396a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9396a-120">Maksymalna liczba sesji, które host może zaakceptować jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="9396a-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9396a-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9396a-121">Requirements</span></span>  
  
|<span data-ttu-id="9396a-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="9396a-122">MOF</span></span>|<span data-ttu-id="9396a-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="9396a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9396a-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="9396a-124">Namespace</span></span>|<span data-ttu-id="9396a-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9396a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9396a-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9396a-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
