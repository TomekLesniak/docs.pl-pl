---
title: ISymUnmanagedWriter2 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 6feb48b7c78dda64ba372e470b83ffb14f21f2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683332"
---
# <a name="isymunmanagedwriter2-interface"></a>ISymUnmanagedWriter2 — Interfejs

Reprezentuje moduł zapisujący symboli i zawiera metody definiowania dokumentów, punktów sekwencji, zakresów leksykalnych i zmiennych. Ten interfejs rozszerza interfejs [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DefineConstant2, metoda](isymunmanagedwriter2-defineconstant2-method.md)|Definiuje nazwę wartości stałej.|  
|[DefineGlobalVariable2, metoda](isymunmanagedwriter2-defineglobalvariable2-method.md)|Definiuje pojedynczą zmienną globalną.|  
|[DefineLocalVariable2, metoda](isymunmanagedwriter2-definelocalvariable2-method.md)|Definiuje pojedynczą zmienną w bieżącym zakresie leksykalnym.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy magazynu symboli diagnostycznych](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter — Interfejs](isymunmanagedwriter-interface.md)
- [ISymUnmanagedWriter3 — Interfejs](isymunmanagedwriter3-interface.md)
