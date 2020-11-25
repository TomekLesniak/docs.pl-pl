---
title: StrongNameFreeBuffer — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: d93bda046a79dbdec2195eee48fefc1e5538b2e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732258"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="59623-102">StrongNameFreeBuffer — Funkcja</span><span class="sxs-lookup"><span data-stu-id="59623-102">StrongNameFreeBuffer Function</span></span>

<span data-ttu-id="59623-103">Zwalnia pamięć, która została przypisana przy użyciu poprzedniego wywołania funkcji silnej nazwy, takiej jak [StrongNameGetPublicKey —](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey —](strongnametokenfrompublickey-function.md)lub [StrongNameSignatureGeneration —](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="59623-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="59623-104">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="59623-104">This function has been deprecated.</span></span> <span data-ttu-id="59623-105">Zamiast tego użyj metody [ICLRStrongName:: StrongNameFreeBuffer —](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59623-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59623-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="59623-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59623-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="59623-107">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="59623-108">podczas Wskaźnik do pamięci do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="59623-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59623-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="59623-109">Requirements</span></span>  

 <span data-ttu-id="59623-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59623-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59623-111">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="59623-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="59623-112">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59623-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59623-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59623-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59623-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="59623-114">See also</span></span>

- [<span data-ttu-id="59623-115">StrongNameFreeBuffer, metoda</span><span class="sxs-lookup"><span data-stu-id="59623-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="59623-116">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="59623-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
