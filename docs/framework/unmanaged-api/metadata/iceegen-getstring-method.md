---
title: ICeeGen::GetString — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: 9d14ec33128596a148ca3509a49c8c97fafe82d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723106"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="6d33e-102">ICeeGen::GetString — Metoda</span><span class="sxs-lookup"><span data-stu-id="6d33e-102">ICeeGen::GetString Method</span></span>

<span data-ttu-id="6d33e-103">Pobiera ciąg przechowywany w określonym względnym adresie wirtualnym.</span><span class="sxs-lookup"><span data-stu-id="6d33e-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="6d33e-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="6d33e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d33e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6d33e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d33e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="6d33e-106">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="6d33e-107">podczas Względny adres wirtualny ciągu do zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="6d33e-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="6d33e-108">określoną Zwrócony ciąg.</span><span class="sxs-lookup"><span data-stu-id="6d33e-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d33e-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6d33e-109">Requirements</span></span>  

 <span data-ttu-id="6d33e-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d33e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d33e-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6d33e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d33e-112">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d33e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d33e-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d33e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d33e-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6d33e-114">See also</span></span>

- [<span data-ttu-id="6d33e-115">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6d33e-115">ICeeGen Interface</span></span>](iceegen-interface.md)
