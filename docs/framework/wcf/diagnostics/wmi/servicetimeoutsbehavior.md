---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 867219130fc853f3ba2c1c2f807b1651f6480f13
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273974"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="3272b-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="3272b-102">ServiceTimeoutsBehavior</span></span>

<span data-ttu-id="3272b-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="3272b-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3272b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3272b-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3272b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="3272b-105">Methods</span></span>  

 <span data-ttu-id="3272b-106">Klasa ServiceTimeoutsBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="3272b-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3272b-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3272b-107">Properties</span></span>  

 <span data-ttu-id="3272b-108">Klasa ServiceTimeoutsBehavior ma następującą właściwość:</span><span class="sxs-lookup"><span data-stu-id="3272b-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="3272b-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="3272b-109">TransactionTimeout</span></span>  

 <span data-ttu-id="3272b-110">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="3272b-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="3272b-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="3272b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3272b-112">Okres, w którym transakcja musi zostać zakończona.</span><span class="sxs-lookup"><span data-stu-id="3272b-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3272b-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3272b-113">Requirements</span></span>  
  
|<span data-ttu-id="3272b-114">PLIK</span><span class="sxs-lookup"><span data-stu-id="3272b-114">MOF</span></span>|<span data-ttu-id="3272b-115">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="3272b-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3272b-116">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="3272b-116">Namespace</span></span>|<span data-ttu-id="3272b-117">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3272b-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3272b-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3272b-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
