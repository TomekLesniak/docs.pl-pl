---
title: IAssemblyEnum::GetNextAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
ms.openlocfilehash: af43d9cf4d5aa790036a13d060fc6ccf113f335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719895"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="9f82b-102">IAssemblyEnum::GetNextAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="9f82b-102">IAssemblyEnum::GetNextAssembly Method</span></span>

<span data-ttu-id="9f82b-103">Pobiera wskaźnik do następnego [IAssemblyName](iassemblyname-interface.md) zawartego w tym obiekcie [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f82b-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f82b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9f82b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f82b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9f82b-105">Parameters</span></span>  

 `pvReserved`  
 <span data-ttu-id="9f82b-106">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="9f82b-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9f82b-107">`pvReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="9f82b-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="9f82b-108">określoną Zwrócony `IAssemblyName` wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="9f82b-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9f82b-109">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="9f82b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9f82b-110">`dwFlags` musi mieć wartość 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="9f82b-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f82b-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9f82b-111">Requirements</span></span>  

 <span data-ttu-id="9f82b-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f82b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f82b-113">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9f82b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9f82b-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f82b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f82b-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9f82b-115">See also</span></span>

- [<span data-ttu-id="9f82b-116">IAssemblyName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9f82b-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="9f82b-117">IAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9f82b-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
