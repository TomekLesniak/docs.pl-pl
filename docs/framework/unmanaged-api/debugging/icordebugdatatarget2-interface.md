---
title: Interfejs ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: aa1db39b564b987fb8d0f79d529f5af59b7e4c02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713756"
---
# <a name="icordebugdatatarget2-interface"></a>Interfejs ICorDebugDataTarget2

Logicznie rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CreateVirtualUnwinder, metoda](icordebugdatatarget2-createvirtualunwinder-method.md)|Tworzy nowy wątek unwiatrer, który zaczyna odwracać od kontekstu początkowego (co nie musi być elementem liścia wątku).|  
|[EnumerateThreadIDs, metoda](icordebugdatatarget2-enumeratethreadids-method.md)|Zwraca listę aktywnych identyfikatorów wątków.|  
|[GetImageFromPointer, metoda](icordebugdatatarget2-getimagefrompointer-method.md)|Zwraca adres podstawowy i rozmiar modułu z adresu w tym module.|  
|[GetImageLocation, metoda](icordebugdatatarget2-getimagelocation-method.md)|Zwraca ścieżkę modułu z adresu podstawowego modułu.|  
|[GetSymbolProviderForImage, metoda](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Zwraca dostawcę symboli dla modułu z adresu podstawowego tego modułu.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs jest dostępny tylko dla .NET Native. W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
