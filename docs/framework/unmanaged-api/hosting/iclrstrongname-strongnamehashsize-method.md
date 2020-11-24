---
title: ICLRStrongName::StrongNameHashSize — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 6ee87fdbf75d4a07a7337a1c9fdc58a06191b992
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674819"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="8d363-102">ICLRStrongName::StrongNameHashSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="8d363-102">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="8d363-103">Pobiera rozmiar buforu wymagany dla skrótu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="8d363-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d363-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8d363-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d363-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8d363-105">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="8d363-106">podczas Algorytm wyznaczania wartości skrótu używany do obliczania rozmiaru buforu.</span><span class="sxs-lookup"><span data-stu-id="8d363-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="8d363-107">określoną Zwrócony rozmiar buforu w bajtach.</span><span class="sxs-lookup"><span data-stu-id="8d363-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d363-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="8d363-108">Return Value</span></span>  

 <span data-ttu-id="8d363-109">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="8d363-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d363-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8d363-110">Requirements</span></span>  

 <span data-ttu-id="8d363-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d363-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d363-112">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="8d363-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8d363-113">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d363-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d363-114">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d363-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d363-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8d363-115">See also</span></span>

- [<span data-ttu-id="8d363-116">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8d363-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
