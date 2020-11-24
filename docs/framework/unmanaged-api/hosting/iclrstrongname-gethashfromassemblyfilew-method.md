---
title: ICLRStrongName::GetHashFromAssemblyFileW — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: e94bfe6151ed42886355423a838f21e13748ec61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685776"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="9d77b-102">ICLRStrongName::GetHashFromAssemblyFileW — Metoda</span><span class="sxs-lookup"><span data-stu-id="9d77b-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="9d77b-103">Generuje skrót do zawartości pliku określonego przez ciąg Unicode.</span><span class="sxs-lookup"><span data-stu-id="9d77b-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d77b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9d77b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d77b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9d77b-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="9d77b-106">podczas Ścieżka do pliku, który ma zostać poddany skrótowi.</span><span class="sxs-lookup"><span data-stu-id="9d77b-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="9d77b-107">Ten parametr musi być ciągiem Unicode.</span><span class="sxs-lookup"><span data-stu-id="9d77b-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9d77b-108">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="9d77b-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="9d77b-109">Użyj wartości zero dla domyślnego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="9d77b-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9d77b-110">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="9d77b-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9d77b-111">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="9d77b-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9d77b-112">określoną Zwrócony rozmiar, w bajtach, z `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="9d77b-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d77b-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9d77b-113">Return Value</span></span>  

 <span data-ttu-id="9d77b-114">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="9d77b-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d77b-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9d77b-115">Requirements</span></span>  

 <span data-ttu-id="9d77b-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d77b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d77b-117">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="9d77b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d77b-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d77b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d77b-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d77b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d77b-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9d77b-120">See also</span></span>

- [<span data-ttu-id="9d77b-121">GetHashFromAssemblyFile, metoda</span><span class="sxs-lookup"><span data-stu-id="9d77b-121">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="9d77b-122">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9d77b-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
