---
title: ICorDebugModule3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
ms.openlocfilehash: 543a1a3c79b6cf3eb799da5844f35286dfa91940
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709560"
---
# <a name="icordebugmodule3-interface"></a>ICorDebugModule3 — Interfejs

Tworzy czytnik symbolu dla modułu dynamicznego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[ICorDebugModule3::CreateReaderForInMemorySymbols — Metoda](icordebugmodule3-createreaderforinmemorysymbols-method.md)|Tworzy czytnik symboli (zazwyczaj [interfejs ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md)) dla modułu dynamicznego.|  
  
## <a name="remarks"></a>Uwagi  

 Ten interfejs logicznie rozszerza interfejsy "ICorDebugModule" i "ICorDebugModule2".  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:** 4,5, 4, 3,5 SP1
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugRemoteTarget — Interfejs](icordebugremotetarget-interface.md)
- [ICorDebug — Interfejs](icordebug-interface.md)

- [Debugowanie — Interfejsy](debugging-interfaces.md)
