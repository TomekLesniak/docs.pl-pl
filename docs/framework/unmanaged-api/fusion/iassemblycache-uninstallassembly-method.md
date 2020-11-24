---
title: IAssemblyCache::UninstallAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
ms.openlocfilehash: 36a2a609e95740ffc45722635a7e1f09e0ed5601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670787"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="0cff5-102">IAssemblyCache::UninstallAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="0cff5-102">IAssemblyCache::UninstallAssembly Method</span></span>

<span data-ttu-id="0cff5-103">Odinstalowuje określony zestaw z globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="0cff5-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cff5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0cff5-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cff5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0cff5-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="0cff5-106">podczas Flagi zdefiniowane w pliku Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="0cff5-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="0cff5-107">podczas Nazwa zestawu do odinstalowania.</span><span class="sxs-lookup"><span data-stu-id="0cff5-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="0cff5-108">podczas Struktura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) , która zawiera dane instalacji dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="0cff5-108">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="0cff5-109">[out, opcjonalne] Jedna z wartości dyspozycji zdefiniowanych w pliku Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="0cff5-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="0cff5-110">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="0cff5-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="0cff5-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="0cff5-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="0cff5-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="0cff5-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="0cff5-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="0cff5-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="0cff5-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="0cff5-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="0cff5-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="0cff5-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="0cff5-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="0cff5-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cff5-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0cff5-117">Requirements</span></span>  

 <span data-ttu-id="0cff5-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cff5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cff5-119">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0cff5-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0cff5-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cff5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cff5-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0cff5-121">See also</span></span>

- [<span data-ttu-id="0cff5-122">IAssemblyCache — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0cff5-122">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
