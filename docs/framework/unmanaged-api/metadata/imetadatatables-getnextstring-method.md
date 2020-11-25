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
# <a name="imetadatatablesgetnextstring-method"></a>IMetaDataTables::GetNextString — Metoda

Pobiera indeks następnego ciągu w bieżącej kolumnie tabeli.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ixString`  
 podczas Wartość indeksu z kolumny tabeli ciągów.  
  
 `pNext`  
 określoną Wskaźnik do indeksu następnego ciągu w kolumnie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataTables — Interfejs](imetadatatables-interface.md)
- [IMetaDataTables2 — Interfejs](imetadatatables2-interface.md)
