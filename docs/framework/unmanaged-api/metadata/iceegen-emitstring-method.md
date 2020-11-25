---
title: ICeeGen::EmitString — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: b9c907868df31da8d995c6a6b86db258d395335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715449"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="2c82e-102">ICeeGen::EmitString — Metoda</span><span class="sxs-lookup"><span data-stu-id="2c82e-102">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="2c82e-103">Emituje określony ciąg do bazy kodu.</span><span class="sxs-lookup"><span data-stu-id="2c82e-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="2c82e-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="2c82e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c82e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2c82e-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c82e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="2c82e-106">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="2c82e-107">podczas Ciąg do emisji.</span><span class="sxs-lookup"><span data-stu-id="2c82e-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="2c82e-108">określoną Względny adres wirtualny emitowanego ciągu.</span><span class="sxs-lookup"><span data-stu-id="2c82e-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c82e-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2c82e-109">Requirements</span></span>  

 <span data-ttu-id="2c82e-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c82e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c82e-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c82e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c82e-112">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c82e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c82e-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c82e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c82e-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2c82e-114">See also</span></span>

- [<span data-ttu-id="2c82e-115">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2c82e-115">ICeeGen Interface</span></span>](iceegen-interface.md)
