---
title: IMetaDataImport::IsValidToken — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: b4dc1e60f3d29e2671882d1900a1c49e56969601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702865"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="bd1b0-102">IMetaDataImport::IsValidToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="bd1b0-102">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="bd1b0-103">Pobiera wartość wskazującą, czy określony token przechowuje prawidłowe odwołanie do obiektu kodu.</span><span class="sxs-lookup"><span data-stu-id="bd1b0-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1b0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bd1b0-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd1b0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="bd1b0-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="bd1b0-106">podczas Token, aby sprawdzić prawidłowość odwołania.</span><span class="sxs-lookup"><span data-stu-id="bd1b0-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd1b0-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="bd1b0-107">Return Value</span></span>  

 <span data-ttu-id="bd1b0-108">`true` if `tk` jest prawidłowym tokenem metadanych w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="bd1b0-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="bd1b0-109">W przeciwnym razie wartość `false`.</span><span class="sxs-lookup"><span data-stu-id="bd1b0-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1b0-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bd1b0-110">Requirements</span></span>  

 <span data-ttu-id="bd1b0-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd1b0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1b0-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd1b0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd1b0-113">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd1b0-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd1b0-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1b0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1b0-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bd1b0-115">See also</span></span>

- [<span data-ttu-id="bd1b0-116">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="bd1b0-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bd1b0-117">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="bd1b0-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
