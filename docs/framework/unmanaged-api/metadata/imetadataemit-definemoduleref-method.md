---
title: IMetaDataEmit::DefineModuleRef — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
ms.openlocfilehash: 96d24705d80dabcda691edec497a4a30b6d37dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719557"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="358fc-102">IMetaDataEmit::DefineModuleRef — Metoda</span><span class="sxs-lookup"><span data-stu-id="358fc-102">IMetaDataEmit::DefineModuleRef Method</span></span>

<span data-ttu-id="358fc-103">Tworzy sygnaturę metadanych dla modułu o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="358fc-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="358fc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="358fc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="358fc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="358fc-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="358fc-106">podczas Nazwa innego pliku metadanych (zazwyczaj jest to biblioteka DLL).</span><span class="sxs-lookup"><span data-stu-id="358fc-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="358fc-107">Jest to tylko nazwa pliku.</span><span class="sxs-lookup"><span data-stu-id="358fc-107">This is the file name only.</span></span> <span data-ttu-id="358fc-108">Nie należy używać pełnej nazwy ścieżki.</span><span class="sxs-lookup"><span data-stu-id="358fc-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="358fc-109">określoną Przypisany `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="358fc-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="358fc-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="358fc-110">Requirements</span></span>  

 <span data-ttu-id="358fc-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="358fc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="358fc-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="358fc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="358fc-113">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="358fc-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="358fc-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="358fc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358fc-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="358fc-115">See also</span></span>

- [<span data-ttu-id="358fc-116">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="358fc-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="358fc-117">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="358fc-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
