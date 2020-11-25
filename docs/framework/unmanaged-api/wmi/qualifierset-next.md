---
title: Funkcja QualifierSet_Next (niezarządzana dokumentacja interfejsu API)
description: Funkcja QualifierSet_Next pobiera następny kwalifikator w wyliczeniu.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721130"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="0ae5f-103">Funkcja QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="0ae5f-103">QualifierSet_Next function</span></span>

<span data-ttu-id="0ae5f-104">Pobiera następny kwalifikator w wyliczeniu, który rozpoczął wywoływanie funkcji [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0ae5f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0ae5f-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="0ae5f-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0ae5f-106">Parameters</span></span>

<span data-ttu-id="0ae5f-107">`vFunc` podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="0ae5f-108">`ptr` podczas Wskaźnik do wystąpienia [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="0ae5f-109">`lFlags` podczas Rezerwacj.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="0ae5f-110">Ten parametr musi być równy 0.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-110">This parameter must be 0.</span></span>

<span data-ttu-id="0ae5f-111">`pstrName` określoną Nazwa kwalifikatora.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="0ae5f-112">Jeśli `null` , ten parametr jest ignorowany; w przeciwnym razie `pstrName` nie powinien wskazywać prawidłowego `BSTR` lub wycieku pamięci.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="0ae5f-113">Jeśli wartość nie jest równa null, funkcja zawsze przydziela nowe, `BSTR` gdy zwraca `WBEM_S_NO_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="0ae5f-114">`pVal` określoną Po pomyślnym wykonaniu tej operacji wartość kwalifikatora.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="0ae5f-115">Jeśli funkcja się nie powiedzie, `VARIANT` wskazywane przez `pVal` nie jest modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="0ae5f-116">Jeśli ten parametr ma wartość `null` , parametr jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="0ae5f-117">`plFlavor` określoną Wskaźnik do LONG, który odbiera wersję kwalifikatora.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="0ae5f-118">Jeśli informacje o wersji nie są potrzebne, ten parametr może być `null` .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="0ae5f-119">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0ae5f-119">Return value</span></span>

<span data-ttu-id="0ae5f-120">Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="0ae5f-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0ae5f-121">Stała</span><span class="sxs-lookup"><span data-stu-id="0ae5f-121">Constant</span></span>  |<span data-ttu-id="0ae5f-122">Wartość</span><span class="sxs-lookup"><span data-stu-id="0ae5f-122">Value</span></span>  |<span data-ttu-id="0ae5f-123">Opis</span><span class="sxs-lookup"><span data-stu-id="0ae5f-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0ae5f-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0ae5f-124">0x80041008</span></span> | <span data-ttu-id="0ae5f-125">Parametr jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="0ae5f-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0ae5f-126">0x8004101d</span></span> | <span data-ttu-id="0ae5f-127">Obiekt wywołujący nie wywołał [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0ae5f-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0ae5f-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0ae5f-128">0x80041006</span></span> | <span data-ttu-id="0ae5f-129">Za mało dostępnej pamięci, aby rozpocząć nowe Wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="0ae5f-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="0ae5f-130">0x40005</span></span> | <span data-ttu-id="0ae5f-131">W wyliczeniu nie ma więcej kwalifikatorów.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0ae5f-132">0</span><span class="sxs-lookup"><span data-stu-id="0ae5f-132">0</span></span> | <span data-ttu-id="0ae5f-133">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0ae5f-134">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ae5f-134">Remarks</span></span>

<span data-ttu-id="0ae5f-135">Ta funkcja zawija wywołanie do metody [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="0ae5f-136">Wywołaj `QualifierSet_Next` funkcję wielokrotnie, aby wyliczyć wszystkie kwalifikatory do momentu zwrócenia funkcji `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="0ae5f-137">Aby przerwać wyliczanie, wywołaj funkcję [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0ae5f-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="0ae5f-138">Kolejność kwalifikatorów zwróconych podczas wyliczania jest niezdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="0ae5f-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="0ae5f-139">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0ae5f-139">Requirements</span></span>  

 <span data-ttu-id="0ae5f-140">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae5f-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae5f-141">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0ae5f-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0ae5f-142">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae5f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae5f-143">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0ae5f-143">See also</span></span>

- [<span data-ttu-id="0ae5f-144">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="0ae5f-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
