---
title: ISymUnmanagedReaderSymbolSearchInfo — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: af4124aed823a0a2475a181efe3fa68e1fae0bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678392"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a>ISymUnmanagedReaderSymbolSearchInfo — Interfejs

Dostarcza metody, które pobierają informacje o wyszukiwaniu symboli. Uzyskaj ten interfejs, wywołując `QueryInterface` obiekt, który implementuje interfejs [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetSymbolSearchInfo, metoda](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|Pobiera informacje o wyszukiwaniu symboli.|  
|[GetSymbolSearchInfoCount, metoda](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|Pobiera liczbę informacji o wyszukiwaniu symboli.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
