---
title: ICLRStrongName::GetHashFromHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: 68bfdb2f66147b54c75b8f577a01278016e248b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685737"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="588b9-102">ICLRStrongName::GetHashFromHandle — Metoda</span><span class="sxs-lookup"><span data-stu-id="588b9-102">ICLRStrongName::GetHashFromHandle Method</span></span>

<span data-ttu-id="588b9-103">Generuje skrót do zawartości pliku, który ma określone dojście do pliku, przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="588b9-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="588b9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="588b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="588b9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="588b9-105">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="588b9-106">podczas Dojście pliku do mieszania.</span><span class="sxs-lookup"><span data-stu-id="588b9-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="588b9-107">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="588b9-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="588b9-108">Użyj wartości zero dla algorytmu domyślnego.</span><span class="sxs-lookup"><span data-stu-id="588b9-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="588b9-109">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="588b9-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="588b9-110">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="588b9-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="588b9-111">określoną Rozmiar zwracanych wartości (w bajtach) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="588b9-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="588b9-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="588b9-112">Return Value</span></span>  

 <span data-ttu-id="588b9-113">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="588b9-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="588b9-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="588b9-114">Requirements</span></span>  

 <span data-ttu-id="588b9-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="588b9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="588b9-116">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="588b9-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="588b9-117">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="588b9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="588b9-118">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="588b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="588b9-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="588b9-119">See also</span></span>

- [<span data-ttu-id="588b9-120">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="588b9-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
