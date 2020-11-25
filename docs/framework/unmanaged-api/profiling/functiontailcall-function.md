---
title: FunctionTailcall — Funkcja
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: 02bc6f4bbb6754bd160fe2694f27563908f3a759
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722222"
---
# <a name="functiontailcall-function"></a>FunctionTailcall — Funkcja

Powiadamia profiler, że aktualnie wykonywana funkcja ma wykonać wywołanie tail do innej funkcji.  
  
> [!NOTE]
> `FunctionTailcall`Funkcja jest przestarzała w .NET Framework w wersji 2,0. Będzie ona nadal działała, ale nastąpi spadek wydajności. Zamiast tego użyj funkcji [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parametry

- `funcID`

  \[in) identyfikator aktualnie wykonywanej funkcji, która ma na celu wykonanie wywołania tail.

## <a name="remarks"></a>Uwagi  

 Funkcja Target wywołania tail będzie używać bieżącej ramki stosu i zwróci się bezpośrednio do obiektu wywołującego funkcji, która wykonał wywołanie tail. Oznacza to, że wywołanie zwrotne [FunctionLeave —](functionleave-function.md) nie zostanie wygenerowane dla funkcji, która jest elementem docelowym wywołania tail.  
  
 `FunctionTailcall`Funkcja jest wywołaniem zwrotnym, należy ją zaimplementować. Implementacja musi używać `__declspec` `naked` atrybutu klasy magazynu ().  
  
 Aparat wykonywania nie zapisuje żadnych rejestrów przed wywołaniem tej funkcji.  
  
- We wpisie należy zapisać wszystkie używane rejestry, w tym te w jednostce zmiennoprzecinkowej (FPU).  
  
- Po zakończeniu należy przywrócić stos, usuwanie wyłączyć wszystkie parametry, które zostały wypchnięte przez jego obiekt wywołujący.  
  
 Implementacja `FunctionTailcall` nie powinna być blokowana, ponieważ spowoduje opóźnienie wyrzucania elementów bezużytecznych. Implementacja nie powinna podejmować próby wyrzucania elementów bezużytecznych, ponieważ stos może nie znajdować się w stanie przyjaznym do wyrzucania elementów bezużytecznych. W przypadku próby wyrzucania elementów bezużytecznych środowisko uruchomieniowe zostanie zablokowane do momentu `FunctionTailcall` powracania.  
  
 Ponadto `FunctionTailcall` Funkcja nie może wywołać kodu zarządzanego lub w jakikolwiek sposób może spowodować alokację pamięci zarządzanej.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:** 1,1, 1,0  
  
## <a name="see-also"></a>Zobacz także

- [FunctionEnter2 — Funkcja](functionenter2-function.md)
- [FunctionLeave2 — Funkcja](functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2, metoda](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilowanie statycznych funkcji globalnych](profiling-global-static-functions.md)
