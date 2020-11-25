---
title: IAssemblyName::Clone — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
ms.openlocfilehash: ca528bdbd9662db373d1beeece803d6c43728f2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698614"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="ff637-102">IAssemblyName::Clone — Metoda</span><span class="sxs-lookup"><span data-stu-id="ff637-102">IAssemblyName::Clone Method</span></span>

<span data-ttu-id="ff637-103">Tworzy skróconą kopię tego obiektu [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ff637-103">Creates a shallow copy of this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff637-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ff637-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff637-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ff637-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="ff637-106">określoną Zwrócona kopia tego `IAssemblyName` obiektu.</span><span class="sxs-lookup"><span data-stu-id="ff637-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff637-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ff637-107">Requirements</span></span>  

 <span data-ttu-id="ff637-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff637-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff637-109">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ff637-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ff637-110">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff637-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff637-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ff637-111">See also</span></span>

- [<span data-ttu-id="ff637-112">IAssemblyName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ff637-112">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
