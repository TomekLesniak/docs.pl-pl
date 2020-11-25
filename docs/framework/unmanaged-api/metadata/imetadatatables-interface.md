---
title: IMetaDataTables — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 073e73f082416308b893974471e39cbf5243d01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708858"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables — Interfejs

Zapewnia metody przechowywania i pobierania informacji o metadanych w tabelach.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetBlob, metoda](imetadatatables-getblob-method.md)|Pobiera wskaźnik do dużego obiektu binarnego (BLOB) w określonym indeksie kolumny.|  
|[GetBlobHeapSize, metoda](imetadatatables-getblobheapsize-method.md)|Pobiera rozmiar (w bajtach) sterty obiektu BLOB.|  
|[GetCodedTokenInfo, metoda](imetadatatables-getcodedtokeninfo-method.md)|Pobiera wskaźnik do tablicy tokenów skojarzonych z określonym indeksem wiersza.|  
|[GetColumn, metoda](imetadatatables-getcolumn-method.md)|Pobiera wskaźnik do wartości zawartych w kolumnie w określonym indeksie kolumny w tabeli w określonym indeksie tabeli.|  
|[GetColumnInfo, metoda](imetadatatables-getcolumninfo-method.md)|Pobiera dane dotyczące określonej kolumny w określonej tabeli.|  
|[GetGuid, metoda](imetadatatables-getguid-method.md)|Pobiera identyfikator GUID z wiersza o określonym indeksie.|  
|[GetGuidHeapSize, metoda](imetadatatables-getguidheapsize-method.md)|Pobiera rozmiar sterty identyfikatora GUID w bajtach.|  
|[GetNextBlob, metoda](imetadatatables-getnextblob-method.md)|Pobiera indeks następnego obiektu BLOB w tabeli.|  
|[GetNextGuid, metoda](imetadatatables-getnextguid-method.md)|Pobiera indeks następnej wartości identyfikatora GUID z bieżącej kolumny tabeli.|  
|[GetNextString, metoda](imetadatatables-getnextstring-method.md)|Pobiera indeks następnego ciągu w bieżącej kolumnie tabeli.|  
|[GetNextUserString, metoda](imetadatatables-getnextuserstring-method.md)|Pobiera indeks wiersza, który zawiera następny zakodowany ciąg w bieżącej kolumnie tabeli.|  
|[GetNumTables, metoda](imetadatatables-getnumtables-method.md)|Pobiera liczbę tabel w zakresie bieżącego `IMetaDataTables` wystąpienia.|  
|[GetRow, metoda](imetadatatables-getrow-method.md)|Pobiera wiersz o określonym indeksie wiersza w tabeli w określonym indeksie tabeli.|  
|[GetString — Metoda](imetadatatables-getstring-method.md)|Pobiera ciąg o określonym indeksie z kolumny tabeli w bieżącym zakresie odwołania.|  
|[GetStringHeapSize, metoda](imetadatatables-getstringheapsize-method.md)|Pobiera rozmiar sterty ciągu w bajtach.|  
|[GetTableIndex, metoda](imetadatatables-gettableindex-method.md)|Pobiera indeks tabeli, do której odwołuje się określony token.|  
|[GetTableInfo, metoda](imetadatatables-gettableinfo-method.md)|Pobiera nazwę, rozmiar wiersza, liczbę wierszy, liczbę kolumn i indeks kolumny klucza tabeli w określonym indeksie tabeli.|  
|[GetUserString, metoda](imetadatatables-getuserstring-method.md)|Pobiera zakodowany ciąg o określonym indeksie w kolumnie ciąg w bieżącym zakresie.|  
|[GetUserStringHeapSize, metoda](imetadatatables-getuserstringheapsize-method.md)|Pobiera rozmiar sterty ciągu użytkownika w bajtach.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataTables2 — Interfejs](imetadatatables2-interface.md)
