---
title: IMetaDataTables::GetUserStringHeapSize — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 048010f00f6581a29c6b1a3150bf5ae8822b5664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672464"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="b4756-102">IMetaDataTables::GetUserStringHeapSize — Metoda</span><span class="sxs-lookup"><span data-stu-id="b4756-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="b4756-103">Pobiera rozmiar sterty ciągu użytkownika w bajtach.</span><span class="sxs-lookup"><span data-stu-id="b4756-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4756-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b4756-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4756-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b4756-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="b4756-106">określoną Wskaźnik do rozmiaru, w bajtach, sterty ciągu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b4756-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4756-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b4756-107">Requirements</span></span>  

 <span data-ttu-id="b4756-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4756-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4756-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b4756-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4756-110">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4756-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4756-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4756-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4756-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b4756-112">See also</span></span>

- [<span data-ttu-id="b4756-113">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b4756-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b4756-114">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b4756-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
