---
title: ISymUnmanagedBinder — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
ms.openlocfilehash: 554e59484f00626726f7f024c69e93a5e6647130
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727383"
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder — Interfejs

Reprezentuje spinacz symboliczny dla niezarządzanego kodu.  
  
> [!IMPORTANT]
> Jest to zagrożenie bezpieczeństwa, aby otworzyć plik bazy danych programu (PDB) z niezaufanego źródła.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetReaderForFile, metoda](isymunmanagedbinder-getreaderforfile-method.md)|W przypadku interfejsu metadanych i nazwy pliku funkcja zwraca poprawną strukturę [ISymUnmanagedReader](isymunmanagedreader-interface.md) , która odczyta symbole debugowania skojarzone z modułem.|  
|[GetReaderFromStream, metoda](isymunmanagedbinder-getreaderfromstream-method.md)|Podano interfejs metadanych i strumień zawierający magazyn symboli, zwracając poprawną strukturę [ISymUnmanagedReader](isymunmanagedreader-interface.md) , która odczyta symbole debugowania z danego magazynu symboli.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder2 — Interfejs](isymunmanagedbinder2-interface.md)
- [ISymUnmanagedBinder3 — Interfejs](isymunmanagedbinder3-interface.md)
