---
title: ISymUnmanagedBinder3 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727318"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3 — Interfejs

Rozszerza interfejs segregatora symboli. Uzyskaj ten interfejs, wywołując `QueryInterface` obiekt, który implementuje `ISymUnmanagedBinder` interfejs.  
  
> [!IMPORTANT]
> Jest to zagrożenie bezpieczeństwa, aby otworzyć plik bazy danych programu (PDB) z niezaufanego źródła.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetReaderFromCallback, metoda](isymunmanagedbinder3-getreaderfromcallback-method.md)|Zezwala użytkownikowi na implementowanie lub dostarczanie za pośrednictwem wywołania zwrotnego albo `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` uzyskanie informacji o katalogu debugowania z pamięci|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder — Interfejs](isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2 — Interfejs](isymunmanagedbinder2-interface.md)
