---
title: IMetaDataValidate — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataValidate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate
helpviewer_keywords:
- IMetaDataValidate interface [.NET Framework metadata]
ms.assetid: db98608a-e85c-4f50-9d7b-5f57a426ddb6
topic_type:
- apiref
ms.openlocfilehash: 518ee65bc684f643bf4f608223c0fa40ea3f0dd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685542"
---
# <a name="imetadatavalidate-interface"></a><span data-ttu-id="a42c1-102">IMetaDataValidate — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a42c1-102">IMetaDataValidate Interface</span></span>

<span data-ttu-id="a42c1-103">Zapewnia metody weryfikacji podpisów metadanych.</span><span class="sxs-lookup"><span data-stu-id="a42c1-103">Provides methods to validate metadata signatures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a42c1-104">Metody</span><span class="sxs-lookup"><span data-stu-id="a42c1-104">Methods</span></span>  
  
|<span data-ttu-id="a42c1-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="a42c1-105">Method</span></span>|<span data-ttu-id="a42c1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="a42c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a42c1-107">ValidateMetaData, metoda</span><span class="sxs-lookup"><span data-stu-id="a42c1-107">ValidateMetaData Method</span></span>](imetadatavalidate-validatemetadata-method.md)|<span data-ttu-id="a42c1-108">Sprawdza poprawność podpisów metadanych obiektów w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="a42c1-108">Validates the metadata signatures of the objects in the current metadata scope.</span></span>|  
|[<span data-ttu-id="a42c1-109">ValidatorInit, metoda</span><span class="sxs-lookup"><span data-stu-id="a42c1-109">ValidatorInit Method</span></span>](imetadatavalidate-validatorinit-method.md)|<span data-ttu-id="a42c1-110">Ustawia flagę określającą typ modułu w bieżącym zakresie metadanych i rejestruje określoną metodę wywołania zwrotnego dla błędów walidacji.</span><span class="sxs-lookup"><span data-stu-id="a42c1-110">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a42c1-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a42c1-111">Requirements</span></span>  

 <span data-ttu-id="a42c1-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a42c1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a42c1-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a42c1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a42c1-114">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a42c1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a42c1-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a42c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42c1-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a42c1-116">See also</span></span>

- [<span data-ttu-id="a42c1-117">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="a42c1-117">Metadata Interfaces</span></span>](metadata-interfaces.md)
