---
title: IMetaDataTables::GetNextString — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: b79dbdd64ac171d1bc4cd30b96ee76b4a853afb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727253"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="92062-102">IMetaDataTables::GetNextString — Metoda</span><span class="sxs-lookup"><span data-stu-id="92062-102">IMetaDataTables::GetNextString Method</span></span>

<span data-ttu-id="92062-103">Pobiera indeks następnego ciągu w bieżącej kolumnie tabeli.</span><span class="sxs-lookup"><span data-stu-id="92062-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92062-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="92062-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92062-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="92062-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="92062-106">podczas Wartość indeksu z kolumny tabeli ciągów.</span><span class="sxs-lookup"><span data-stu-id="92062-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="92062-107">określoną Wskaźnik do indeksu następnego ciągu w kolumnie.</span><span class="sxs-lookup"><span data-stu-id="92062-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92062-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="92062-108">Requirements</span></span>  

 <span data-ttu-id="92062-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92062-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92062-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="92062-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92062-111">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92062-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92062-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92062-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92062-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="92062-113">See also</span></span>

- [<span data-ttu-id="92062-114">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="92062-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="92062-115">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="92062-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
