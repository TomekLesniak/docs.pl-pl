---
title: ICorDebugSymbolProvider2, interfejs
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: 3bef03e9e85224058bc17e1f0ce8746e98aa30f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688344"
---
# <a name="icordebugsymbolprovider2-interface"></a>ICorDebugSymbolProvider2, interfejs

Logicznie rozszerza interfejs [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) w celu pobrania dodatkowych informacji o symbolach debugowania.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetFrameProps, metoda](icordebugsymbolprovider2-getframeprops-method.md)|Zwraca metodę rozpoczynającą względny adres wirtualny metody i ramkę nadrzędną, w której znajduje się adres wirtualny względem kodu.|  
|[GetGenericDictionaryInfo, metoda](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|Pobiera mapę ogólnego słownika.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs jest dostępny tylko dla .NET Native. W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
