---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273259"
---
# <a name="serviceappdomain"></a><span data-ttu-id="bff28-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="bff28-102">ServiceAppDomain</span></span>

<span data-ttu-id="bff28-103">Mapuje usługę do domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bff28-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff28-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bff28-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bff28-105">Metody</span><span class="sxs-lookup"><span data-stu-id="bff28-105">Methods</span></span>  

 <span data-ttu-id="bff28-106">Klasa serviceappdomain nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="bff28-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bff28-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="bff28-107">Properties</span></span>  

 <span data-ttu-id="bff28-108">Klasa serviceappdomain ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="bff28-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="bff28-109">ref</span><span class="sxs-lookup"><span data-stu-id="bff28-109">ref</span></span>  

 <span data-ttu-id="bff28-110">Typ danych: usługa</span><span class="sxs-lookup"><span data-stu-id="bff28-110">Data type: Service</span></span>  
<span data-ttu-id="bff28-111">Kwalifikatory: klucz</span><span class="sxs-lookup"><span data-stu-id="bff28-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="bff28-112">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="bff28-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bff28-113">Usługa tej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bff28-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="bff28-114">ref</span><span class="sxs-lookup"><span data-stu-id="bff28-114">ref</span></span>  

 <span data-ttu-id="bff28-115">Typ danych: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="bff28-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="bff28-116">Kwalifikatory: klucz</span><span class="sxs-lookup"><span data-stu-id="bff28-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="bff28-117">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="bff28-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bff28-118">Zawiera właściwości domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bff28-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bff28-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bff28-119">Requirements</span></span>  
  
|<span data-ttu-id="bff28-120">PLIK</span><span class="sxs-lookup"><span data-stu-id="bff28-120">MOF</span></span>|<span data-ttu-id="bff28-121">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="bff28-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bff28-122">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="bff28-122">Namespace</span></span>|<span data-ttu-id="bff28-123">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bff28-123">Defined in root\ServiceModel</span></span>|
