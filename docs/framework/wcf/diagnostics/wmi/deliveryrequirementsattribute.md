---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274052"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="ea785-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="ea785-102">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="ea785-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="ea785-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea785-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ea785-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ea785-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ea785-105">Methods</span></span>  

 <span data-ttu-id="ea785-106">Klasa element DeliveryRequirementsAttribute nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="ea785-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ea785-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ea785-107">Properties</span></span>  

 <span data-ttu-id="ea785-108">Klasa element DeliveryRequirementsAttribute ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="ea785-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="ea785-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="ea785-109">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="ea785-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ea785-110">Data type: string</span></span>  
  
 <span data-ttu-id="ea785-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ea785-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea785-112">Określa, czy powiązanie dla usługi obsługuje kontrakty.</span><span class="sxs-lookup"><span data-stu-id="ea785-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="ea785-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="ea785-113">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="ea785-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="ea785-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ea785-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ea785-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea785-116">Określa, czy powiązanie obsługuje uporządkowane komunikaty.</span><span class="sxs-lookup"><span data-stu-id="ea785-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="ea785-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="ea785-117">TargetContract</span></span>  

 <span data-ttu-id="ea785-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ea785-118">Data type: string</span></span>  
  
 <span data-ttu-id="ea785-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ea785-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea785-120">Kontrakt, do którego ma zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="ea785-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea785-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ea785-121">Requirements</span></span>  
  
|<span data-ttu-id="ea785-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="ea785-122">MOF</span></span>|<span data-ttu-id="ea785-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ea785-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ea785-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ea785-124">Namespace</span></span>|<span data-ttu-id="ea785-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ea785-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea785-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ea785-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
