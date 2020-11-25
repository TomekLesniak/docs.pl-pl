---
title: ICLRDataTarget::GetMachineType — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
ms.openlocfilehash: 00601e0bc722c0dc5e972324eddc0ab073d04586
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703541"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="4e218-102">ICLRDataTarget::GetMachineType — Metoda</span><span class="sxs-lookup"><span data-stu-id="4e218-102">ICLRDataTarget::GetMachineType Method</span></span>

<span data-ttu-id="4e218-103">Pobiera identyfikator rodzaju instrukcji, która jest używana przez proces docelowy.</span><span class="sxs-lookup"><span data-stu-id="4e218-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e218-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4e218-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e218-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4e218-105">Parameters</span></span>  

 `machineType`  
 <span data-ttu-id="4e218-106">określoną Wskaźnik do wartości, która wskazuje zestaw instrukcji używany przez proces docelowy.</span><span class="sxs-lookup"><span data-stu-id="4e218-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="4e218-107">Zwracana `machineType` jest jedna ze stałych IMAGE_FILE_MACHINE, które są zdefiniowane w pliku nagłówkowym Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="4e218-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e218-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4e218-108">Requirements</span></span>  

 <span data-ttu-id="4e218-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e218-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e218-110">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="4e218-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4e218-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4e218-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e218-112">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e218-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e218-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4e218-113">See also</span></span>

- [<span data-ttu-id="4e218-114">ICLRDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4e218-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
