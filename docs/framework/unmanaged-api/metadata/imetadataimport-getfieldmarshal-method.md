---
title: IMetaDataImport::GetFieldMarshal — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: 35f73135dbeea1c79d15e0a9e9367c5d533487ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676867"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="fe272-102">IMetaDataImport::GetFieldMarshal — Metoda</span><span class="sxs-lookup"><span data-stu-id="fe272-102">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="fe272-103">Pobiera wskaźnik do natywnego, niezarządzanego typu pola reprezentowanego przez określony token metadanych pola.</span><span class="sxs-lookup"><span data-stu-id="fe272-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe272-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fe272-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe272-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fe272-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="fe272-106">podczas Token metadanych, który reprezentuje pole, aby uzyskać informacje dotyczące organizowania międzyoperacyjnego.</span><span class="sxs-lookup"><span data-stu-id="fe272-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="fe272-107">określoną Wskaźnik do sygnatury metadanych typu natywnego pola.</span><span class="sxs-lookup"><span data-stu-id="fe272-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="fe272-108">określoną Rozmiar w bajtach `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="fe272-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe272-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fe272-109">Requirements</span></span>  

 <span data-ttu-id="fe272-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe272-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe272-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe272-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe272-112">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe272-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe272-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe272-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe272-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fe272-114">See also</span></span>

- [<span data-ttu-id="fe272-115">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fe272-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fe272-116">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fe272-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
