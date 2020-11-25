---
title: StrongNameKeyGenEx — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708546"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="a74b6-102">StrongNameKeyGenEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a74b6-102">StrongNameKeyGenEx Function</span></span>

<span data-ttu-id="a74b6-103">Generuje nową parę kluczy publicznych/prywatnych z określonym rozmiarem klucza w celu użycia silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a74b6-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="a74b6-104">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="a74b6-104">This function has been deprecated.</span></span> <span data-ttu-id="a74b6-105">Zamiast tego użyj metody [ICLRStrongName:: StrongNameKeyGenEx —](../hosting/iclrstrongname-strongnamekeygenex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a74b6-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a74b6-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="a74b6-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a74b6-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="a74b6-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="a74b6-108">podczas Nazwa żądanego kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="a74b6-108">[in] The requested key container name.</span></span> <span data-ttu-id="a74b6-109">`wszKeyContainer` nie może być pustym ciągiem ani mieć wartości null w celu wygenerowania nazwy tymczasowej.</span><span class="sxs-lookup"><span data-stu-id="a74b6-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a74b6-110">podczas Określa, czy klucz ma pozostać zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="a74b6-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="a74b6-111">Obsługiwane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="a74b6-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="a74b6-112">0x00000000 — używany, gdy `wszKeyContainer` ma wartość null, aby wygenerować nazwę kontenera kluczy tymczasowych.</span><span class="sxs-lookup"><span data-stu-id="a74b6-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="a74b6-113">0x00000001 ( `SN_LEAVE_KEY` ) — określa, że klucz powinien pozostać zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="a74b6-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="a74b6-114">podczas Żądany rozmiar klucza w bitach.</span><span class="sxs-lookup"><span data-stu-id="a74b6-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="a74b6-115">określoną Zwracana para kluczy publiczny/prywatny.</span><span class="sxs-lookup"><span data-stu-id="a74b6-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="a74b6-116">określoną Rozmiar, w bajtach, z `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="a74b6-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a74b6-117">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a74b6-117">Return Value</span></span>  

 <span data-ttu-id="a74b6-118">`true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="a74b6-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a74b6-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a74b6-119">Remarks</span></span>  

 <span data-ttu-id="a74b6-120">Do `dwKeySize` podpisania zestawu o silnej nazwie .NET Framework wersje 1,0 i 1,1 są wymagane z 1024 BITS; w wersji 2,0 dodano 2048 obsługę kluczy.</span><span class="sxs-lookup"><span data-stu-id="a74b6-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="a74b6-121">Po pobraniu klucza należy wywołać funkcję [StrongNameFreeBuffer —](strongnamefreebuffer-function.md) , aby zwolnić przydzieloną pamięć.</span><span class="sxs-lookup"><span data-stu-id="a74b6-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="a74b6-122">Jeśli `StrongNameKeyGenEx` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.</span><span class="sxs-lookup"><span data-stu-id="a74b6-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a74b6-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a74b6-123">Requirements</span></span>  

 <span data-ttu-id="a74b6-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a74b6-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a74b6-125">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="a74b6-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a74b6-126">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a74b6-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a74b6-127">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a74b6-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74b6-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a74b6-128">See also</span></span>

- [<span data-ttu-id="a74b6-129">StrongNameKeyGenEx, metoda</span><span class="sxs-lookup"><span data-stu-id="a74b6-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="a74b6-130">StrongNameKeyGen, metoda</span><span class="sxs-lookup"><span data-stu-id="a74b6-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="a74b6-131">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a74b6-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
