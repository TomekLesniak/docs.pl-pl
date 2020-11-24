---
title: IMetaDataImport::EnumPermissionSets — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690528"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="6c323-102">IMetaDataImport::EnumPermissionSets — Metoda</span><span class="sxs-lookup"><span data-stu-id="6c323-102">IMetaDataImport::EnumPermissionSets Method</span></span>

<span data-ttu-id="6c323-103">Wylicza uprawnienia dla obiektów w określonym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="6c323-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c323-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6c323-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c323-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6c323-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="6c323-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="6c323-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6c323-107">Musi ona mieć wartość NULL dla pierwszego wywołania tej metody.</span><span class="sxs-lookup"><span data-stu-id="6c323-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="6c323-108">podczas Token metadanych, który ogranicza zakres wyszukiwania lub wartość NULL, aby przeszukać możliwie najszerszego zakresu.</span><span class="sxs-lookup"><span data-stu-id="6c323-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="6c323-109">podczas Flagi reprezentujące <xref:System.Security.Permissions.SecurityAction> wartości do uwzględnienia w `rPermission` , lub zero, aby zwrócić wszystkie akcje.</span><span class="sxs-lookup"><span data-stu-id="6c323-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="6c323-110">określoną Tablica służąca do przechowywania tokenów uprawnień.</span><span class="sxs-lookup"><span data-stu-id="6c323-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6c323-111">podczas Maksymalny rozmiar `rPermission` tablicy.</span><span class="sxs-lookup"><span data-stu-id="6c323-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6c323-112">określoną Liczba tokenów uprawnień zwróconych w `rPermission` .</span><span class="sxs-lookup"><span data-stu-id="6c323-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c323-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="6c323-113">Return Value</span></span>  
  
|<span data-ttu-id="6c323-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c323-114">HRESULT</span></span>|<span data-ttu-id="6c323-115">Opis</span><span class="sxs-lookup"><span data-stu-id="6c323-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6c323-116">`EnumPermissionSets` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="6c323-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6c323-117">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="6c323-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="6c323-118">W takim przypadku `pcTokens` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="6c323-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c323-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6c323-119">Requirements</span></span>  

 <span data-ttu-id="6c323-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c323-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c323-121">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6c323-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c323-122">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c323-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c323-123">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c323-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c323-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6c323-124">See also</span></span>

- [<span data-ttu-id="6c323-125">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c323-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6c323-126">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c323-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
