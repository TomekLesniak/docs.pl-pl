---
title: IValidator — Interfejs
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: ce417402231d03828243bfb8bb7543c0a644a882
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700993"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="4d1c1-102">IValidator — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4d1c1-102">IValidator Interface</span></span>

<span data-ttu-id="4d1c1-103">Zapewnia metody sprawdzania poprawności przenośnych obrazów wykonywalnych (PE) i raportowania błędów walidacji.</span><span class="sxs-lookup"><span data-stu-id="4d1c1-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d1c1-104">Metody</span><span class="sxs-lookup"><span data-stu-id="4d1c1-104">Methods</span></span>  
  
|<span data-ttu-id="4d1c1-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="4d1c1-105">Method</span></span>|<span data-ttu-id="4d1c1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4d1c1-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4d1c1-107">Walidacja</span><span class="sxs-lookup"><span data-stu-id="4d1c1-107">Validate</span></span>|<span data-ttu-id="4d1c1-108">Sprawdza poprawność określonego pliku PE lub języka pośredniego firmy Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4d1c1-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="4d1c1-109">FormatEventInfo —</span><span class="sxs-lookup"><span data-stu-id="4d1c1-109">FormatEventInfo</span></span>|<span data-ttu-id="4d1c1-110">Pobiera komunikat o błędzie odpowiadający określonemu błędowi walidacji.</span><span class="sxs-lookup"><span data-stu-id="4d1c1-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d1c1-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4d1c1-111">Requirements</span></span>  

 <span data-ttu-id="4d1c1-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d1c1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d1c1-113">**Nagłówek:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="4d1c1-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="4d1c1-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d1c1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d1c1-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d1c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1c1-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4d1c1-116">See also</span></span>

- [<span data-ttu-id="4d1c1-117">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="4d1c1-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4d1c1-118">CorRuntimeHost — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="4d1c1-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
