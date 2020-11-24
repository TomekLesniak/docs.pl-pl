---
title: IMetaDataTables::GetString — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 8ecaa003084064be1071a85aa726c38d773ec0b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672581"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="fd692-102">IMetaDataTables::GetString — Metoda</span><span class="sxs-lookup"><span data-stu-id="fd692-102">IMetaDataTables::GetString Method</span></span>

<span data-ttu-id="fd692-103">Pobiera ciąg o określonym indeksie z kolumny tabeli w bieżącym zakresie odwołania.</span><span class="sxs-lookup"><span data-stu-id="fd692-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd692-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fd692-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd692-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fd692-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="fd692-106">podczas Indeks, od którego należy zacząć wyszukiwanie następnej wartości.</span><span class="sxs-lookup"><span data-stu-id="fd692-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="fd692-107">określoną Wskaźnik do wskaźnika do zwracanej wartości ciągu.</span><span class="sxs-lookup"><span data-stu-id="fd692-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd692-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fd692-108">Requirements</span></span>  

 <span data-ttu-id="fd692-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd692-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd692-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd692-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd692-111">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd692-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd692-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd692-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd692-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fd692-113">See also</span></span>

- [<span data-ttu-id="fd692-114">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd692-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="fd692-115">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd692-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
