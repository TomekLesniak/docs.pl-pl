---
title: IMetaDataImport::GetClassLayout — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711263"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="16715-102">IMetaDataImport::GetClassLayout — Metoda</span><span class="sxs-lookup"><span data-stu-id="16715-102">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="16715-103">Pobiera informacje o układzie dla klasy, do której odwołuje się określony token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="16715-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16715-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="16715-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16715-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="16715-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="16715-106">podczas Token TypeDef dla klasy z układem, który ma zostać zwrócony.</span><span class="sxs-lookup"><span data-stu-id="16715-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="16715-107">określoną Jedna z wartości 1, 2, 4, 8 lub 16 reprezentuje rozmiar pakietu klasy.</span><span class="sxs-lookup"><span data-stu-id="16715-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="16715-108">określoną Tablica wartości [COR_FIELD_OFFSET](cor-field-offset-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="16715-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="16715-109">podczas Maksymalny rozmiar `rFieldOffset` tablicy.</span><span class="sxs-lookup"><span data-stu-id="16715-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="16715-110">określoną Liczba elementów zwróconych w `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="16715-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="16715-111">określoną Rozmiar w bajtach klasy reprezentowanej przez `td` .</span><span class="sxs-lookup"><span data-stu-id="16715-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16715-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="16715-112">Requirements</span></span>  

 <span data-ttu-id="16715-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16715-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16715-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="16715-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16715-115">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16715-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16715-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16715-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16715-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="16715-117">See also</span></span>

- [<span data-ttu-id="16715-118">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="16715-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="16715-119">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="16715-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
