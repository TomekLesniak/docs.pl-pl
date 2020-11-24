---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException — Metoda
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
ms.openlocfilehash: 33927cc0e3a3cdaad70d437f9dd5ca5dfdcdc46b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673565"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="ea62d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException — Metoda</span><span class="sxs-lookup"><span data-stu-id="ea62d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>

<span data-ttu-id="ea62d-103">Pobiera pakiet programu Watson dla bieżącego wyjątku w wątku wywołującym.</span><span class="sxs-lookup"><span data-stu-id="ea62d-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="ea62d-104">*Zasobnik* to kolekcja danych błędów, która jest powiązana z tą samą wadą kodu.</span><span class="sxs-lookup"><span data-stu-id="ea62d-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="ea62d-105">Program *Watson* odwołuje się do zestawu technologii służących do zbierania i analizowania danych, które są skojarzone z wyjątkiem.</span><span class="sxs-lookup"><span data-stu-id="ea62d-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea62d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="ea62d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea62d-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="ea62d-107">Parameters</span></span>  

 `pParams`  
 <span data-ttu-id="ea62d-108">określoną Wskaźnik do struktury [BucketParameters —](bucketparameters-structure.md) , która zawiera dane błędów dla wyjątku.</span><span class="sxs-lookup"><span data-stu-id="ea62d-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea62d-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ea62d-109">Requirements</span></span>  

 <span data-ttu-id="ea62d-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea62d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea62d-111">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ea62d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea62d-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea62d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea62d-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea62d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea62d-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ea62d-114">See also</span></span>

- [<span data-ttu-id="ea62d-115">ICLRErrorReportingManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ea62d-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
