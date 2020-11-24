---
title: IMetaDataTables::GetTableInfo — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 65943ac169106a95feaff7d44017444e65764b60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672529"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="3f8c6-102">IMetaDataTables::GetTableInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="3f8c6-102">IMetaDataTables::GetTableInfo Method</span></span>

<span data-ttu-id="3f8c6-103">Pobiera nazwę, rozmiar wiersza, liczbę wierszy, liczbę kolumn i indeks kolumny klucza w określonej tabeli.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f8c6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3f8c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f8c6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3f8c6-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="3f8c6-106">podczas Identyfikator tabeli, której właściwości mają zostać zwrócone.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="3f8c6-107">określoną Wskaźnik do rozmiaru, w bajtach, wiersza tabeli.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="3f8c6-108">określoną Wskaźnik do liczby wierszy w tabeli.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="3f8c6-109">określoną Wskaźnik do liczby kolumn w tabeli.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="3f8c6-110">określoną Wskaźnik do indeksu kolumny klucza lub-1, jeśli tabela nie ma kolumny klucza.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="3f8c6-111">określoną Wskaźnik do wskaźnika do nazwy tabeli.</span><span class="sxs-lookup"><span data-stu-id="3f8c6-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f8c6-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3f8c6-112">Requirements</span></span>  

 <span data-ttu-id="3f8c6-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f8c6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f8c6-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3f8c6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f8c6-115">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f8c6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f8c6-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f8c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8c6-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3f8c6-117">See also</span></span>

- [<span data-ttu-id="3f8c6-118">IMetaDataTables — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f8c6-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="3f8c6-119">IMetaDataTables2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f8c6-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
