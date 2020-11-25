---
title: ICLRStrongName::GetHashFromAssemblyFile — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 0a15a4d237f63da54615ee1801e6cd39620e8274
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727864"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="b403e-102">ICLRStrongName::GetHashFromAssemblyFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="b403e-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>

<span data-ttu-id="b403e-103">Pobiera skrót określonego pliku zestawu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="b403e-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b403e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b403e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b403e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b403e-105">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="b403e-106">podczas Ścieżka do pliku, który ma zostać poddany skrótowi.</span><span class="sxs-lookup"><span data-stu-id="b403e-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b403e-107">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="b403e-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="b403e-108">Użyj wartości zero dla domyślnego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="b403e-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b403e-109">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="b403e-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b403e-110">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="b403e-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b403e-111">określoną Zwrócony rozmiar, w bajtach, z `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="b403e-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b403e-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b403e-112">Return Value</span></span>  

 <span data-ttu-id="b403e-113">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="b403e-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b403e-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b403e-114">Requirements</span></span>  

 <span data-ttu-id="b403e-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b403e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b403e-116">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="b403e-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b403e-117">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b403e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b403e-118">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b403e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b403e-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b403e-119">See also</span></span>

- [<span data-ttu-id="b403e-120">GetHashFromAssemblyFileW, metoda</span><span class="sxs-lookup"><span data-stu-id="b403e-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="b403e-121">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b403e-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
