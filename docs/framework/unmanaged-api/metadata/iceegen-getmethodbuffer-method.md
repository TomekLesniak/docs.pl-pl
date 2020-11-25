---
title: ICeeGen::GetMethodBuffer — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
ms.openlocfilehash: e9c2dab9f30be6e5eea8f6570b297f8df11b6fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715334"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="63d30-102">ICeeGen::GetMethodBuffer — Metoda</span><span class="sxs-lookup"><span data-stu-id="63d30-102">ICeeGen::GetMethodBuffer Method</span></span>

<span data-ttu-id="63d30-103">Pobiera bufor odpowiedniego rozmiaru dla metody pod określonym względnym adresem wirtualnym.</span><span class="sxs-lookup"><span data-stu-id="63d30-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="63d30-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="63d30-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d30-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="63d30-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d30-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="63d30-106">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="63d30-107">podczas Względny adres wirtualny metody, dla której ma zostać zwrócony bufor.</span><span class="sxs-lookup"><span data-stu-id="63d30-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="63d30-108">określoną Wskaźnik do zwróconego buforu.</span><span class="sxs-lookup"><span data-stu-id="63d30-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d30-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="63d30-109">Requirements</span></span>  

 <span data-ttu-id="63d30-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d30-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d30-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="63d30-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63d30-112">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63d30-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63d30-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d30-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d30-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="63d30-114">See also</span></span>

- [<span data-ttu-id="63d30-115">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="63d30-115">ICeeGen Interface</span></span>](iceegen-interface.md)
