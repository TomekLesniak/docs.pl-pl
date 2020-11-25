---
title: ICorDebugClass2::SetJMCStatus — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717828"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="a0d45-102">ICorDebugClass2::SetJMCStatus — Metoda</span><span class="sxs-lookup"><span data-stu-id="a0d45-102">ICorDebugClass2::SetJMCStatus Method</span></span>

<span data-ttu-id="a0d45-103">Dla każdej metody klasy ustawia wartość wskazującą, czy metoda jest kodem zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a0d45-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d45-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a0d45-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0d45-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a0d45-105">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="a0d45-106">podczas Ustaw na, aby `true` wskazać, że metoda jest kodem zdefiniowanym przez użytkownika; w przeciwnym razie ustaw wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="a0d45-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0d45-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a0d45-107">Remarks</span></span>  

 <span data-ttu-id="a0d45-108">JMC (Just-My-Code) stepper pominie kod niezdefiniowany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a0d45-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="a0d45-109">Kod zdefiniowany przez użytkownika musi być podzbiorem kodu możliwością debugowania.</span><span class="sxs-lookup"><span data-stu-id="a0d45-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="a0d45-110">`SetJMCStatus` Zwraca wartość HRESULT S_FALSE, jeśli nie można ustawić wartości dla żadnej metody, nawet jeśli pomyślnie ustawi wartość dla wszystkich innych metod.</span><span class="sxs-lookup"><span data-stu-id="a0d45-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0d45-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a0d45-111">Requirements</span></span>  

 <span data-ttu-id="a0d45-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0d45-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0d45-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a0d45-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0d45-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a0d45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0d45-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
