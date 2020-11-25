---
title: IMetaDataImport::IsGlobal — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: 0d76abf8a9c923089f367ab4e1786ac8cc92622d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702982"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="61a83-102">IMetaDataImport::IsGlobal — Metoda</span><span class="sxs-lookup"><span data-stu-id="61a83-102">IMetaDataImport::IsGlobal Method</span></span>

<span data-ttu-id="61a83-103">Pobiera wartość wskazującą, czy pole, metoda lub typ reprezentowane przez określony token metadanych ma zakres globalny.</span><span class="sxs-lookup"><span data-stu-id="61a83-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a83-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="61a83-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61a83-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="61a83-105">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="61a83-106">podczas Token metadanych, który reprezentuje typ, pole lub metodę.</span><span class="sxs-lookup"><span data-stu-id="61a83-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="61a83-107">[out] 1, jeśli obiekt ma zakres globalny; w przeciwnym razie 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="61a83-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61a83-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="61a83-108">Requirements</span></span>  

 <span data-ttu-id="61a83-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61a83-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61a83-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="61a83-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61a83-111">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61a83-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61a83-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61a83-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a83-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="61a83-113">See also</span></span>

- [<span data-ttu-id="61a83-114">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="61a83-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="61a83-115">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="61a83-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
