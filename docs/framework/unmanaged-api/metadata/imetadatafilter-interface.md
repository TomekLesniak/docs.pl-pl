---
title: IMetaDataFilter — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701851"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="80eab-102">IMetaDataFilter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="80eab-102">IMetaDataFilter Interface</span></span>

<span data-ttu-id="80eab-103">Zapewnia metody oznaczania i filtrowania tokenów metadanych, aby uniknąć powtarzających się akcji, które zostały już wykonane.</span><span class="sxs-lookup"><span data-stu-id="80eab-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80eab-104">Metody</span><span class="sxs-lookup"><span data-stu-id="80eab-104">Methods</span></span>  
  
|<span data-ttu-id="80eab-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="80eab-105">Method</span></span>|<span data-ttu-id="80eab-106">Opis</span><span class="sxs-lookup"><span data-stu-id="80eab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80eab-107">IsTokenMarked, metoda</span><span class="sxs-lookup"><span data-stu-id="80eab-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="80eab-108">Pobiera wartość wskazującą, czy określony token metadanych został przetworzony.</span><span class="sxs-lookup"><span data-stu-id="80eab-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="80eab-109">MarkToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="80eab-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="80eab-110">Ustawia wartość wskazującą, że określony token metadanych został przetworzony.</span><span class="sxs-lookup"><span data-stu-id="80eab-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="80eab-111">UnmarkAll, metoda</span><span class="sxs-lookup"><span data-stu-id="80eab-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="80eab-112">Usuwa znaczniki przetwarzania ze wszystkich tokenów w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="80eab-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80eab-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="80eab-113">Requirements</span></span>  

 <span data-ttu-id="80eab-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80eab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80eab-115">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="80eab-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80eab-116">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80eab-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80eab-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80eab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80eab-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="80eab-118">See also</span></span>

- [<span data-ttu-id="80eab-119">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="80eab-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
