---
title: GetHashFromAssemblyFileW — Funkcja
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: b895c77850c0457fd2a152c1128c016093599f76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730984"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="fc128-102">GetHashFromAssemblyFileW — Funkcja</span><span class="sxs-lookup"><span data-stu-id="fc128-102">GetHashFromAssemblyFileW Function</span></span>

<span data-ttu-id="fc128-103">Pobiera skrót określonego pliku zestawu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="fc128-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="fc128-104">Ścieżka do pliku zestawu musi być określona jako ciąg Unicode.</span><span class="sxs-lookup"><span data-stu-id="fc128-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="fc128-105">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="fc128-105">This function has been deprecated.</span></span> <span data-ttu-id="fc128-106">Zamiast tego użyj metody [ICLRStrongName:: GetHashFromAssemblyFileW —](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fc128-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc128-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="fc128-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc128-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="fc128-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="fc128-109">podczas Ścieżka do pliku, który ma zostać poddany skrótowi.</span><span class="sxs-lookup"><span data-stu-id="fc128-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="fc128-110">Ten parametr musi być ciągiem Unicode.</span><span class="sxs-lookup"><span data-stu-id="fc128-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fc128-111">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="fc128-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="fc128-112">Użyj wartości zero dla domyślnego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="fc128-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fc128-113">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="fc128-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fc128-114">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="fc128-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fc128-115">określoną Zwrócony rozmiar, w bajtach, z `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="fc128-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc128-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fc128-116">Requirements</span></span>  

 <span data-ttu-id="fc128-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc128-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc128-118">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="fc128-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fc128-119">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc128-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc128-120">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc128-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc128-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fc128-121">See also</span></span>

- [<span data-ttu-id="fc128-122">GetHashFromAssemblyFileW, metoda</span><span class="sxs-lookup"><span data-stu-id="fc128-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="fc128-123">GetHashFromAssemblyFile, metoda</span><span class="sxs-lookup"><span data-stu-id="fc128-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="fc128-124">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fc128-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
