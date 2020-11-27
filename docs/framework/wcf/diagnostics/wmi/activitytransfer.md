---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291118"
---
# <a name="activitytransfer"></a><span data-ttu-id="2908f-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="2908f-102">ActivityTransfer</span></span>

<span data-ttu-id="2908f-103">Zdarzenie transferu działania</span><span class="sxs-lookup"><span data-stu-id="2908f-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2908f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2908f-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2908f-105">Metody</span><span class="sxs-lookup"><span data-stu-id="2908f-105">Methods</span></span>  

 <span data-ttu-id="2908f-106">Klasa ActivityTransfer nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="2908f-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2908f-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="2908f-107">Properties</span></span>  

 <span data-ttu-id="2908f-108">Klasa ActivityTransfer ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="2908f-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="2908f-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="2908f-109">ActivityID</span></span>  
  
- <span data-ttu-id="2908f-110">Typ danych: obiekt</span><span class="sxs-lookup"><span data-stu-id="2908f-110">Data type: object</span></span>  
    <span data-ttu-id="2908f-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="2908f-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="2908f-112">Identyfikator działania</span><span class="sxs-lookup"><span data-stu-id="2908f-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="2908f-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="2908f-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="2908f-114">Typ danych: obiekt</span><span class="sxs-lookup"><span data-stu-id="2908f-114">Data type: object</span></span>  
    <span data-ttu-id="2908f-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="2908f-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="2908f-116">IDENTYFIKATOR powiązanego działania</span><span class="sxs-lookup"><span data-stu-id="2908f-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2908f-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2908f-117">Requirements</span></span>  
  
|<span data-ttu-id="2908f-118">PLIK</span><span class="sxs-lookup"><span data-stu-id="2908f-118">MOF</span></span>|<span data-ttu-id="2908f-119">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="2908f-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2908f-120">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="2908f-120">Namespace</span></span>|<span data-ttu-id="2908f-121">Zdefiniowane w root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="2908f-121">Defined in root\ServiceModel.</span></span>|
