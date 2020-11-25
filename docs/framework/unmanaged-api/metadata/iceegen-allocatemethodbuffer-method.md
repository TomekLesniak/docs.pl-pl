---
title: ICeeGen::AllocateMethodBuffer — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: e1849eb95401e3637a1fd1b00715332f9886071e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715527"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="76174-102">ICeeGen::AllocateMethodBuffer — Metoda</span><span class="sxs-lookup"><span data-stu-id="76174-102">ICeeGen::AllocateMethodBuffer Method</span></span>

<span data-ttu-id="76174-103">Tworzy bufor o określonym rozmiarze dla metody i pobiera względny adres wirtualny metody.</span><span class="sxs-lookup"><span data-stu-id="76174-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="76174-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="76174-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76174-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="76174-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76174-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="76174-106">Parameters</span></span>  

 `cchBuffer`  
 <span data-ttu-id="76174-107">podczas Długość buforu do utworzenia.</span><span class="sxs-lookup"><span data-stu-id="76174-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="76174-108">określoną Zwrócony bufor.</span><span class="sxs-lookup"><span data-stu-id="76174-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="76174-109">określoną Względny adres wirtualny metody.</span><span class="sxs-lookup"><span data-stu-id="76174-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76174-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="76174-110">Requirements</span></span>  

 <span data-ttu-id="76174-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76174-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76174-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="76174-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76174-113">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76174-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76174-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76174-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76174-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="76174-115">See also</span></span>

- [<span data-ttu-id="76174-116">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="76174-116">ICeeGen Interface</span></span>](iceegen-interface.md)
