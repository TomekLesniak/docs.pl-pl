---
title: GetHashFromAssemblyFile — Funkcja
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: caefc9773b0d208f8b20847b664f7bc017d2c076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730997"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="7a9d9-102">GetHashFromAssemblyFile — Funkcja</span><span class="sxs-lookup"><span data-stu-id="7a9d9-102">GetHashFromAssemblyFile Function</span></span>

<span data-ttu-id="7a9d9-103">Pobiera skrót określonego pliku zestawu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7a9d9-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7a9d9-104">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="7a9d9-104">This function has been deprecated.</span></span> <span data-ttu-id="7a9d9-105">Zamiast tego użyj metody [ICLRStrongName:: GetHashFromAssemblyFile —](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7a9d9-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a9d9-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="7a9d9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a9d9-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="7a9d9-107">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="7a9d9-108">podczas Ścieżka do pliku, który ma zostać poddany skrótowi.</span><span class="sxs-lookup"><span data-stu-id="7a9d9-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7a9d9-109">[in. out] Stała, która określa algorytm wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7a9d9-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="7a9d9-110">Użyj wartości zero dla domyślnego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7a9d9-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7a9d9-111">określoną Zwrócony bufor wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="7a9d9-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7a9d9-112">podczas Żądany maksymalny rozmiar `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="7a9d9-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7a9d9-113">określoną Zwrócony rozmiar, w bajtach, z `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="7a9d9-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a9d9-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7a9d9-114">Requirements</span></span>  

 <span data-ttu-id="7a9d9-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a9d9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a9d9-116">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="7a9d9-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7a9d9-117">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a9d9-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a9d9-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a9d9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9d9-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7a9d9-119">See also</span></span>

- [<span data-ttu-id="7a9d9-120">GetHashFromAssemblyFile, metoda</span><span class="sxs-lookup"><span data-stu-id="7a9d9-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="7a9d9-121">GetHashFromAssemblyFileW, metoda</span><span class="sxs-lookup"><span data-stu-id="7a9d9-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="7a9d9-122">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7a9d9-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
