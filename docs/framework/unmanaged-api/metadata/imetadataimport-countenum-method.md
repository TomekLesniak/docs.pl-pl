---
title: IMetaDataImport::CountEnum — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: f2470cd7112adff35ef49c21a155072fcd4008be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727292"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="23d42-102">IMetaDataImport::CountEnum — Metoda</span><span class="sxs-lookup"><span data-stu-id="23d42-102">IMetaDataImport::CountEnum Method</span></span>

<span data-ttu-id="23d42-103">Pobiera liczbę elementów w wyliczeniu, która została pobrana przez określony moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="23d42-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d42-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="23d42-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23d42-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="23d42-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="23d42-106">podczas Uchwyt dla modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="23d42-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="23d42-107">określoną Liczba wyliczonych elementów.</span><span class="sxs-lookup"><span data-stu-id="23d42-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d42-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="23d42-108">Remarks</span></span>  

 <span data-ttu-id="23d42-109">Dojście określone przez `hEnum` jest uzyskiwane z poprzedniego `Enum` wywołania *nazwy* (na przykład [IMetaDataImport:: EnumTypeDefs —](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="23d42-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d42-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="23d42-110">Requirements</span></span>  

 <span data-ttu-id="23d42-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23d42-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d42-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="23d42-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23d42-113">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23d42-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23d42-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d42-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="23d42-115">See also</span></span>

- [<span data-ttu-id="23d42-116">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="23d42-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="23d42-117">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="23d42-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
