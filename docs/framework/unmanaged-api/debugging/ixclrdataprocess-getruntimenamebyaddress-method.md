---
title: 'IXCLRDataProcess:: GetRuntimeNameByAddress, Metoda'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270492"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a><span data-ttu-id="edbc2-102">IXCLRDataProcess:: GetRuntimeNameByAddress, Metoda</span><span class="sxs-lookup"><span data-stu-id="edbc2-102">IXCLRDataProcess::GetRuntimeNameByAddress Method</span></span>

<span data-ttu-id="edbc2-103">Pobiera nazwę dla danego adresu.</span><span class="sxs-lookup"><span data-stu-id="edbc2-103">Gets a name for the given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="edbc2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="edbc2-104">Syntax</span></span>

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a><span data-ttu-id="edbc2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="edbc2-105">Parameters</span></span>

`address`\
<span data-ttu-id="edbc2-106">podczas `CLRDATA_ADDRESS` Wartość, która reprezentuje adres kodu.</span><span class="sxs-lookup"><span data-stu-id="edbc2-106">[in] A `CLRDATA_ADDRESS` value that represents a code address.</span></span>

`flags`\
<span data-ttu-id="edbc2-107">podczas Ustaw wartość "0".</span><span class="sxs-lookup"><span data-stu-id="edbc2-107">[in] Set to '0'.</span></span>

`bufLen`\
<span data-ttu-id="edbc2-108">podczas Długość buforu.</span><span class="sxs-lookup"><span data-stu-id="edbc2-108">[in] The length of the buffer.</span></span>

`namLen`\
<span data-ttu-id="edbc2-109">określoną Wskaźnik do liczby zwracanych znaków.</span><span class="sxs-lookup"><span data-stu-id="edbc2-109">[out] A pointer to the number of characters returned.</span></span>

`namBuf`\
<span data-ttu-id="edbc2-110">[out, size_is ( `bufLen` )] wejściowy bufor o długości `bufLen` , który przechowuje nazwę środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="edbc2-110">[out, size_is(`bufLen`)] The input buffer of length `bufLen` that stores the runtime name.</span></span>

`displacement`\
<span data-ttu-id="edbc2-111">określoną `CLRDATA_ADDRESS` Wskaźnik do przesunięcia kodu zwróconego symbolu.</span><span class="sxs-lookup"><span data-stu-id="edbc2-111">[out] A `CLRDATA_ADDRESS` pointer to the code offset of the returned symbol.</span></span>

## <a name="remarks"></a><span data-ttu-id="edbc2-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="edbc2-112">Remarks</span></span>

<span data-ttu-id="edbc2-113">Podana metoda jest częścią `IXCLRDataProcess` interfejsu i odpowiada szesnastemu gnieździe tabeli metody wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="edbc2-113">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 16th slot of the virtual-method table.</span></span>

> [!NOTE]
> <span data-ttu-id="edbc2-114">Jeśli bufor nie jest wystarczająco duży dla nazwy, ta metoda zwraca `S_FALSE` i ustawia `nameLen` wymaganą długość buforu.</span><span class="sxs-lookup"><span data-stu-id="edbc2-114">If the buffer is not large enough for the name, this method returns `S_FALSE` and sets `nameLen` to the required buffer length.</span></span>

## <a name="requirements"></a><span data-ttu-id="edbc2-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="edbc2-115">Requirements</span></span>

<span data-ttu-id="edbc2-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="edbc2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="edbc2-117">**Nagłówek:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="edbc2-117">**Header:** None\</span></span>
<span data-ttu-id="edbc2-118">**Biblioteka:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="edbc2-118">**Library:** None\</span></span>
<span data-ttu-id="edbc2-119">**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="edbc2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="edbc2-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="edbc2-120">See also</span></span>

- [<span data-ttu-id="edbc2-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="edbc2-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="edbc2-122">IXCLRDataProcess, interfejs</span><span class="sxs-lookup"><span data-stu-id="edbc2-122">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
