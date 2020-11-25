---
title: ClrCreateManagedInstance — Funkcja
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 9aed79138499f1aa7b6fa3a28ad4505edd51b041
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731775"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance — Funkcja

Tworzy wystąpienie określonego typu zarządzanego.  
  
 Ta funkcja jest przestarzała w .NET Framework 4. Przy użyciu aktywacji COM można utworzyć wystąpienie typu zarządzanego lub użyć hostingu (zobacz [Interfejsy hostingu środowiska CLR dodane w .NET Framework 4 i 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pTypeName`  
 podczas Wskaźnik do nazwy żądanego typu wystąpienia.  
  
 `riid`  
 podczas `IID` Typ żądanego wystąpienia.  
  
 `ppObject`  
 określoną Wskaźnik do wskaźnika do wystąpienia typu zarządzanego, który zażądał obiekt wywołujący.  
  
## <a name="remarks"></a>Uwagi  

 Środowisko uruchomieniowe języka wspólnego powinno być już załadowane do procesu. Na przykład można go załadować przy użyciu wywołania funkcji [CorBindToRuntimeEx](corbindtoruntimeex-function.md) przed `ClrCreateManagedInstance` wywołaniem funkcji. Jeśli środowisko uruchomieniowe nie zostało załadowane, program `ClrCreateManagedInstance` najpierw podejmie próbę załadowania 1.0.3705 środowiska uruchomieniowego. Jeśli to się nie powiedzie, zostanie podjęta próba załadowania najnowszej wersji środowiska uruchomieniowego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
- [Hosting](index.md)
