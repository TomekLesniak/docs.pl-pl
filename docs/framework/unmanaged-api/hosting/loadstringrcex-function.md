---
title: LoadStringRCEx — Funkcja
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727539"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="1cba8-102">LoadStringRCEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1cba8-102">LoadStringRCEx Function</span></span>

<span data-ttu-id="1cba8-103">Tłumaczy wartość HRESULT na odpowiedni komunikat o błędzie dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="1cba8-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="1cba8-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1cba8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cba8-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1cba8-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cba8-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="1cba8-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="1cba8-107">podczas Identyfikator kultury.</span><span class="sxs-lookup"><span data-stu-id="1cba8-107">[in] A culture identifier.</span></span> <span data-ttu-id="1cba8-108">Przekaż `lcid` wartość 1, aby użyć domyślnej kultury.</span><span class="sxs-lookup"><span data-stu-id="1cba8-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="1cba8-109">podczas WYNIK HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1cba8-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="1cba8-110">określoną Bufor, który zawiera komunikat o błędzie po pomyślnym zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="1cba8-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="1cba8-111">podczas Rozmiar buforu komunikatów o błędach.</span><span class="sxs-lookup"><span data-stu-id="1cba8-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="1cba8-112">podczas Ignoruj.</span><span class="sxs-lookup"><span data-stu-id="1cba8-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="1cba8-113">określoną Wskaźnik do długości komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="1cba8-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cba8-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1cba8-114">Return Value</span></span>  

 <span data-ttu-id="1cba8-115">Ta metoda zwraca standardowe kody błędów COM, jak zdefiniowano w WinError. h, oprócz następujących wartości.</span><span class="sxs-lookup"><span data-stu-id="1cba8-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1cba8-116">Kod powrotu</span><span class="sxs-lookup"><span data-stu-id="1cba8-116">Return code</span></span>|<span data-ttu-id="1cba8-117">Opis</span><span class="sxs-lookup"><span data-stu-id="1cba8-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1cba8-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cba8-118">S_OK</span></span>|<span data-ttu-id="1cba8-119">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="1cba8-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="1cba8-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1cba8-120">E_INVALIDARG</span></span>|<span data-ttu-id="1cba8-121">`szBuffer` ma wartość null lub `iMax` jest równa zero (0).</span><span class="sxs-lookup"><span data-stu-id="1cba8-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cba8-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1cba8-122">Remarks</span></span>  

 <span data-ttu-id="1cba8-123">Jeśli metoda nie zakończy się pomyślnie, `szBuffer` zawiera pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="1cba8-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cba8-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1cba8-124">Requirements</span></span>  

 <span data-ttu-id="1cba8-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cba8-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cba8-126">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1cba8-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cba8-127">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cba8-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cba8-128">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cba8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cba8-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1cba8-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1cba8-130">LoadStringRC — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1cba8-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="1cba8-131">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="1cba8-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
