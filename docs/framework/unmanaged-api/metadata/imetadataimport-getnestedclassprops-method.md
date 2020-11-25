---
title: IMetaDataImport::GetNestedClassProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 8c0496c34c43a71ec4f51ba66b3bb18790023a2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722300"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="b0e93-102">IMetaDataImport::GetNestedClassProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="b0e93-102">IMetaDataImport::GetNestedClassProps Method</span></span>

<span data-ttu-id="b0e93-103">Pobiera token TypeDef dla elementu nadrzędnego <xref:System.Type> określonego typu zagnieżdżonego.</span><span class="sxs-lookup"><span data-stu-id="b0e93-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e93-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b0e93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0e93-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b0e93-105">Parameters</span></span>  

 `tdNestedClass`  
 <span data-ttu-id="b0e93-106">podczas Token TypeDef reprezentujący <xref:System.Type> zwraca token klasy nadrzędnej dla.</span><span class="sxs-lookup"><span data-stu-id="b0e93-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="b0e93-107">określoną Wskaźnik do tokenu TypeDef dla <xref:System.Type> , który `tdNestedClass` jest zagnieżdżony w.</span><span class="sxs-lookup"><span data-stu-id="b0e93-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0e93-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b0e93-108">Requirements</span></span>  

 <span data-ttu-id="b0e93-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0e93-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0e93-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b0e93-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0e93-111">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0e93-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0e93-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e93-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e93-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b0e93-113">See also</span></span>

- [<span data-ttu-id="b0e93-114">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b0e93-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b0e93-115">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b0e93-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
