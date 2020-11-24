---
title: EnumerateCLRs — Funkcja
ms.date: 03/30/2017
api_name:
- EnumerateCLRs
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type:
- apiref
ms.openlocfilehash: 8fe0df3ee08f9915ed43990b6f9686e25b183a0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676104"
---
# <a name="enumerateclrs-function"></a><span data-ttu-id="f34f6-102">EnumerateCLRs — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f34f6-102">EnumerateCLRs Function</span></span>

<span data-ttu-id="f34f6-103">Zapewnia mechanizm wyliczania CLRs w procesie.</span><span class="sxs-lookup"><span data-stu-id="f34f6-103">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f34f6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f34f6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f34f6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f34f6-105">Parameters</span></span>  

 `debuggeePID`  
 <span data-ttu-id="f34f6-106">podczas Identyfikator procesu, z którego jest wyliczany załadowany CLRs.</span><span class="sxs-lookup"><span data-stu-id="f34f6-106">[in] Process identifier of the process from which loaded CLRs will be enumerated.</span></span>  
  
 `ppHandleArrayOut`  
 <span data-ttu-id="f34f6-107">określoną Wskaźnik do tablicy zawierającej uchwyty zdarzeń, które są używane do kontynuowania uruchamiania CLR.</span><span class="sxs-lookup"><span data-stu-id="f34f6-107">[out] Pointer to an array containing event handles that are used to continue a CLR startup.</span></span> <span data-ttu-id="f34f6-108">Nie ma gwarancji, że każdy uchwyt w tablicy jest prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="f34f6-108">Each handle in the array is not guaranteed to be valid.</span></span> <span data-ttu-id="f34f6-109">Jeśli jest prawidłowy, dojście ma być używane jako zdarzenie kontynuacji uruchamiania dla odpowiedniego środowiska uruchomieniowego, które znajduje się w tym samym indeksie `ppStringArrayOut` .</span><span class="sxs-lookup"><span data-stu-id="f34f6-109">If valid, the handle is to be used as the continue-startup event for the corresponding runtime located in the same index of `ppStringArrayOut`.</span></span>  
  
 `ppStringArrayOut`  
 <span data-ttu-id="f34f6-110">określoną Wskaźnik do tablicy ciągów, które określają pełne ścieżki do CLRs załadowane w procesie.</span><span class="sxs-lookup"><span data-stu-id="f34f6-110">[out] Pointer to an array of strings that specify full paths to CLRs loaded in the process.</span></span>  
  
 `pdwArrayLengthOut`  
 <span data-ttu-id="f34f6-111">określoną Wskaźnik na wartość typu DWORD, która zawiera długość równomiernie dopasowanego rozmiaru `ppHandleArrayOut` i `pdwArrayLengthOut` .</span><span class="sxs-lookup"><span data-stu-id="f34f6-111">[out] Pointer to a DWORD that contains the length of the equally sized `ppHandleArrayOut` and `pdwArrayLengthOut`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f34f6-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f34f6-112">Return Value</span></span>  

 <span data-ttu-id="f34f6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f34f6-113">S_OK</span></span>  
 <span data-ttu-id="f34f6-114">Liczba CLRs w procesie została pomyślnie określona, a odpowiednie tablice uchwytów i ścieżek zostały prawidłowo wypełnione.</span><span class="sxs-lookup"><span data-stu-id="f34f6-114">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="f34f6-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f34f6-115">E_INVALIDARG</span></span>  
 <span data-ttu-id="f34f6-116">Albo `ppHandleArrayOut` ma `ppStringArrayOut` wartość null lub `pdwArrayLengthOut` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="f34f6-116">Either `ppHandleArrayOut` or `ppStringArrayOut` is null, or `pdwArrayLengthOut` is null.</span></span>  
  
 <span data-ttu-id="f34f6-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f34f6-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f34f6-118">Funkcja nie może przydzielić wystarczającej ilości pamięci dla tablic uchwytu i ścieżki.</span><span class="sxs-lookup"><span data-stu-id="f34f6-118">The function is unable to allocate enough memory for the handle and path arrays.</span></span>  
  
 <span data-ttu-id="f34f6-119">E_FAIL (lub inne kody powrotne E_)</span><span class="sxs-lookup"><span data-stu-id="f34f6-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f34f6-120">Nie można wyliczyć załadowanych CLRs.</span><span class="sxs-lookup"><span data-stu-id="f34f6-120">Unable to enumerate loaded CLRs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f34f6-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f34f6-121">Remarks</span></span>  

 <span data-ttu-id="f34f6-122">Dla procesu docelowego, który jest identyfikowany przez `debuggeePID` , funkcja zwraca tablicę ścieżek, `ppStringArrayOut` do CLRs załadowanej w procesie; tablica dojść do zdarzeń, `ppHandleArrayOut` która może zawierać zdarzenie kontynuacji uruchamiania dla środowiska CLR w tym samym indeksie; oraz rozmiar tablic, `pdwArrayLengthOut` który określa liczbę załadowanych CLRs.</span><span class="sxs-lookup"><span data-stu-id="f34f6-122">For a target process that is identified by `debuggeePID`, the function returns an array of paths, `ppStringArrayOut`, to CLRs loaded in the process; an array of event handles, `ppHandleArrayOut`, which may contain a continue-startup event for the CLR at the same index; and the size of the arrays, `pdwArrayLengthOut`, which specifies the number of CLRs that are loaded.</span></span>  
  
 <span data-ttu-id="f34f6-123">W systemie operacyjnym Windows `debuggeePID` mapuje na identyfikator procesu systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="f34f6-123">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="f34f6-124">Pamięć dla `ppHandleArrayOut` i `ppStringArrayOut` są przydzielone przez tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="f34f6-124">The memory for `ppHandleArrayOut` and `ppStringArrayOut` are allocated by this function.</span></span> <span data-ttu-id="f34f6-125">Aby zwolnić przydzieloną pamięć, należy wywołać [funkcję CloseCLREnumeration](closeclrenumeration-function.md).</span><span class="sxs-lookup"><span data-stu-id="f34f6-125">To free the memory allocated, you must call [CloseCLREnumeration Function](closeclrenumeration-function.md).</span></span>  
  
 <span data-ttu-id="f34f6-126">Tę funkcję można wywołać z parametrami tablicy ustawionymi na wartość null, aby można było zwrócić liczbę CLRs w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="f34f6-126">This function can be called with both array parameters set to null in order to return the count of CLRs in the target process.</span></span> <span data-ttu-id="f34f6-127">Z tego licznika obiekt wywołujący może wnioskować o rozmiar buforu, który zostanie utworzony: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)` .</span><span class="sxs-lookup"><span data-stu-id="f34f6-127">From this count, a caller can infer the size of the buffer that will be created: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f34f6-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f34f6-128">Requirements</span></span>  

 <span data-ttu-id="f34f6-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f34f6-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f34f6-130">**Nagłówek:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="f34f6-130">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="f34f6-131">**Biblioteka:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="f34f6-131">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="f34f6-132">**.NET Framework wersje:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f34f6-132">**.NET Framework Versions:** 3.5 SP1</span></span>
