---
title: Clone — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja klonowania zwraca nowy obiekt, który jest kompletnym klonem bieżącego.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: aecbf750b42626629dcb5aef369978a2e2bd002a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708117"
---
# <a name="clone-function"></a><span data-ttu-id="cc9e2-103">Clone, funkcja</span><span class="sxs-lookup"><span data-stu-id="cc9e2-103">Clone function</span></span>

<span data-ttu-id="cc9e2-104">Zwraca nowy obiekt, który jest kompletnym klonem bieżącego obiektu.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="cc9e2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="cc9e2-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="cc9e2-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="cc9e2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="cc9e2-107">podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="cc9e2-108">podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="cc9e2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="cc9e2-109">określoną Nowy obiekt, który jest kompletną Lone `ptr` .</span><span class="sxs-lookup"><span data-stu-id="cc9e2-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="cc9e2-110">Ten argument nie może mieć `null` wartości, Jeśli odbierze kopię bieżącego obiektu.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="cc9e2-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cc9e2-111">Return value</span></span>

<span data-ttu-id="cc9e2-112">Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="cc9e2-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cc9e2-113">Stała</span><span class="sxs-lookup"><span data-stu-id="cc9e2-113">Constant</span></span>  |<span data-ttu-id="cc9e2-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="cc9e2-114">Value</span></span>  |<span data-ttu-id="cc9e2-115">Opis</span><span class="sxs-lookup"><span data-stu-id="cc9e2-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="cc9e2-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cc9e2-116">0x80041001</span></span> | <span data-ttu-id="cc9e2-117">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cc9e2-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cc9e2-118">0x80041008</span></span> | <span data-ttu-id="cc9e2-119">`null` został określony jako parametr i nie jest dozwolony w tym użyciu.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cc9e2-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cc9e2-120">0x80041006</span></span> | <span data-ttu-id="cc9e2-121">Za mało dostępnej pamięci, aby sklonować obiekt.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cc9e2-122">0</span><span class="sxs-lookup"><span data-stu-id="cc9e2-122">0</span></span> | <span data-ttu-id="cc9e2-123">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="cc9e2-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cc9e2-124">Remarks</span></span>

<span data-ttu-id="cc9e2-125">Ta funkcja otacza wywołanie metody [IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="cc9e2-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="cc9e2-126">Sklonowany obiekt jest obiektem COM, który ma liczbę odwołań 1.</span><span class="sxs-lookup"><span data-stu-id="cc9e2-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc9e2-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cc9e2-127">Requirements</span></span>  

 <span data-ttu-id="cc9e2-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc9e2-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc9e2-129">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="cc9e2-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cc9e2-130">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cc9e2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9e2-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cc9e2-131">See also</span></span>

- [<span data-ttu-id="cc9e2-132">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="cc9e2-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
