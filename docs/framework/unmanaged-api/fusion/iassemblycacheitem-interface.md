---
title: IAssemblyCacheItem — Interfejs
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719947"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="23f94-102">IAssemblyCacheItem — Interfejs</span><span class="sxs-lookup"><span data-stu-id="23f94-102">IAssemblyCacheItem Interface</span></span>

<span data-ttu-id="23f94-103">Reprezentuje pojedynczy zestaw w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="23f94-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23f94-104">Metody</span><span class="sxs-lookup"><span data-stu-id="23f94-104">Methods</span></span>  
  
|<span data-ttu-id="23f94-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="23f94-105">Method</span></span>|<span data-ttu-id="23f94-106">Opis</span><span class="sxs-lookup"><span data-stu-id="23f94-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23f94-107">AbortItem, metoda</span><span class="sxs-lookup"><span data-stu-id="23f94-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="23f94-108">Zezwala na zestaw w globalnej pamięci podręcznej zestawów na wykonywanie operacji czyszczenia przed jego wydaniem.</span><span class="sxs-lookup"><span data-stu-id="23f94-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="23f94-109">Commit — metoda</span><span class="sxs-lookup"><span data-stu-id="23f94-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="23f94-110">Zatwierdza odwołanie do pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="23f94-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="23f94-111">CreateStream, metoda</span><span class="sxs-lookup"><span data-stu-id="23f94-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="23f94-112">Tworzy strumień o określonej nazwie i formacie.</span><span class="sxs-lookup"><span data-stu-id="23f94-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23f94-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="23f94-113">Requirements</span></span>  

 <span data-ttu-id="23f94-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23f94-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f94-115">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="23f94-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="23f94-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f94-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="23f94-117">See also</span></span>

- [<span data-ttu-id="23f94-118">Interfejsy łączenia</span><span class="sxs-lookup"><span data-stu-id="23f94-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="23f94-119">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="23f94-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="23f94-120">IAssemblyCache — Interfejs</span><span class="sxs-lookup"><span data-stu-id="23f94-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
