---
title: IMetaDataTables::GetRow — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 01c4c1734aa0701f787a2b73787e9e4781901d42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672659"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="ee608-102">IMetaDataTables::GetRow — Metoda</span><span class="sxs-lookup"><span data-stu-id="ee608-102">IMetaDataTables::GetRow Method</span></span>

<span data-ttu-id="ee608-103">Pobiera wiersz o określonym indeksie wiersza w tabeli w określonym indeksie tabeli.</span><span class="sxs-lookup"><span data-stu-id="ee608-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee608-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ee608-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee608-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ee608-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="ee608-106">podczas Indeks tabeli, z której zostanie pobrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ee608-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="ee608-107">podczas Indeks wiersza do pobrania.</span><span class="sxs-lookup"><span data-stu-id="ee608-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="ee608-108">określoną Wskaźnik do wskaźnika do wiersza.</span><span class="sxs-lookup"><span data-stu-id="ee608-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee608-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ee608-109">Remarks</span></span>  

  <span data-ttu-id="ee608-110">Nie zalecamy użycia tej metody, ponieważ nie zwracają one spójnych wyników.</span><span class="sxs-lookup"><span data-stu-id="ee608-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ee608-111">Aby uzyskać informacje na temat tabeli GUID, zobacz dokumentację Common Language Infrastructure (CLI), szczególnie "partycja II: definicja metadanych i semantyka".</span><span class="sxs-lookup"><span data-stu-id="ee608-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ee608-112">Dokumentacja jest dostępna w trybie online; Zobacz [ECMA C# i Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) i [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ee608-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee608-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ee608-113">Requirements</span></span>  

 <span data-ttu-id="ee608-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee608-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee608-115">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ee608-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee608-116">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee608-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee608-117">**Wersje .NET Framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee608-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee608-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ee608-118">See also</span></span>

- [<span data-ttu-id="ee608-119">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ee608-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ee608-120">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ee608-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
