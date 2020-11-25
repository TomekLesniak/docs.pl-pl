---
title: StrongNameTokenFromPublicKey — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 89556cf0e1ef65c35278a526e10fc791063ea2c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708351"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="19a9d-102">StrongNameTokenFromPublicKey — Funkcja</span><span class="sxs-lookup"><span data-stu-id="19a9d-102">StrongNameTokenFromPublicKey Function</span></span>

<span data-ttu-id="19a9d-103">Pobiera token reprezentujący klucz publiczny.</span><span class="sxs-lookup"><span data-stu-id="19a9d-103">Gets a token representing a public key.</span></span> <span data-ttu-id="19a9d-104">Token silnej nazwy to skrócona postać klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="19a9d-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="19a9d-105">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="19a9d-105">This function has been deprecated.</span></span> <span data-ttu-id="19a9d-106">Zamiast tego użyj metody [ICLRStrongName:: StrongNameTokenFromPublicKey —](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="19a9d-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a9d-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="19a9d-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19a9d-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="19a9d-108">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="19a9d-109">podczas Struktura typu [PublicKeyBlob —](publickeyblob-structure.md) , która zawiera publiczną część pary kluczy używanej do generowania podpisu silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="19a9d-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="19a9d-110">podczas Rozmiar, w bajtach, z `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="19a9d-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="19a9d-111">określoną Token silnej nazwy odpowiadający kluczowi przekazaniu `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="19a9d-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="19a9d-112">Środowisko uruchomieniowe języka wspólnego przydziela pamięć, w której ma zostać zwrócony token.</span><span class="sxs-lookup"><span data-stu-id="19a9d-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="19a9d-113">Obiekt wywołujący musi zwolnić tę pamięć przy użyciu funkcji [StrongNameFreeBuffer —](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="19a9d-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="19a9d-114">określoną Rozmiar (w bajtach) zwracanego tokenu silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="19a9d-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19a9d-115">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="19a9d-115">Return Value</span></span>  

 <span data-ttu-id="19a9d-116">`true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="19a9d-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19a9d-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="19a9d-117">Remarks</span></span>  

 <span data-ttu-id="19a9d-118">Token silnej nazwy to Skrócona forma klucza publicznego służąca do oszczędzania miejsca podczas przechowywania informacji o kluczu w metadanych.</span><span class="sxs-lookup"><span data-stu-id="19a9d-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="19a9d-119">W odniesieniu do zestawu zależnego w odwołaniach do zestawów są używane tokeny silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="19a9d-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="19a9d-120">Jeśli `StrongNameTokenFromPublicKey` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.</span><span class="sxs-lookup"><span data-stu-id="19a9d-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19a9d-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="19a9d-121">Requirements</span></span>  

 <span data-ttu-id="19a9d-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19a9d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19a9d-123">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="19a9d-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="19a9d-124">**Biblioteka:** Uwzględnione jako zasób w mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="19a9d-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="19a9d-125">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19a9d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a9d-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="19a9d-126">See also</span></span>

- [<span data-ttu-id="19a9d-127">StrongNameTokenFromPublicKey, metoda</span><span class="sxs-lookup"><span data-stu-id="19a9d-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="19a9d-128">StrongNameGetPublicKey, metoda</span><span class="sxs-lookup"><span data-stu-id="19a9d-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="19a9d-129">PublicKeyBlob — Struktura</span><span class="sxs-lookup"><span data-stu-id="19a9d-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
