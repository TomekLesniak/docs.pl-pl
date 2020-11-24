---
title: IDefinitionAppId — Interfejs
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 1e6c42d8e74d2d3e7925c657c67832f662416e64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673872"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="824b9-102">IDefinitionAppId — Interfejs</span><span class="sxs-lookup"><span data-stu-id="824b9-102">IDefinitionAppId Interface</span></span>

<span data-ttu-id="824b9-103">Reprezentuje unikatowy identyfikator kodu, który definiuje aplikację w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="824b9-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="824b9-104">Metody</span><span class="sxs-lookup"><span data-stu-id="824b9-104">Methods</span></span>  
  
|<span data-ttu-id="824b9-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="824b9-105">Method</span></span>|<span data-ttu-id="824b9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="824b9-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="824b9-107">Pobiera sformatowany ciąg, który reprezentuje kod w tym `IDefinitionAppId` obiekcie.</span><span class="sxs-lookup"><span data-stu-id="824b9-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="824b9-108">Ustawia kod tego `IDefinitionAppId` obiektu na określoną wartość ciągu sformatowanego.</span><span class="sxs-lookup"><span data-stu-id="824b9-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="824b9-109">Pobiera wskaźnik interfejsu do obiektu [IEnumDefinitionIdentity —](ienumdefinitionidentity-interface.md) , który zawiera zestawy w bieżącej ścieżce aplikacji.</span><span class="sxs-lookup"><span data-stu-id="824b9-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="824b9-110">Ustawia ścieżkę aplikacji dla zestawu w bieżącym zakresie do wartości, do której odwołuje się określony obiekt [IDefinitionIdentity —](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="824b9-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="824b9-111">Pobiera wskaźnik do ciągu reprezentującego Identyfikator tokenu dla subskrypcji dla tego `IDefinitionAppId` obiektu.</span><span class="sxs-lookup"><span data-stu-id="824b9-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="824b9-112">Ustawia identyfikator tokenu dla subskrypcji dla tego `IDefinitionAppId` obiektu na określoną wartość ciągu.</span><span class="sxs-lookup"><span data-stu-id="824b9-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="824b9-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="824b9-113">Requirements</span></span>  

 <span data-ttu-id="824b9-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="824b9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="824b9-115">**Nagłówek:** Izolacja. h</span><span class="sxs-lookup"><span data-stu-id="824b9-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="824b9-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="824b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824b9-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="824b9-117">See also</span></span>

- [<span data-ttu-id="824b9-118">Interfejsy łączenia</span><span class="sxs-lookup"><span data-stu-id="824b9-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
