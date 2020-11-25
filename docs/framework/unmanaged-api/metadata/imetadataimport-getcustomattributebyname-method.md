---
title: IMetaDataImport::GetCustomAttributeByName — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: 3eb894aaf8ccdc99ea23ddf946f39f3ec71773d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711211"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="3fdc0-102">IMetaDataImport::GetCustomAttributeByName — Metoda</span><span class="sxs-lookup"><span data-stu-id="3fdc0-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>

<span data-ttu-id="3fdc0-103">Pobiera atrybut niestandardowy, uwzględniając jego nazwę i właściciela.</span><span class="sxs-lookup"><span data-stu-id="3fdc0-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdc0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3fdc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fdc0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3fdc0-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="3fdc0-106">podczas Token metadanych reprezentujący obiekt będący właścicielem atrybutu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="3fdc0-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="3fdc0-107">podczas Nazwa atrybutu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="3fdc0-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="3fdc0-108">określoną Wskaźnik do tablicy danych, która jest wartością atrybutu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="3fdc0-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="3fdc0-109">określoną Rozmiar w bajtach danych zwróconych w \* `ppData` .</span><span class="sxs-lookup"><span data-stu-id="3fdc0-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fdc0-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3fdc0-110">Remarks</span></span>  

 <span data-ttu-id="3fdc0-111">Istnieje możliwość zdefiniowania wielu atrybutów niestandardowych dla tego samego właściciela; mogą nawet mieć taką samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="3fdc0-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="3fdc0-112">Jednakże `GetCustomAttributeByName` zwraca tylko jedno wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="3fdc0-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="3fdc0-113">( `GetCustomAttributeByName` zwraca pierwsze wystąpienie, które napotka.) Aby znaleźć wszystkie wystąpienia atrybutu niestandardowego, wywołaj metodę [IMetaDataImport:: EnumCustomAttributes —](imetadataimport-enumcustomattributes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3fdc0-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdc0-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3fdc0-114">Requirements</span></span>  

 <span data-ttu-id="3fdc0-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fdc0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fdc0-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3fdc0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fdc0-117">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fdc0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3fdc0-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdc0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdc0-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3fdc0-119">See also</span></span>

- [<span data-ttu-id="3fdc0-120">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3fdc0-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3fdc0-121">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3fdc0-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
