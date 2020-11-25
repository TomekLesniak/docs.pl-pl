---
title: ISymUnmanagedWriter4 — Interfejs
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725810"
---
# <a name="isymunmanagedwriter4-interface"></a>ISymUnmanagedWriter4 — Interfejs

Interfejs ISymUnmanagedWriter4.  
  
## <a name="syntax"></a>Składnia  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>Metody  

 Ten interfejs zawiera następujące metody:  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetDebugInfoWithPadding, metoda](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Działa tak samo jak [Metoda GetDebugInfo —](isymunmanagedwriter-getdebuginfo-method.md) , z tą różnicą, że ciąg ścieżki jest dopełniany zerami po zamykającym znaku null, aby dane ciągu miały stały rozmiar `MAX_PATH` . Uzupełnienie jest udzielane tylko wtedy, gdy sama długość ciągu ścieżki jest mniejsza niż `MAX_PATH` .<br /><br /> Ułatwia to pisanie narzędzi, które różnicuje pliki PE.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter3 — Interfejs](isymunmanagedwriter3-interface.md)
