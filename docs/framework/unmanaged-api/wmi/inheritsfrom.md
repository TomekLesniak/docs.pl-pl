---
title: InheritsFrom — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja InheritsFrom określa, czy Klasa lub wystąpienie pochodzi od określonej klasy nadrzędnej.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3cfe3388dc808335e6d3daaf7ec949108e95f52e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726798"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="59240-103">InheritsFrom, funkcja</span><span class="sxs-lookup"><span data-stu-id="59240-103">InheritsFrom function</span></span>

<span data-ttu-id="59240-104">Określa, czy bieżąca Klasa lub wystąpienie pochodzi z określonej klasy nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="59240-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="59240-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="59240-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="59240-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="59240-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="59240-107">podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="59240-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="59240-108">podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="59240-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="59240-109">podczas Nazwa klasy.</span><span class="sxs-lookup"><span data-stu-id="59240-109">[in] The name of the class.</span></span> <span data-ttu-id="59240-110">`wszAncestor` musi wskazywać prawidłowy `LPCWSTR` .</span><span class="sxs-lookup"><span data-stu-id="59240-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="59240-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="59240-111">Return value</span></span>

<span data-ttu-id="59240-112">Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="59240-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="59240-113">Stała</span><span class="sxs-lookup"><span data-stu-id="59240-113">Constant</span></span>  |<span data-ttu-id="59240-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="59240-114">Value</span></span>  |<span data-ttu-id="59240-115">Opis</span><span class="sxs-lookup"><span data-stu-id="59240-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="59240-116">0</span><span class="sxs-lookup"><span data-stu-id="59240-116">0</span></span> | <span data-ttu-id="59240-117">Bieżący obiekt dziedziczy z `wszAncestor` .</span><span class="sxs-lookup"><span data-stu-id="59240-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="59240-118">1</span><span class="sxs-lookup"><span data-stu-id="59240-118">1</span></span> | <span data-ttu-id="59240-119">Bieżący obiekt nie dziedziczy po elemencie `wszAncestor` .</span><span class="sxs-lookup"><span data-stu-id="59240-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="59240-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="59240-120">0x80041008</span></span> | <span data-ttu-id="59240-121">`wszAncestor` to `null`.</span><span class="sxs-lookup"><span data-stu-id="59240-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="59240-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="59240-122">Remarks</span></span>

<span data-ttu-id="59240-123">Ta funkcja otacza wywołanie metody [IWbemClassObject:: InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="59240-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="59240-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="59240-124">Requirements</span></span>  

 <span data-ttu-id="59240-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59240-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59240-126">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="59240-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="59240-127">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59240-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59240-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="59240-128">See also</span></span>

- [<span data-ttu-id="59240-129">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="59240-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
