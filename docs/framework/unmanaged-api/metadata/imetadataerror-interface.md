---
title: IMetaDataError — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 5f5e04787ce0ab0e1c8ecf3c19ba37e76ba38bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701929"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="f5ecf-102">IMetaDataError — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f5ecf-102">IMetaDataError Interface</span></span>

<span data-ttu-id="f5ecf-103">Zapewnia mechanizm wywołania zwrotnego do raportowania błędów podczas scalania metadanych.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5ecf-104">`IMetaDataError`Interfejs musi być zaimplementowany przez klienta.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5ecf-105">Metody</span><span class="sxs-lookup"><span data-stu-id="f5ecf-105">Methods</span></span>  
  
|<span data-ttu-id="f5ecf-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="f5ecf-106">Method</span></span>|<span data-ttu-id="f5ecf-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f5ecf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5ecf-108">OnError, metoda</span><span class="sxs-lookup"><span data-stu-id="f5ecf-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="f5ecf-109">Zawiera powiadomienie o błędach występujących podczas scalania metadanych.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5ecf-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f5ecf-110">Requirements</span></span>  

 <span data-ttu-id="f5ecf-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5ecf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ecf-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f5ecf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5ecf-113">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5ecf-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5ecf-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ecf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ecf-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f5ecf-115">See also</span></span>

- [<span data-ttu-id="f5ecf-116">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="f5ecf-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
