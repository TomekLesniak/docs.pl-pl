---
title: ICorDebugInternalFrame2::GetFrameAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 05a9ab58acb3bf5829fd231ae6d8bcc96ae06da6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724874"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="3739b-102">ICorDebugInternalFrame2::GetFrameAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="3739b-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>

<span data-ttu-id="3739b-103">Zwraca adres stosu ramki wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="3739b-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3739b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3739b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3739b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3739b-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="3739b-106">określoną Wskaźnik na `CORDB_ADDRESS` ramkę wewnętrzną.</span><span class="sxs-lookup"><span data-stu-id="3739b-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3739b-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3739b-107">Return Value</span></span>  

 <span data-ttu-id="3739b-108">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="3739b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3739b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3739b-109">HRESULT</span></span>|<span data-ttu-id="3739b-110">Opis</span><span class="sxs-lookup"><span data-stu-id="3739b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3739b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3739b-111">S_OK</span></span>|<span data-ttu-id="3739b-112">Adres ramki wewnętrznej został pomyślnie zwrócony.</span><span class="sxs-lookup"><span data-stu-id="3739b-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="3739b-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3739b-113">E_FAIL</span></span>|<span data-ttu-id="3739b-114">Nie można zwrócić adresu wewnętrznej ramki.</span><span class="sxs-lookup"><span data-stu-id="3739b-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="3739b-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3739b-115">E_INVALIDARG</span></span>|<span data-ttu-id="3739b-116">`pAddress` to `null`.</span><span class="sxs-lookup"><span data-stu-id="3739b-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3739b-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3739b-117">Remarks</span></span>  

 <span data-ttu-id="3739b-118">Wartość zwrócona w `pAddress` może służyć do określenia lokalizacji wewnętrznej ramki względem innych ramek na stosie.</span><span class="sxs-lookup"><span data-stu-id="3739b-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="3739b-119">Nawet na komputerach z procesorem IA-64, wewnętrzna ramka znajduje się tylko na stosie i nie istnieje odpowiedni wskaźnik do magazynu zapasowego.</span><span class="sxs-lookup"><span data-stu-id="3739b-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3739b-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3739b-120">Requirements</span></span>  

 <span data-ttu-id="3739b-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3739b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3739b-122">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3739b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3739b-123">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3739b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3739b-124">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3739b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3739b-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3739b-125">See also</span></span>

- [<span data-ttu-id="3739b-126">ICorDebugInternalFrame2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3739b-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="3739b-127">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="3739b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3739b-128">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="3739b-128">Debugging</span></span>](index.md)
