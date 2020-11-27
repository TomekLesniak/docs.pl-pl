---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c618b5b41790b04a84b4c50fe47baa2c0cb05ab2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274104"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="f5b6d-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f5b6d-102">SymmetricSecurityBindingElement</span></span>

<span data-ttu-id="f5b6d-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f5b6d-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5b6d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f5b6d-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f5b6d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="f5b6d-105">Methods</span></span>  

 <span data-ttu-id="f5b6d-106">Klasa SymmetricSecurityBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="f5b6d-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f5b6d-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f5b6d-107">Properties</span></span>  

 <span data-ttu-id="f5b6d-108">Klasa SymmetricSecurityBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="f5b6d-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="f5b6d-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="f5b6d-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="f5b6d-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="f5b6d-110">Data type: string</span></span>  
  
 <span data-ttu-id="f5b6d-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f5b6d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5b6d-112">Kolejność szyfrowania i podpisywania wiadomości dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="f5b6d-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="f5b6d-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="f5b6d-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="f5b6d-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="f5b6d-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5b6d-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="f5b6d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5b6d-116">Czy powiązanie wymaga potwierdzenia podpisu.</span><span class="sxs-lookup"><span data-stu-id="f5b6d-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5b6d-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f5b6d-117">Requirements</span></span>  
  
|<span data-ttu-id="f5b6d-118">PLIK</span><span class="sxs-lookup"><span data-stu-id="f5b6d-118">MOF</span></span>|<span data-ttu-id="f5b6d-119">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="f5b6d-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f5b6d-120">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="f5b6d-120">Namespace</span></span>|<span data-ttu-id="f5b6d-121">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f5b6d-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5b6d-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f5b6d-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
