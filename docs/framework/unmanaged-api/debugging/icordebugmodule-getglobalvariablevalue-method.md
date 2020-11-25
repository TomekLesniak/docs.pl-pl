---
title: ICorDebugModule::GetGlobalVariableValue — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
ms.openlocfilehash: 94fe7deb10c23ea0bc824bb2244e8d1d87f831e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710040"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="51087-102">ICorDebugModule::GetGlobalVariableValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="51087-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>

<span data-ttu-id="51087-103">Pobiera wartość określonej zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="51087-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51087-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="51087-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51087-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="51087-105">Parameters</span></span>  

 `fieldDef`  
 <span data-ttu-id="51087-106">podczas `mdFieldDef` Token, który odwołuje się do metadanych opisujących zmienną globalną.</span><span class="sxs-lookup"><span data-stu-id="51087-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="51087-107">określoną Wskaźnik do adresu obiektu ICorDebugValue, który reprezentuje wartość określonej zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="51087-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51087-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="51087-108">Requirements</span></span>  

 <span data-ttu-id="51087-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51087-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51087-110">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="51087-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51087-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="51087-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51087-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51087-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
