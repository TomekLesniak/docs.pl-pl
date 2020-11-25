---
title: GetHistoryFileDirectory — Funkcja
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724441"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="66274-102">GetHistoryFileDirectory — Funkcja</span><span class="sxs-lookup"><span data-stu-id="66274-102">GetHistoryFileDirectory Function</span></span>

<span data-ttu-id="66274-103">Pobiera ścieżkę katalogu historii aplikacji.</span><span class="sxs-lookup"><span data-stu-id="66274-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66274-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="66274-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66274-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="66274-105">Parameters</span></span>  

 `wzDir`  
 <span data-ttu-id="66274-106">określoną Bufor służący do przechowywania ścieżki do katalogu historii aplikacji.</span><span class="sxs-lookup"><span data-stu-id="66274-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="66274-107">[in. out] Długość buforu.</span><span class="sxs-lookup"><span data-stu-id="66274-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66274-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="66274-108">Return Value</span></span>  

 <span data-ttu-id="66274-109">Ta metoda zwraca kody błędów standardowego modelu COM, jak zdefiniowano w pliku WinError. h oprócz następujących wartości.</span><span class="sxs-lookup"><span data-stu-id="66274-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="66274-110">Kod powrotu</span><span class="sxs-lookup"><span data-stu-id="66274-110">Return code</span></span>|<span data-ttu-id="66274-111">Opis</span><span class="sxs-lookup"><span data-stu-id="66274-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="66274-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="66274-112">S_OK</span></span>|<span data-ttu-id="66274-113">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="66274-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="66274-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="66274-114">E_INVALIDARG</span></span>|<span data-ttu-id="66274-115">`wzDir` lub `pdwSize` ma wartość null lub ciąg wersji jest niepoprawny.</span><span class="sxs-lookup"><span data-stu-id="66274-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66274-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="66274-116">Remarks</span></span>  

 <span data-ttu-id="66274-117">Po pomyślnym zakończeniu `pdwSize` argument ma ustawioną długość ciągu ścieżki.</span><span class="sxs-lookup"><span data-stu-id="66274-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66274-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="66274-118">Requirements</span></span>  

 <span data-ttu-id="66274-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66274-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66274-120">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="66274-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="66274-121">**Biblioteka:** Fusion.dll i Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="66274-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="66274-122">Użyj Fusion.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66274-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="66274-123">**.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66274-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66274-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="66274-124">See also</span></span>

- [<span data-ttu-id="66274-125">CreateHistoryReader — Funkcja</span><span class="sxs-lookup"><span data-stu-id="66274-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="66274-126">NukeDownloadedCache — Funkcja</span><span class="sxs-lookup"><span data-stu-id="66274-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="66274-127">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="66274-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
