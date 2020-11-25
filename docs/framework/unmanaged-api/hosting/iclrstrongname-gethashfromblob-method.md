---
title: ICLRStrongName::GetHashFromBlob — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714812"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="7200c-102">ICLRStrongName::GetHashFromBlob — Metoda</span><span class="sxs-lookup"><span data-stu-id="7200c-102">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="7200c-103">Pobiera skrót zestawu pod określonym adresem pamięci przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7200c-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7200c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7200c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7200c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7200c-105">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="7200c-106">podczas Wskaźnik do adresu bloku pamięci, który ma zostać zmieszany.</span><span class="sxs-lookup"><span data-stu-id="7200c-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="7200c-107">podczas Długość (w bajtach) bloku pamięci.</span><span class="sxs-lookup"><span data-stu-id="7200c-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7200c-108">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7200c-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="7200c-109">Użyj wartości zero dla algorytmu domyślnego.</span><span class="sxs-lookup"><span data-stu-id="7200c-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7200c-110">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7200c-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7200c-111">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="7200c-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7200c-112">określoną Rozmiar zwracanych wartości (w bajtach) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="7200c-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7200c-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7200c-113">Return Value</span></span>  

 <span data-ttu-id="7200c-114">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="7200c-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7200c-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7200c-115">Requirements</span></span>  

 <span data-ttu-id="7200c-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7200c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7200c-117">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="7200c-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7200c-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7200c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7200c-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7200c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7200c-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7200c-120">See also</span></span>

- [<span data-ttu-id="7200c-121">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7200c-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
