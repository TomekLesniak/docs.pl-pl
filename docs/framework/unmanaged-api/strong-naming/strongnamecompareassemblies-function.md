---
title: StrongNameCompareAssemblies — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: e7292635ea0344f1c77c8d44908a9a811e464ff9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732310"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="68e45-102">StrongNameCompareAssemblies — Funkcja</span><span class="sxs-lookup"><span data-stu-id="68e45-102">StrongNameCompareAssemblies Function</span></span>

<span data-ttu-id="68e45-103">Określa, czy dwa zestawy różnią się tylko sygnaturami silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="68e45-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="68e45-104">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="68e45-104">This function has been deprecated.</span></span> <span data-ttu-id="68e45-105">Zamiast tego użyj metody [ICLRStrongName:: StrongNameCompareAssemblies —](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .</span><span class="sxs-lookup"><span data-stu-id="68e45-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68e45-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="68e45-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68e45-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="68e45-107">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="68e45-108">podczas Ścieżka do pierwszego zestawu.</span><span class="sxs-lookup"><span data-stu-id="68e45-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="68e45-109">podczas Ścieżka do drugiego zestawu.</span><span class="sxs-lookup"><span data-stu-id="68e45-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="68e45-110">określoną Jedna z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="68e45-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="68e45-111">`SN_CMP_DIFFERENT` (0) — określa, że zestawy zawierają różne dane.</span><span class="sxs-lookup"><span data-stu-id="68e45-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="68e45-112">`SN_CMP_IDENTICAL` (1) — określa, że zestawy są dokładnie takie same, łącznie z ich sygnaturami i sumą kontrolną.</span><span class="sxs-lookup"><span data-stu-id="68e45-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="68e45-113">`SN_CMP_SIGONLY` (2) — określa, że zestawy różnią się tylko sygnaturą i sumą kontrolną.</span><span class="sxs-lookup"><span data-stu-id="68e45-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68e45-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="68e45-114">Return Value</span></span>  

 <span data-ttu-id="68e45-115">`true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="68e45-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68e45-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="68e45-116">Requirements</span></span>  

 <span data-ttu-id="68e45-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68e45-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68e45-118">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="68e45-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="68e45-119">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68e45-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68e45-120">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68e45-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68e45-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="68e45-121">Remarks</span></span>  

 <span data-ttu-id="68e45-122">Podpis silnej nazwy zestawu składa się z nazwy tekstu, wersji, kultury i tokenu klucza publicznego zestawu.</span><span class="sxs-lookup"><span data-stu-id="68e45-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="68e45-123">Jeśli `StrongNameCompareAssemblies` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.</span><span class="sxs-lookup"><span data-stu-id="68e45-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e45-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="68e45-124">See also</span></span>

- [<span data-ttu-id="68e45-125">StrongNameCompareAssemblies, metoda</span><span class="sxs-lookup"><span data-stu-id="68e45-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="68e45-126">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="68e45-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
