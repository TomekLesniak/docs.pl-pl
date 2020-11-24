---
title: GetQualifierSet — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja GetQualifierSet pobiera kwalifikator zestawu dla klasy lub wystąpienia.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f9bb882a0f62499167b79bf3e6691d05e394720f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671346"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="e7abd-103">GetQualifierSet, funkcja</span><span class="sxs-lookup"><span data-stu-id="e7abd-103">GetQualifierSet function</span></span>

<span data-ttu-id="e7abd-104">Pobiera kwalifikator zestawu dla wystąpienia klasy lub definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="e7abd-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e7abd-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e7abd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="e7abd-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="e7abd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e7abd-107">podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="e7abd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e7abd-108">podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="e7abd-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="e7abd-109">określoną Odbiera wskaźnik interfejsu, który umożliwia dostęp do kwalifikatorów obiektu klasy.</span><span class="sxs-lookup"><span data-stu-id="e7abd-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="e7abd-110">`ppQualSet` nie może być `null` .</span><span class="sxs-lookup"><span data-stu-id="e7abd-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="e7abd-111">Jeśli wystąpi błąd, nowy obiekt nie jest zwracany, a wskaźnik nie zostanie zmodyfikowany.</span><span class="sxs-lookup"><span data-stu-id="e7abd-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="e7abd-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e7abd-112">Return value</span></span>

<span data-ttu-id="e7abd-113">Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="e7abd-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e7abd-114">Stała</span><span class="sxs-lookup"><span data-stu-id="e7abd-114">Constant</span></span>  |<span data-ttu-id="e7abd-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="e7abd-115">Value</span></span>  |<span data-ttu-id="e7abd-116">Opis</span><span class="sxs-lookup"><span data-stu-id="e7abd-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e7abd-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e7abd-117">0x80041001</span></span> | <span data-ttu-id="e7abd-118">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="e7abd-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e7abd-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e7abd-119">0x80041002</span></span> | <span data-ttu-id="e7abd-120">Określona metoda nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="e7abd-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e7abd-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e7abd-121">0x80041006</span></span> | <span data-ttu-id="e7abd-122">Za mało dostępnej pamięci, aby ukończyć tę operację.</span><span class="sxs-lookup"><span data-stu-id="e7abd-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e7abd-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e7abd-123">0x80041008</span></span> | <span data-ttu-id="e7abd-124">Parametr ma wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="e7abd-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e7abd-125">0</span><span class="sxs-lookup"><span data-stu-id="e7abd-125">0</span></span> | <span data-ttu-id="e7abd-126">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e7abd-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e7abd-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e7abd-127">Remarks</span></span>

<span data-ttu-id="e7abd-128">Ta funkcja otacza wywołanie metody [IWbemClassObject:: GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="e7abd-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="e7abd-129">[Wskaźnik IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) umożliwia obiektowi wywołującemu Dodawanie, edytowanie lub usuwanie tych kwalifikatorów.</span><span class="sxs-lookup"><span data-stu-id="e7abd-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="e7abd-130">Takie dodane, zmodyfikowane lub usunięte kwalifikatory mają zastosowanie do całego wystąpienia lub definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="e7abd-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="e7abd-131">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e7abd-131">Requirements</span></span>  

<span data-ttu-id="e7abd-132">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7abd-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7abd-133">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e7abd-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e7abd-134">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e7abd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7abd-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e7abd-135">See also</span></span>

- [<span data-ttu-id="e7abd-136">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="e7abd-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
