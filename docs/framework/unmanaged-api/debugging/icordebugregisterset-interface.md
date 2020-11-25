---
title: ICorDebugRegisterSet — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 940810288b72be0d4dfc5366176663c22c369ebb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712381"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet — Interfejs

Reprezentuje zestaw rejestrów dostępnych na komputerze, który aktualnie wykonuje kod.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetRegisters — Metoda](icordebugregisterset-getregisters-method.md)|Pobiera wartość każdego rejestru (na komputerze, który aktualnie wykonuje kod), który jest określony przez maskę bitową.|  
|[GetRegistersAvailable — Metoda](icordebugregisterset-getregistersavailable-method.md)|Pobiera maskę bitową wskazującą, które rejestry w tej `ICorDebugRegisterSet` chwili są dostępne.|  
|[GetThreadContext, metoda](icordebugregisterset-getthreadcontext-method.md)|Pobiera kontekst bieżącego wątku.|  
|[SetRegisters, metoda](icordebugregisterset-setregisters-method.md)|Nie zaimplementowane dla .NET Framework w wersji 2,0.|  
|[SetThreadContext, metoda](icordebugregisterset-setthreadcontext-method.md)|Nie zaimplementowane dla .NET Framework 2,0.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugRegisterSet`Interfejs obsługuje tylko rejestry 32-bitowe. Użyj interfejsu [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) na platformach, takich jak IA-64, które wymagają dodatkowych rejestrów.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [ICorDebugRegisterSet2 — Interfejs](icordebugregisterset2-interface.md)
