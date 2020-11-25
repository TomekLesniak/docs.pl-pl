---
title: ISymUnmanagedScope — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725888"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope — Interfejs

Reprezentuje zakres leksykalny w ramach metody.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetChildren, metoda](isymunmanagedscope-getchildren-method.md)|Pobiera elementy podrzędne tego zakresu.|  
|[GetEndOffset — Metoda](isymunmanagedscope-getendoffset-method.md)|Pobiera przesunięcie końca dla tego zakresu.|  
|[GetLocalCount, metoda](isymunmanagedscope-getlocalcount-method.md)|Pobiera liczbę zmiennych lokalnych zdefiniowanych w tym zakresie.|  
|[GetLocals, metoda](isymunmanagedscope-getlocals-method.md)|Pobiera zmienne lokalne zdefiniowane w tym zakresie.|  
|[GetMethod, metoda](isymunmanagedscope-getmethod-method.md)|Pobiera metodę, która zawiera ten zakres.|  
|[GetNamespaces, metoda](isymunmanagedscope-getnamespaces-method.md)|Pobiera przestrzenie nazw, które są używane w tym zakresie.|  
|[GetParent, metoda](isymunmanagedscope-getparent-method.md)|Pobiera zakres nadrzędny tego zakresu.|  
|[GetStartOffset, metoda](isymunmanagedscope-getstartoffset-method.md)|Pobiera przesunięcie początku dla tego zakresu.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2 — Interfejs](isymunmanagedscope2-interface.md)
