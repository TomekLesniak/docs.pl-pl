---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273207"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="ad741-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="ad741-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="ad741-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="ad741-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad741-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ad741-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad741-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ad741-105">Methods</span></span>  

 <span data-ttu-id="ad741-106">Klasa ServiceAuthorizationBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="ad741-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad741-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ad741-107">Properties</span></span>  

 <span data-ttu-id="ad741-108">Klasa ServiceAuthorizationBehavior ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="ad741-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="ad741-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="ad741-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="ad741-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="ad741-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ad741-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ad741-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad741-112">Wartość, która kontroluje, czy usługa próbuje dokonać personifikacji przy użyciu poświadczeń dostarczonych przez komunikat przychodzący.</span><span class="sxs-lookup"><span data-stu-id="ad741-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="ad741-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="ad741-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="ad741-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad741-114">Data type: string</span></span>  
  
 <span data-ttu-id="ad741-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ad741-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad741-116">Podmiot zabezpieczeń używany do wykonywania operacji na serwerze.</span><span class="sxs-lookup"><span data-stu-id="ad741-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="ad741-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="ad741-117">RoleProvider</span></span>  

 <span data-ttu-id="ad741-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad741-118">Data type: string</span></span>  
  
 <span data-ttu-id="ad741-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ad741-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad741-120">Nazwa dostawcy roli ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ad741-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="ad741-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="ad741-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="ad741-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad741-122">Data type: string</span></span>  
  
 <span data-ttu-id="ad741-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ad741-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad741-124">Menedżer autoryzacji używany do autoryzacji niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="ad741-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad741-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ad741-125">Requirements</span></span>  
  
|<span data-ttu-id="ad741-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="ad741-126">MOF</span></span>|<span data-ttu-id="ad741-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ad741-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad741-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ad741-128">Namespace</span></span>|<span data-ttu-id="ad741-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad741-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad741-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ad741-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
