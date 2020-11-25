---
title: ICorDebugInstanceFieldSymbol, interfejs
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 4ef0f7a46acf7e9df732d630c9eb22044e09d658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724900"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>ICorDebugInstanceFieldSymbol, interfejs

Przedstawia informacje o symbolu debugowania dla pola wystąpienia.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetName — Metoda](icordebuginstancefieldsymbol-getname-method.md)|Pobiera nazwę pola wystąpienia.|  
|[GetOffset — Metoda](icordebuginstancefieldsymbol-getoffset-method.md)|Pobiera przesunięcie w bajtach tego pola wystąpienia w jego klasie nadrzędnej.|  
|[GetSize — Metoda](icordebuginstancefieldsymbol-getsize-method.md)|Pobiera rozmiar w bajtach pola wystąpienia.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugInstanceFieldSymbol`Interfejs jest używany do pobierania informacji o symbolach debugowania dla pola wystąpienia.  
  
> [!NOTE]
> Ten interfejs jest dostępny tylko dla .NET Native. W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugStaticFieldSymbol, interfejs](icordebugstaticfieldsymbol-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
