---
title: IMetaDataConverter::GetTypeLibFromMetaData — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: eed8661f8885ca16492ab336a599b5290057843a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714604"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="65f25-102">IMetaDataConverter::GetTypeLibFromMetaData — Metoda</span><span class="sxs-lookup"><span data-stu-id="65f25-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>

<span data-ttu-id="65f25-103">Pobiera wskaźnik do `ITypeLib` wystąpienia, które reprezentuje bibliotekę typów, która ma określoną nazwę biblioteki i modułu.</span><span class="sxs-lookup"><span data-stu-id="65f25-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f25-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="65f25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65f25-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="65f25-105">Parameters</span></span>  

 `strModule`  
 <span data-ttu-id="65f25-106">podczas Nazwa modułu biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="65f25-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="65f25-107">podczas Nazwa biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="65f25-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="65f25-108">określoną Wskaźnik do lokalizacji, która otrzymuje adres `ITypeLib` wystąpienia, które reprezentuje bibliotekę typów.</span><span class="sxs-lookup"><span data-stu-id="65f25-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65f25-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="65f25-109">Requirements</span></span>  

 <span data-ttu-id="65f25-110">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f25-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65f25-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="65f25-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65f25-112">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65f25-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65f25-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65f25-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f25-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="65f25-114">See also</span></span>

- [<span data-ttu-id="65f25-115">IMetaDataConverter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65f25-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)
