---
title: ISymUnmanagedBinder2 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: c5a43f6c277f582f9f14cefe5bfba6f5300c09d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727357"
---
# <a name="isymunmanagedbinder2-interface"></a>ISymUnmanagedBinder2 — Interfejs

Reprezentuje spinacz symboliczny dla kodu niezarządzanego i rozszerza interfejs [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .  
  
> [!IMPORTANT]
> Jest to zagrożenie bezpieczeństwa, aby otworzyć plik bazy danych programu (PDB) z niezaufanego źródła.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetReaderForFile2, metoda](isymunmanagedbinder2-getreaderforfile2-method.md)|Podanym interfejsem metadanych i nazwą pliku zwraca poprawny interfejs [ISymUnmanagedReader](isymunmanagedreader-interface.md) , który odczytuje symbole debugowania skojarzone z modułem. Zapewnia bardziej rozległe wyszukiwanie niż Metoda [ISymUnmanagedBinder:: GetReaderForFile —](isymunmanagedbinder-getreaderforfile-method.md) .|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder — Interfejs](isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder3 — Interfejs](isymunmanagedbinder3-interface.md)
