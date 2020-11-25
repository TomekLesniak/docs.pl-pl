---
title: Profilowanie statycznych funkcji globalnych
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 1b0ad42e6b34e99212e112f6a594b0a36b6715e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723080"
---
# <a name="profiling-global-static-functions"></a>Profilowanie statycznych funkcji globalnych

W tej sekcji opisano niezarządzane funkcje API, które są używane przez interfejs API profilowania.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
## <a name="net-framework-version-1-profiling-functions"></a>Funkcje profilowania .NET Framework w wersji 1  

 [FunctionEnter — Funkcja](functionenter-function.md)  
 Powiadamia profiler, że sterowanie jest przesyłane do funkcji. Przestarzałe w .NET Framework 2,0.  
  
 [FunctionLeave — Funkcja](functionleave-function.md)  
 Powiadamia profiler, że funkcja ma zwrócić do obiektu wywołującego. Przestarzałe w .NET Framework 2,0.  
  
 [FunctionTailcall — Funkcja](functiontailcall-function.md)  
 Powiadamia profiler, że aktualnie wykonywana funkcja ma wykonać wywołanie tail do innej funkcji. Przestarzałe w .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Funkcje profilowania .NET Framework w wersji 2  

 [FunctionIDMapper — Funkcja](functionidmapper-function.md)  
 Powiadamia program profilujący, że dany identyfikator funkcji może zostać ponownie zmapowany na alternatywny identyfikator, który ma być używany w wywołaniach zwrotnych [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)i [FunctionTailcall2](functiontailcall2-function.md) dla tej funkcji. Umożliwia również profilerowi wskazanie, czy chce otrzymywać wywołania zwrotne dla tej funkcji  
  
 [FunctionEnter2 — Funkcja](functionenter2-function.md)  
 Powiadamia profiler, że sterowanie jest przesyłane do funkcji i zawiera informacje na temat ramki stosu i argumentów funkcji. Przestarzałe w .NET Framework 4.  
  
 [FunctionLeave2 — Funkcja](functionleave2-function.md)  
 Powiadamia program profilujący, że funkcja ma zwrócić do obiektu wywołującego i zawiera informacje na temat ramki stosu i wartości zwracanej przez funkcję. Przestarzałe w .NET Framework 4.  
  
 [FunctionTailcall2 — Funkcja](functiontailcall2-function.md)  
 Powiadamia profiler, że aktualnie wykonywana funkcja ma wykonać wywołanie tail do innej funkcji i zawiera informacje na temat ramki stosu. Przestarzałe w .NET Framework 4.  
  
 [StackSnapshotCallback — Funkcja](stacksnapshotcallback-function.md)  
 Zapewnia profilerowi informacje o każdej zarządzanej ramce i każdym uruchomieniu niezarządzanych ramek na stosie podczas przechodzenia stosu, który jest inicjowany przez [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="net-framework-version-4-profiling-functions"></a>Funkcje profilowania .NET Framework w wersji 4  

 [FunctionIDMapper2 — Funkcja](functionidmapper2-function.md)  
 Powiadamia program profilujący, że dany identyfikator funkcji może zostać ponownie zmapowany na alternatywny identyfikator, który ma być używany w wywołaniach zwrotnych [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)i [FunctionTailcall3](functiontailcall3-function.md), lub[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)i [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) dla tej funkcji. Umożliwia również profilerowi określenie, czy chce otrzymywać wywołania zwrotne dla tej funkcji.  
  
 `FunctionIDMapper2` rozszerza funkcję [FunctionIDMapper](functionidmapper-function.md) z `clientData` parametrem, który może być używany przez program do rozróżniania między środowiskami uruchomieniowymi.  
  
 [FunctionEnter3 — Funkcja](functionenter3-function.md)  
 Powiadamia profiler, że sterowanie jest przesyłane do funkcji.  
  
 [FunctionEnter3WithInfo — Funkcja](functionenter3withinfo-function.md)  
 Powiadamia program profilujący, że formant jest przesyłany do funkcji i udostępnia dojście, które może być przekazane do [ICorProfilerInfo3:: GetFunctionEnter3Info —](icorprofilerinfo3-getfunctionenter3info-method.md) w celu pobrania ramki stosu i argumentów funkcji.  
  
 [FunctionLeave3 — Funkcja](functionleave3-function.md)  
 Powiadamia profiler, że formant jest zwracany przez funkcję.  
  
 [FunctionLeave3WithInfo — Funkcja](functionleave3withinfo-function.md)  
 Powiadamia profiler, że formant jest zwracany przez funkcję i udostępnia dojście, które można przesłać do [ICorProfilerInfo3:: GetFunctionLeave3Info —](icorprofilerinfo3-getfunctionleave3info-method.md) , aby pobrać ramkę stosu i wartość zwracaną.  
  
 [FunctionTailcall3 — Funkcja](functiontailcall3-function.md)  
 Powiadamia profiler, że aktualnie wykonywana funkcja ma wykonać wywołanie tail do innej funkcji.  
  
 [FunctionTailcall3WithInfo — Funkcja](functiontailcall3withinfo-function.md)  
 Powiadamia program profilujący, że aktualnie wykonywana funkcja ma wykonać wywołanie tail do innej funkcji i udostępnia dojście, które może zostać przesłane do [ICorProfilerInfo3:: GetFunctionTailcall3Info —](icorprofilerinfo3-getfunctiontailcall3info-method.md) w celu pobrania ramki stosu.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Omówienie profilowania](profiling-overview.md)  
  
 [Interfejsy profilowania](profiling-interfaces.md)  
  
 [Profilowanie — Wyliczenia](profiling-enumerations.md)  
  
 [Profiling — Struktury](profiling-structures.md)
