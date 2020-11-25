---
title: ICorDebugModule::GetBaseAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: 4562318c87b79fba5f3d99860ee438c0144e9aae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710249"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="dcb7e-102">ICorDebugModule::GetBaseAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="dcb7e-102">ICorDebugModule::GetBaseAddress Method</span></span>

<span data-ttu-id="dcb7e-103">Pobiera adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="dcb7e-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcb7e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dcb7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcb7e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="dcb7e-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="dcb7e-106">określoną A `CORDB_ADDRESS` określający adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="dcb7e-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcb7e-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dcb7e-107">Remarks</span></span>  

 <span data-ttu-id="dcb7e-108">Jeśli moduł jest obrazem natywnym (czyli jeśli moduł został wyprodukowany przez generator obrazu natywnego, NGen.exe), jego adres podstawowy będzie równy zero.</span><span class="sxs-lookup"><span data-stu-id="dcb7e-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb7e-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dcb7e-109">Requirements</span></span>  

 <span data-ttu-id="dcb7e-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcb7e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcb7e-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="dcb7e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcb7e-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="dcb7e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcb7e-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcb7e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb7e-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dcb7e-114">See also</span></span>
