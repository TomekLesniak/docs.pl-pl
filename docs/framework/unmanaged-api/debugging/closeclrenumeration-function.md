---
title: CloseCLREnumeration — Funkcja
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673916"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="49995-102">CloseCLREnumeration — Funkcja</span><span class="sxs-lookup"><span data-stu-id="49995-102">CloseCLREnumeration Function</span></span>

<span data-ttu-id="49995-103">Zamyka wszystkie prawidłowe zdarzenia uruchamiania środowiska uruchomieniowego języka wspólnego (CLR), które znajdują się w tablicy dojść zwracanych przez [funkcję EnumerateCLRs —](enumerateclrs-function.md), i zwalnia pamięć dla tablic uchwytów i ścieżek ciągów.</span><span class="sxs-lookup"><span data-stu-id="49995-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49995-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="49995-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49995-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="49995-105">Parameters</span></span>  

 `pHandleArray`  
 <span data-ttu-id="49995-106">podczas Wskaźnik do tablicy dojść do zdarzeń zwróconych z [funkcji EnumerateCLRs —](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="49995-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="49995-107">podczas Wskaźnik do tablicy ścieżek ciągów CLR zwracanych z [funkcji EnumerateCLRs —](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="49995-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="49995-108">podczas Wartość DWORD, która zawiera rozmiar (długość) `pHandleArray` lub `pStringArray` (jest taka sama).</span><span class="sxs-lookup"><span data-stu-id="49995-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49995-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="49995-109">Return Value</span></span>  

 <span data-ttu-id="49995-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="49995-110">S_OK</span></span>  
 <span data-ttu-id="49995-111">Uchwyty otwarte przez [funkcję EnumerateCLRs —](enumerateclrs-function.md) są zamknięte, a pamięć przydzieloną dla dojścia i tablic ciągów jest zwalniana.</span><span class="sxs-lookup"><span data-stu-id="49995-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="49995-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="49995-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="49995-113">Długość `pHandleArray` nie pasuje do długości, która została przeniesiona `dwArrayLength` .</span><span class="sxs-lookup"><span data-stu-id="49995-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="49995-114">E_FAIL (lub inne kody powrotne E_)</span><span class="sxs-lookup"><span data-stu-id="49995-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="49995-115">Funkcja nie może zwolnić pamięci dla `pHandleArray` i `pStringArray` .</span><span class="sxs-lookup"><span data-stu-id="49995-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49995-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="49995-116">Requirements</span></span>  

 <span data-ttu-id="49995-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49995-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49995-118">**Nagłówek:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="49995-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="49995-119">**Biblioteka:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="49995-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="49995-120">**.NET Framework wersje:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="49995-120">**.NET Framework Versions:** 3.5 SP1</span></span>
