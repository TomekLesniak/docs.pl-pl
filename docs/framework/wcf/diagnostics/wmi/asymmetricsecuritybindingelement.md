---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255731"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="03a11-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="03a11-102">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="03a11-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="03a11-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a11-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="03a11-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="03a11-105">Metody</span><span class="sxs-lookup"><span data-stu-id="03a11-105">Methods</span></span>  

 <span data-ttu-id="03a11-106">Klasa element AsymmetricSecurityBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="03a11-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="03a11-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="03a11-107">Properties</span></span>  

 <span data-ttu-id="03a11-108">Klasa element AsymmetricSecurityBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="03a11-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="03a11-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="03a11-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="03a11-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="03a11-110">Data type: string</span></span>  
  
 <span data-ttu-id="03a11-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="03a11-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03a11-112">Kolejność szyfrowania i podpisywania wiadomości dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="03a11-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="03a11-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="03a11-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="03a11-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="03a11-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="03a11-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="03a11-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03a11-116">Czy powiązanie wymaga potwierdzenia podpisu.</span><span class="sxs-lookup"><span data-stu-id="03a11-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a11-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="03a11-117">Requirements</span></span>  
  
|<span data-ttu-id="03a11-118">PLIK</span><span class="sxs-lookup"><span data-stu-id="03a11-118">MOF</span></span>|<span data-ttu-id="03a11-119">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="03a11-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="03a11-120">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="03a11-120">Namespace</span></span>|<span data-ttu-id="03a11-121">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="03a11-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03a11-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="03a11-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
