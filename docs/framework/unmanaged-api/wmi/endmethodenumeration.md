---
title: EndMethodEnumeration — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja EndMethodEnumeration kończy sekwencję wyliczenia metod.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 82f50530967699427d8a00b1c9f518b639273626
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708065"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="9c733-103">EndMethodEnumeration, funkcja</span><span class="sxs-lookup"><span data-stu-id="9c733-103">EndMethodEnumeration function</span></span>

<span data-ttu-id="9c733-104">Kończy sekwencję wyliczenia rozpoczętą od wywołania [funkcji BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9c733-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9c733-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9c733-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="9c733-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="9c733-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9c733-107">podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="9c733-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9c733-108">podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="9c733-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="9c733-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9c733-109">Return value</span></span>

<span data-ttu-id="9c733-110">Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="9c733-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9c733-111">Stała</span><span class="sxs-lookup"><span data-stu-id="9c733-111">Constant</span></span>  |<span data-ttu-id="9c733-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="9c733-112">Value</span></span>  |<span data-ttu-id="9c733-113">Opis</span><span class="sxs-lookup"><span data-stu-id="9c733-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="9c733-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="9c733-114">0x8004101d</span></span> | <span data-ttu-id="9c733-115">Wystąpił błąd wewnętrzny.</span><span class="sxs-lookup"><span data-stu-id="9c733-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9c733-116">0</span><span class="sxs-lookup"><span data-stu-id="9c733-116">0</span></span> | <span data-ttu-id="9c733-117">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="9c733-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9c733-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9c733-118">Remarks</span></span>

<span data-ttu-id="9c733-119">Ta funkcja otacza wywołanie metody [IWbemClassObject:: EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="9c733-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="9c733-120">Obiekt wywołujący rozpoczyna sekwencję wyliczenia za pomocą [funkcji BeginMethodEnumeration](beginmethodenumeration.md), a następnie wywołuje [funkcję NextMethod](nextmethod.md )do momentu, gdy metoda zwróci metodę `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="9c733-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="9c733-121">Obiekt wywołujący opcjonalnie kończy sekwencję przez wywołanie metody `EndMethodEnumeration` .</span><span class="sxs-lookup"><span data-stu-id="9c733-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="9c733-122">Obiekt wywołujący może zakończyć Wyliczenie wczesne przez wywołanie `EndMethodEnumeration` w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="9c733-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c733-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9c733-123">Requirements</span></span>  

 <span data-ttu-id="9c733-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c733-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c733-125">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="9c733-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9c733-126">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9c733-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c733-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9c733-127">See also</span></span>

- [<span data-ttu-id="9c733-128">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="9c733-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
