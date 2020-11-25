---
title: ICeeGen::AddSectionReloc — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
ms.openlocfilehash: 87a5224247c2d94613de482fbaa34bf978198bf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715540"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="ad65d-102">ICeeGen::AddSectionReloc — Metoda</span><span class="sxs-lookup"><span data-stu-id="ad65d-102">ICeeGen::AddSectionReloc Method</span></span>

<span data-ttu-id="ad65d-103">Dodaje instrukcję. reloc do bazy kodu.</span><span class="sxs-lookup"><span data-stu-id="ad65d-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="ad65d-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="ad65d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad65d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ad65d-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad65d-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="ad65d-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="ad65d-107">podczas Sekcja kodu w pamięci, do której ma zostać dodana Instrukcja. reloc.</span><span class="sxs-lookup"><span data-stu-id="ad65d-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="ad65d-108">podczas Przesunięcie sekcji.</span><span class="sxs-lookup"><span data-stu-id="ad65d-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="ad65d-109">podczas Sekcja, do której `offset` odwołuje się.</span><span class="sxs-lookup"><span data-stu-id="ad65d-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="ad65d-110">podczas Jedna z wartości [CeeSectionRelocType —](ceesectionreloctype-enumeration.md) , wskazując rodzaj instrukcji. reloc, która ma zostać dodana.</span><span class="sxs-lookup"><span data-stu-id="ad65d-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad65d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ad65d-111">Requirements</span></span>  

 <span data-ttu-id="ad65d-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad65d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad65d-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad65d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad65d-114">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad65d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad65d-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad65d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad65d-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ad65d-116">See also</span></span>

- [<span data-ttu-id="ad65d-117">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ad65d-117">ICeeGen Interface</span></span>](iceegen-interface.md)
