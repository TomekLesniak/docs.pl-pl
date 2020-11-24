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
# <a name="imetadatatablesgettableinfo-method"></a>IMetaDataTables::GetTableInfo — Metoda

Pobiera nazwę, rozmiar wiersza, liczbę wierszy, liczbę kolumn i indeks kolumny klucza w określonej tabeli.  
  
## <a name="syntax"></a>Składnia  
  
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
  
## <a name="parameters"></a>Parametry  

 `ixTbl`  
 podczas Identyfikator tabeli, której właściwości mają zostać zwrócone.  
  
 `pcbRow`  
 określoną Wskaźnik do rozmiaru, w bajtach, wiersza tabeli.  
  
 `pcRows`  
 określoną Wskaźnik do liczby wierszy w tabeli.  
  
 `pcCols`  
 określoną Wskaźnik do liczby kolumn w tabeli.  
  
 `piKey`  
 określoną Wskaźnik do indeksu kolumny klucza lub-1, jeśli tabela nie ma kolumny klucza.  
  
 `ppName`  
 określoną Wskaźnik do wskaźnika do nazwy tabeli.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataTables — Interfejs](imetadatatables-interface.md)
- [IMetaDataTables2 — Interfejs](imetadatatables2-interface.md)
