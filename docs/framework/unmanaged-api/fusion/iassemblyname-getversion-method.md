---
title: IAssemblyName::GetVersion — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
ms.openlocfilehash: 6f37979c7a4873a7751db0296dc7d485c3444561
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715904"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="91243-102">IAssemblyName::GetVersion — Metoda</span><span class="sxs-lookup"><span data-stu-id="91243-102">IAssemblyName::GetVersion Method</span></span>

<span data-ttu-id="91243-103">Pobiera informacje o wersji zestawu, do którego odwołuje się ten obiekt [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="91243-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91243-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="91243-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91243-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="91243-105">Parameters</span></span>  

 `pdwVersionHi`  
 <span data-ttu-id="91243-106">określoną Wysoka 32 bitów wersji.</span><span class="sxs-lookup"><span data-stu-id="91243-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="91243-107">określoną Niska 32 bitów wersji.</span><span class="sxs-lookup"><span data-stu-id="91243-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91243-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="91243-108">Requirements</span></span>  

 <span data-ttu-id="91243-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91243-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91243-110">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="91243-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="91243-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91243-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91243-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="91243-112">See also</span></span>

- [<span data-ttu-id="91243-113">IAssemblyName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="91243-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
