---
title: IMetaDataEmit::DefineMethodImpl — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 24a7c5bca1287e55f3eb06d63e1fed8da37eb3b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719570"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="2a122-102">IMetaDataEmit::DefineMethodImpl — Metoda</span><span class="sxs-lookup"><span data-stu-id="2a122-102">IMetaDataEmit::DefineMethodImpl Method</span></span>

<span data-ttu-id="2a122-103">Tworzy definicję dla implementacji metody dziedziczonej z interfejsu i zwraca token do tej definicji implementacji metody.</span><span class="sxs-lookup"><span data-stu-id="2a122-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a122-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2a122-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a122-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2a122-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="2a122-106">podczas `mdTypedef` Token klasy implementującej.</span><span class="sxs-lookup"><span data-stu-id="2a122-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="2a122-107">podczas `mdMethodDef` Token lub `mdMemberRef` treść kodu.</span><span class="sxs-lookup"><span data-stu-id="2a122-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="2a122-108">podczas `mdMethodDef` Token lub `mdMemberRef` metoda interfejsu, która jest implementowana.</span><span class="sxs-lookup"><span data-stu-id="2a122-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a122-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2a122-109">Requirements</span></span>  

 <span data-ttu-id="2a122-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a122-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a122-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2a122-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a122-112">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a122-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a122-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a122-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a122-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2a122-114">See also</span></span>

- [<span data-ttu-id="2a122-115">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2a122-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2a122-116">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2a122-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
