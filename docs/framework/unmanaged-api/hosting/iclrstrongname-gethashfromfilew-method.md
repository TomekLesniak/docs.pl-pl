---
title: ICLRStrongName::GetHashFromFileW — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: eda78976f175230cc2405b9cb151993e63697e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685763"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="44637-102">ICLRStrongName::GetHashFromFileW — Metoda</span><span class="sxs-lookup"><span data-stu-id="44637-102">ICLRStrongName::GetHashFromFileW Method</span></span>

<span data-ttu-id="44637-103">Generuje skrót do zawartości pliku określonego przez ciąg Unicode.</span><span class="sxs-lookup"><span data-stu-id="44637-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44637-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="44637-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="44637-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="44637-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="44637-106">podczas Nazwa Unicode pliku do skrótu.</span><span class="sxs-lookup"><span data-stu-id="44637-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="44637-107">[in. out] Algorytm, który ma być używany podczas generowania skrótu.</span><span class="sxs-lookup"><span data-stu-id="44637-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="44637-108">Prawidłowymi algorytmami są te zdefiniowane przez interfejs CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="44637-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="44637-109">Jeśli `piHashAlg` jest ustawiona na 0, zostanie użyty domyślny algorytm CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="44637-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="44637-110">określoną Tablica bajtowa zawierająca wygenerowany skrót.</span><span class="sxs-lookup"><span data-stu-id="44637-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="44637-111">podczas Maksymalny rozmiar buforu wskazywany przez `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="44637-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="44637-112">określoną Rozmiar, w bajtach, z `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="44637-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44637-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="44637-113">Return Value</span></span>  

 <span data-ttu-id="44637-114">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="44637-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44637-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="44637-115">Remarks</span></span>  

 <span data-ttu-id="44637-116">Ta metoda jest taka sama jak Metoda [ICLRStrongName:: GetHashFromFile —](iclrstrongname-gethashfromfile-method.md) , z tą różnicą, że Specyfikacja nazwy pliku jest Unicode zamiast ANSI.</span><span class="sxs-lookup"><span data-stu-id="44637-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44637-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="44637-117">Requirements</span></span>  

 <span data-ttu-id="44637-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44637-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44637-119">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="44637-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="44637-120">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44637-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44637-121">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44637-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44637-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="44637-122">See also</span></span>

- [<span data-ttu-id="44637-123">GetHashFromFile, metoda</span><span class="sxs-lookup"><span data-stu-id="44637-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="44637-124">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="44637-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
