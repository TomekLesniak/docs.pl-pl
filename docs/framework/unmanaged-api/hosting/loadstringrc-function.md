---
title: LoadStringRC — Funkcja
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727552"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="3238f-102">LoadStringRC — Funkcja</span><span class="sxs-lookup"><span data-stu-id="3238f-102">LoadStringRC Function</span></span>

<span data-ttu-id="3238f-103">Tłumaczy wartość HRESULT na komunikat o błędzie przy użyciu domyślnej kultury bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="3238f-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="3238f-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3238f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3238f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3238f-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3238f-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="3238f-106">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="3238f-107">podczas WYNIK HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3238f-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="3238f-108">określoną Bufor, który zawiera komunikat o błędzie po pomyślnym zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="3238f-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="3238f-109">podczas Rozmiar buforu komunikatów o błędach.</span><span class="sxs-lookup"><span data-stu-id="3238f-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="3238f-110">podczas Ignoruj.</span><span class="sxs-lookup"><span data-stu-id="3238f-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3238f-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3238f-111">Return Value</span></span>  

 <span data-ttu-id="3238f-112">Ta metoda zwraca kody błędów standardowego Component Object Model (COM), jak zdefiniowano w WinError. h, oprócz następujących wartości.</span><span class="sxs-lookup"><span data-stu-id="3238f-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3238f-113">Kod powrotu</span><span class="sxs-lookup"><span data-stu-id="3238f-113">Return code</span></span>|<span data-ttu-id="3238f-114">Opis</span><span class="sxs-lookup"><span data-stu-id="3238f-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3238f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3238f-115">S_OK</span></span>|<span data-ttu-id="3238f-116">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3238f-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="3238f-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3238f-117">E_INVALIDARG</span></span>|<span data-ttu-id="3238f-118">`szBuffer` ma wartość null lub `iMax` jest równa zero (0).</span><span class="sxs-lookup"><span data-stu-id="3238f-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3238f-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3238f-119">Remarks</span></span>  

 <span data-ttu-id="3238f-120">Jeśli metoda nie zakończy się pomyślnie, `szBuffer` zawiera pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="3238f-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3238f-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3238f-121">Requirements</span></span>  

 <span data-ttu-id="3238f-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3238f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3238f-123">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3238f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3238f-124">**Biblioteka:** MSCorEE.dll i Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="3238f-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="3238f-125">Użyj MSCorEE.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3238f-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3238f-126">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3238f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3238f-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3238f-127">See also</span></span>

- [<span data-ttu-id="3238f-128">LoadStringRCEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="3238f-128">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="3238f-129">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="3238f-129">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
