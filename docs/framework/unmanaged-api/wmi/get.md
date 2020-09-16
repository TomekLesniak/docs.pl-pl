---
title: Get — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja Get pobiera określoną wartość właściwości.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 7cc0c285f79b2791863fce251e4683aa7b55341b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553691"
---
# <a name="get-function"></a><span data-ttu-id="96258-103">Get, funkcja</span><span class="sxs-lookup"><span data-stu-id="96258-103">Get function</span></span>

<span data-ttu-id="96258-104">Pobiera określoną wartość właściwości, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="96258-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="96258-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="96258-105">Syntax</span></span>

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="96258-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="96258-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="96258-107">podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="96258-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="96258-108">podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="96258-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="96258-109">podczas Nazwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="96258-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="96258-110">podczas Rezerwacj.</span><span class="sxs-lookup"><span data-stu-id="96258-110">[in] Reserved.</span></span> <span data-ttu-id="96258-111">Ten parametr musi być równy 0.</span><span class="sxs-lookup"><span data-stu-id="96258-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="96258-112">określoną Jeśli funkcja zwróci się pomyślnie, zawiera wartość `wszName` właściwości.</span><span class="sxs-lookup"><span data-stu-id="96258-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="96258-113">Do `pval` argumentu jest przypisany prawidłowy typ i wartość dla kwalifikatora.</span><span class="sxs-lookup"><span data-stu-id="96258-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="96258-114">określoną Jeśli funkcja zwróci się pomyślnie, zawiera [stałą typu CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) , która wskazuje typ właściwości.</span><span class="sxs-lookup"><span data-stu-id="96258-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="96258-115">Jego wartość może być również `null` .</span><span class="sxs-lookup"><span data-stu-id="96258-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="96258-116">określoną Jeśli funkcja zwróci się pomyślnie, otrzymuje informacje o pochodzeniu właściwości.</span><span class="sxs-lookup"><span data-stu-id="96258-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="96258-117">Jego wartością może być `null` lub jedna z następujących WBEM_FLAVOR_TYPE stałych zdefiniowanych w pliku nagłówkowym *WbemCli. h* :</span><span class="sxs-lookup"><span data-stu-id="96258-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="96258-118">Stała</span><span class="sxs-lookup"><span data-stu-id="96258-118">Constant</span></span>  |<span data-ttu-id="96258-119">Wartość</span><span class="sxs-lookup"><span data-stu-id="96258-119">Value</span></span>  |<span data-ttu-id="96258-120">Opis</span><span class="sxs-lookup"><span data-stu-id="96258-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="96258-121">0x40</span><span class="sxs-lookup"><span data-stu-id="96258-121">0x40</span></span> | <span data-ttu-id="96258-122">Właściwość jest standardową właściwością systemu.</span><span class="sxs-lookup"><span data-stu-id="96258-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="96258-123">0x20</span><span class="sxs-lookup"><span data-stu-id="96258-123">0x20</span></span> | <span data-ttu-id="96258-124">Dla klasy: właściwość jest dziedziczona z klasy nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="96258-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="96258-125">Dla wystąpienia: właściwość, podczas gdy dziedziczy z klasy nadrzędnej, nie została zmodyfikowana przez wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="96258-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="96258-126">0</span><span class="sxs-lookup"><span data-stu-id="96258-126">0</span></span> | <span data-ttu-id="96258-127">Dla klasy: właściwość należy do klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="96258-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="96258-128">Dla wystąpienia: właściwość jest modyfikowana przez wystąpienie; oznacza to, że została podana wartość lub kwalifikator został dodany lub zmodyfikowany.</span><span class="sxs-lookup"><span data-stu-id="96258-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="96258-129">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="96258-129">Return value</span></span>

<span data-ttu-id="96258-130">Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="96258-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="96258-131">Stała</span><span class="sxs-lookup"><span data-stu-id="96258-131">Constant</span></span>  |<span data-ttu-id="96258-132">Wartość</span><span class="sxs-lookup"><span data-stu-id="96258-132">Value</span></span>  |<span data-ttu-id="96258-133">Opis</span><span class="sxs-lookup"><span data-stu-id="96258-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="96258-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="96258-134">0x80041001</span></span> | <span data-ttu-id="96258-135">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="96258-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="96258-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="96258-136">0x80041008</span></span> | <span data-ttu-id="96258-137">Co najmniej jeden parametr jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="96258-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="96258-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="96258-138">0x80041002</span></span> | <span data-ttu-id="96258-139">Nie znaleziono określonej właściwości.</span><span class="sxs-lookup"><span data-stu-id="96258-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="96258-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="96258-140">0x80041006</span></span> | <span data-ttu-id="96258-141">Za mało dostępnej pamięci, aby ukończyć tę operację.</span><span class="sxs-lookup"><span data-stu-id="96258-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="96258-142">0</span><span class="sxs-lookup"><span data-stu-id="96258-142">0</span></span> | <span data-ttu-id="96258-143">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="96258-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="96258-144">Uwagi</span><span class="sxs-lookup"><span data-stu-id="96258-144">Remarks</span></span>

<span data-ttu-id="96258-145">Ta funkcja otacza wywołanie metody [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .</span><span class="sxs-lookup"><span data-stu-id="96258-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="96258-146">`Get`Funkcja może również zwracać właściwości systemu.</span><span class="sxs-lookup"><span data-stu-id="96258-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="96258-147">Do `pVal` argumentu jest przypisany prawidłowy typ i wartość dla kwalifikatora oraz funkcja com [VariantInit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)</span><span class="sxs-lookup"><span data-stu-id="96258-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="96258-148">Wymagania</span><span class="sxs-lookup"><span data-stu-id="96258-148">Requirements</span></span>

 <span data-ttu-id="96258-149">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96258-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="96258-150">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="96258-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="96258-151">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="96258-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="96258-152">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="96258-152">See also</span></span>

- [<span data-ttu-id="96258-153">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="96258-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
