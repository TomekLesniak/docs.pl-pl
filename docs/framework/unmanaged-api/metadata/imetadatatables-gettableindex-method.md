---
title: IMetaDataTables::GetTableIndex — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: 52d70a76bdf8380d320edb6e8188443070a36b1b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672562"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="78411-102">IMetaDataTables::GetTableIndex — Metoda</span><span class="sxs-lookup"><span data-stu-id="78411-102">IMetaDataTables::GetTableIndex Method</span></span>

<span data-ttu-id="78411-103">Pobiera indeks tabeli, do której odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="78411-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78411-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="78411-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78411-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="78411-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="78411-106">podczas Token, który odwołuje się do tabeli.</span><span class="sxs-lookup"><span data-stu-id="78411-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="78411-107">określoną Wskaźnik do zwracanego indeksu dla tabeli, do której się odwołuje.</span><span class="sxs-lookup"><span data-stu-id="78411-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78411-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78411-108">Remarks</span></span>  

 <span data-ttu-id="78411-109">Nie zalecamy użycia tej metody, ponieważ nie zwracają one spójnych wyników.</span><span class="sxs-lookup"><span data-stu-id="78411-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="78411-110">Aby uzyskać informacje na temat tabeli GUID, zobacz dokumentację Common Language Infrastructure (CLI), szczególnie "partycja II: definicja metadanych i semantyka".</span><span class="sxs-lookup"><span data-stu-id="78411-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="78411-111">Dokumentacja jest dostępna w trybie online; Zobacz [ECMA C# i Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) i [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="78411-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78411-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="78411-112">Requirements</span></span>  

 <span data-ttu-id="78411-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78411-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78411-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="78411-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78411-115">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78411-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78411-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78411-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78411-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="78411-117">See also</span></span>

- [<span data-ttu-id="78411-118">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="78411-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="78411-119">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="78411-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
