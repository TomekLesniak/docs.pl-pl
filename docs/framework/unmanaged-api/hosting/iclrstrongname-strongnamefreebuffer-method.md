---
title: ICLRStrongName::StrongNameFreeBuffer — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: 0f96ac606bd68226cbd657c3fc1aa7cf0ffc166b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726135"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="fa312-102">ICLRStrongName::StrongNameFreeBuffer — Metoda</span><span class="sxs-lookup"><span data-stu-id="fa312-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>

<span data-ttu-id="fa312-103">Zwalnia pamięć, która została przypisana przy użyciu poprzedniego wywołania metody silnej nazwy, takiej jak [ICLRStrongName:: StrongNameGetPublicKey —](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey —](iclrstrongname-strongnametokenfrompublickey-method.md)lub [ICLRStrongName:: StrongNameSignatureGeneration —](iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="fa312-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa312-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fa312-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa312-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fa312-105">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="fa312-106">podczas Wskaźnik do pamięci do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="fa312-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa312-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="fa312-107">Return Value</span></span>  

 <span data-ttu-id="fa312-108">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="fa312-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa312-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fa312-109">Requirements</span></span>  

 <span data-ttu-id="fa312-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa312-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa312-111">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="fa312-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa312-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa312-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa312-113">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa312-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa312-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fa312-114">See also</span></span>

- [<span data-ttu-id="fa312-115">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fa312-115">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
