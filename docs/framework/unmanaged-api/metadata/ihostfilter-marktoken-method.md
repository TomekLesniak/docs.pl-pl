---
title: IHostFilter::MarkToken — Metoda
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718231"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="b3aca-102">IHostFilter::MarkToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="b3aca-102">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="b3aca-103">Wskazuje, że określony token metadanych zostanie przetworzony.</span><span class="sxs-lookup"><span data-stu-id="b3aca-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3aca-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b3aca-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3aca-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b3aca-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="b3aca-106">podczas Token metadanych do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="b3aca-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3aca-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b3aca-107">Remarks</span></span>  

 <span data-ttu-id="b3aca-108">Zazwyczaj token ma być przetwarzany, jeśli znajduje się w zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="b3aca-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="b3aca-109">`MarkToken`Metoda jest przenoszona do aparatu metadanych za pośrednictwem metody [IMetaDataEmit:: sethandlee](imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b3aca-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3aca-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b3aca-110">Requirements</span></span>  

 <span data-ttu-id="b3aca-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3aca-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3aca-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b3aca-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3aca-113">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3aca-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3aca-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3aca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3aca-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b3aca-115">See also</span></span>

- [<span data-ttu-id="b3aca-116">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="b3aca-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="b3aca-117">IHostFilter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b3aca-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)
