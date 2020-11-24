---
title: ICeeGen::TruncateSection — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 3005db62bba4089c669a00f62e3c1e62f9e1dae9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685711"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="710d6-102">ICeeGen::TruncateSection — Metoda</span><span class="sxs-lookup"><span data-stu-id="710d6-102">ICeeGen::TruncateSection Method</span></span>

<span data-ttu-id="710d6-103">Obcina określoną sekcję kodu o określoną długość.</span><span class="sxs-lookup"><span data-stu-id="710d6-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="710d6-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="710d6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710d6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="710d6-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="710d6-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="710d6-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="710d6-107">podczas Sekcja do obcięcia.</span><span class="sxs-lookup"><span data-stu-id="710d6-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="710d6-108">podczas Długość w bajtach, przez którą ma zostać obcięta sekcja.</span><span class="sxs-lookup"><span data-stu-id="710d6-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="710d6-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="710d6-109">Remarks</span></span>  

 <span data-ttu-id="710d6-110">Wywołanie `TruncateSection` tylko wtedy, gdy istnieją specjalne wymagania sekcji, które nie są obsługiwane przez inne metody.</span><span class="sxs-lookup"><span data-stu-id="710d6-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="710d6-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="710d6-111">Requirements</span></span>  

 <span data-ttu-id="710d6-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="710d6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="710d6-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="710d6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="710d6-114">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="710d6-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="710d6-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="710d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710d6-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="710d6-116">See also</span></span>

- [<span data-ttu-id="710d6-117">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="710d6-117">ICeeGen Interface</span></span>](iceegen-interface.md)
