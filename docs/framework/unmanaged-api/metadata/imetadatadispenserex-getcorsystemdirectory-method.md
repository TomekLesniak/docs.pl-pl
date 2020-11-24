---
title: IMetaDataDispenserEx::GetCORSystemDirectory — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: ea0e6f96028afc201f498119976eb87aa762a6eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681694"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="0b75d-102">IMetaDataDispenserEx::GetCORSystemDirectory — Metoda</span><span class="sxs-lookup"><span data-stu-id="0b75d-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="0b75d-103">Pobiera katalog, który przechowuje bieżące środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="0b75d-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="0b75d-104">Ta metoda jest obsługiwana tylko dla debugerów out-of-process.</span><span class="sxs-lookup"><span data-stu-id="0b75d-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="0b75d-105">Jeśli wywoływana z innego składnika, zwróci E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0b75d-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b75d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="0b75d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b75d-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="0b75d-107">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="0b75d-108">określoną Bufor, w którym ma zostać odebrana nazwa katalogu.</span><span class="sxs-lookup"><span data-stu-id="0b75d-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0b75d-109">podczas Rozmiar, w bajtach, z `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="0b75d-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="0b75d-110">określoną Liczba bajtów, które faktycznie zostały zwrócone `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="0b75d-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b75d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0b75d-111">Requirements</span></span>  

 <span data-ttu-id="0b75d-112">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b75d-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b75d-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0b75d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b75d-114">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b75d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b75d-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b75d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b75d-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0b75d-116">See also</span></span>

- [<span data-ttu-id="0b75d-117">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0b75d-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="0b75d-118">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0b75d-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
