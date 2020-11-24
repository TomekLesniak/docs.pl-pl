---
title: ICLRStrongName::StrongNameSignatureSize — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: f43a4e65442ca79ece71ce7e5e014309a611d7cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671619"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="70324-102">ICLRStrongName::StrongNameSignatureSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="70324-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>

<span data-ttu-id="70324-103">Zwraca rozmiar sygnatury silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="70324-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="70324-104">Ta metoda jest zwykle używana przez kompilatory do określenia ilości miejsca do zarezerwowania w pliku podczas tworzenia zestawu z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="70324-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70324-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="70324-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="70324-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="70324-106">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="70324-107">podczas Struktura typu [PublicKeyBlob —](../strong-naming/publickeyblob-structure.md) , która zawiera publiczną część pary kluczy używanej do generowania podpisu silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="70324-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="70324-108">podczas Rozmiar, w bajtach, z `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="70324-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="70324-109">podczas Liczba bajtów wymagana do zapisania sygnatury silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="70324-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70324-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="70324-110">Return Value</span></span>  

 <span data-ttu-id="70324-111">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="70324-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70324-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70324-112">Requirements</span></span>  

 <span data-ttu-id="70324-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70324-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70324-114">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="70324-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="70324-115">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70324-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70324-116">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70324-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70324-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70324-117">See also</span></span>

- [<span data-ttu-id="70324-118">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70324-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
