---
title: ICorDebugDataTarget::ReadVirtual — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 8fb0cfc72867653eaff65f3183dacf9191604290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679731"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="83c81-102">ICorDebugDataTarget::ReadVirtual — Metoda</span><span class="sxs-lookup"><span data-stu-id="83c81-102">ICorDebugDataTarget::ReadVirtual Method</span></span>

<span data-ttu-id="83c81-103">Pobiera blok ciągłej pamięci zaczynający się od określonego adresu i zwraca go w dostarczonym buforze.</span><span class="sxs-lookup"><span data-stu-id="83c81-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c81-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="83c81-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c81-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="83c81-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="83c81-106">podczas Adres początkowy żądanej pamięci.</span><span class="sxs-lookup"><span data-stu-id="83c81-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="83c81-107">określoną Bufor, w którym będzie przechowywana pamięć.</span><span class="sxs-lookup"><span data-stu-id="83c81-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="83c81-108">podczas Liczba bajtów pobieranych z adresu docelowego.</span><span class="sxs-lookup"><span data-stu-id="83c81-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="83c81-109">określoną Liczba bajtów faktycznie odczytywanych z adresu docelowego.</span><span class="sxs-lookup"><span data-stu-id="83c81-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="83c81-110">Może to być mniejsze niż `bytesRequested` .</span><span class="sxs-lookup"><span data-stu-id="83c81-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83c81-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="83c81-111">Remarks</span></span>  

 <span data-ttu-id="83c81-112">W przypadku odczytywania pierwszego bajtu (na określonym adresie początkowym) wywołanie powinno zwrócić sukces (w celu zapewnienia obsługi wydajnego odczytu struktur danych z unikatową długością, na przykład w przypadku ciągów zakończonych znakiem null).</span><span class="sxs-lookup"><span data-stu-id="83c81-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c81-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="83c81-113">Requirements</span></span>  

 <span data-ttu-id="83c81-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c81-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c81-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="83c81-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83c81-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="83c81-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83c81-117">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c81-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c81-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83c81-118">See also</span></span>

- [<span data-ttu-id="83c81-119">ICorDebugDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83c81-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="83c81-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="83c81-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="83c81-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="83c81-121">Debugging</span></span>](index.md)
