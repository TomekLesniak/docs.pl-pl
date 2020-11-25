---
title: IMetaDataTables::GetCodedTokenInfo — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: b79ac7f71ec0551336298a90829e1f37e2e30b20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711089"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="b26aa-102">IMetaDataTables::GetCodedTokenInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="b26aa-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>

<span data-ttu-id="b26aa-103">Pobiera wskaźnik do tablicy tokenów skojarzonych z określonym indeksem wiersza.</span><span class="sxs-lookup"><span data-stu-id="b26aa-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b26aa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b26aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b26aa-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b26aa-105">Parameters</span></span>  

 `ixCdTkn`  
 <span data-ttu-id="b26aa-106">podczas Rodzaj zakodowanego tokenu do zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="b26aa-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b26aa-107">określoną Wskaźnik do długości `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="b26aa-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="b26aa-108">określoną Wskaźnik do wskaźnika do tablicy zawierającej listę zwracanych tokenów.</span><span class="sxs-lookup"><span data-stu-id="b26aa-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="b26aa-109">określoną Wskaźnik do wskaźnika do nazwy tokenu w `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="b26aa-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b26aa-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b26aa-110">Requirements</span></span>  

 <span data-ttu-id="b26aa-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b26aa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b26aa-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b26aa-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b26aa-113">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b26aa-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b26aa-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b26aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26aa-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b26aa-115">See also</span></span>

- [<span data-ttu-id="b26aa-116">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b26aa-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b26aa-117">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b26aa-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
