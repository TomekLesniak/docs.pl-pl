---
title: GetHashFromHandle — Funkcja
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: 904dcb707e704cfec2dba4e6587f7e3acaf7b538
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732336"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="f487b-102">GetHashFromHandle — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f487b-102">GetHashFromHandle Function</span></span>

<span data-ttu-id="f487b-103">Generuje skrót do zawartości pliku z określonym dojściem do pliku przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="f487b-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="f487b-104">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="f487b-104">This function has been deprecated.</span></span> <span data-ttu-id="f487b-105">Zamiast tego użyj metody [ICLRStrongName:: GetHashFromHandle —](../hosting/iclrstrongname-gethashfromhandle-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f487b-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f487b-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="f487b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f487b-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="f487b-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="f487b-108">podczas Dojście pliku do mieszania.</span><span class="sxs-lookup"><span data-stu-id="f487b-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f487b-109">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="f487b-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f487b-110">Użyj wartości zero dla algorytmu domyślnego.</span><span class="sxs-lookup"><span data-stu-id="f487b-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f487b-111">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="f487b-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f487b-112">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f487b-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f487b-113">określoną Rozmiar zwracanych wartości (w bajtach) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f487b-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f487b-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f487b-114">Requirements</span></span>  

 <span data-ttu-id="f487b-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f487b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f487b-116">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="f487b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f487b-117">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f487b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f487b-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f487b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f487b-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f487b-119">See also</span></span>

- [<span data-ttu-id="f487b-120">GetHashFromHandle, metoda</span><span class="sxs-lookup"><span data-stu-id="f487b-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="f487b-121">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f487b-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
