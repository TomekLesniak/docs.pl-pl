---
title: Funkcja QualifierSet_EndEnumeration (niezarządzana dokumentacja interfejsu API)
description: Funkcja QualifierSet_EndEnumeration przerywa Wyliczenie.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2739003fc9c1f93d379e4a59338cbef7a1a0f135
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726746"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="b1001-103">Funkcja QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="b1001-103">QualifierSet_EndEnumeration function</span></span>

<span data-ttu-id="b1001-104">Kończy Wyliczenie rozpoczęte z wywołaniem funkcji [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b1001-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b1001-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b1001-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="b1001-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b1001-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b1001-107">podczas Ten parametr jest nieużywany.</span><span class="sxs-lookup"><span data-stu-id="b1001-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="b1001-108">`ptr` podczas Wskaźnik do wystąpienia [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="b1001-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="b1001-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b1001-109">Return value</span></span>

<span data-ttu-id="b1001-110">Następująca wartość zwrócona przez tę funkcję jest zdefiniowana w pliku nagłówkowym *WbemCli. h* lub można ją zdefiniować jako stałą w kodzie:</span><span class="sxs-lookup"><span data-stu-id="b1001-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="b1001-111">Stała</span><span class="sxs-lookup"><span data-stu-id="b1001-111">Constant</span></span>  |<span data-ttu-id="b1001-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="b1001-112">Value</span></span>  |<span data-ttu-id="b1001-113">Opis</span><span class="sxs-lookup"><span data-stu-id="b1001-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b1001-114">0</span><span class="sxs-lookup"><span data-stu-id="b1001-114">0</span></span> | <span data-ttu-id="b1001-115">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b1001-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b1001-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b1001-116">Remarks</span></span>

<span data-ttu-id="b1001-117">Ta funkcja otacza wywołanie metody [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="b1001-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="b1001-118">To wywołanie jest zalecane, ale nie jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="b1001-118">This call is recommended, but not required.</span></span> <span data-ttu-id="b1001-119">Natychmiast zwalnia zasoby skojarzone z wyliczeniem.</span><span class="sxs-lookup"><span data-stu-id="b1001-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1001-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b1001-120">Requirements</span></span>  

<span data-ttu-id="b1001-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1001-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="b1001-122">**Nagłówek:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b1001-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="b1001-123">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b1001-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1001-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b1001-124">See also</span></span>

- [<span data-ttu-id="b1001-125">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="b1001-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
