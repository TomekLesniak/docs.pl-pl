---
title: IMetaDataEmit::SetPermissionSetProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 4c3e0953d71020ba62ee4ab68aa9e21ea3f0f521
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675038"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="70556-102">IMetaDataEmit::SetPermissionSetProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="70556-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>

<span data-ttu-id="70556-103">Ustawia lub aktualizuje funkcje sygnatury metadanych zestawu uprawnień zdefiniowanego przez poprzednie wywołanie do [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="70556-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70556-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="70556-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70556-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="70556-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="70556-106">podczas Token metadanych, który reprezentuje obiekt, który ma być dekoracyjny.</span><span class="sxs-lookup"><span data-stu-id="70556-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="70556-107">podczas Wartość [CorDeclSecurity —](cordeclsecurity-enumeration.md) , która określa typ zabezpieczenia deklaracyjnego do użycia.</span><span class="sxs-lookup"><span data-stu-id="70556-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="70556-108">podczas Obiekt BLOB uprawnień.</span><span class="sxs-lookup"><span data-stu-id="70556-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="70556-109">podczas Rozmiar, w bajtach, z `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="70556-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="70556-110">określoną `mdPermission` Token metadanych, który reprezentuje zaktualizowane uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="70556-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70556-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70556-111">Requirements</span></span>  

 <span data-ttu-id="70556-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70556-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70556-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="70556-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70556-114">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70556-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70556-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70556-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70556-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70556-116">See also</span></span>

- [<span data-ttu-id="70556-117">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70556-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="70556-118">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70556-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
