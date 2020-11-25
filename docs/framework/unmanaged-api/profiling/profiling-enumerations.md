---
title: Profilowanie — Wyliczenia
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 8956a09cf76aa54452e8c020239e650e55d8a0d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701617"
---
# <a name="profiling-enumerations"></a>Profilowanie — Wyliczenia

W tej sekcji opisano niezarządzane wyliczenia, które są używane przez interfejs API profilowania.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [COR_PRF_CLAUSE_TYPE — Wyliczenie](cor-prf-clause-type-enumeration.md)  
 Wskazuje typ klauzuli wyjątku, który został właśnie wprowadzony lub pozostawiony w kodzie.  
  
 [COR_PRF_CODEGEN_FLAGS — Wyliczanie](cor-prf-codegen-flags-enumeration.md)  
 Definiuje flagi generowania kodu, które można ustawić za pomocą metody [ICorProfilerFunctionControl:: SetCodegenFlags —](icorprofilerfunctioncontrol-setcodegenflags-method.md) .  
  
 [COR_PRF_FINALIZER_FLAGS — Wyliczenie](cor-prf-finalizer-flags-enumeration.md)  
 Opisuje finalizator dla obiektu.  
  
 [COR_PRF_GC_GENERATION — Wyliczenie](cor-prf-gc-generation-enumeration.md)  
 Identyfikuje generowanie wyrzucania elementów bezużytecznych.  
  
 [COR_PRF_GC_REASON — Wyliczenie](cor-prf-gc-reason-enumeration.md)  
 Wskazuje przyczynę wyrzucania elementów bezużytecznych.  
  
 [COR_PRF_GC_ROOT_FLAGS — Wyliczenie](cor-prf-gc-root-flags-enumeration.md)  
 Wskazuje właściwości elementu głównego modułu wyrzucania elementów bezużytecznych.  
  
 [COR_PRF_GC_ROOT_KIND — Wyliczenie](cor-prf-gc-root-kind-enumeration.md)  
 Wskazuje rodzaj elementu głównego modułu wyrzucania elementów bezużytecznych, który jest udostępniany przez wywołanie zwrotne [ICorProfilerCallback2:: RootReferences2 —](icorprofilercallback2-rootreferences2-method.md) .  
  
 [Wyliczenie COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)  
 Oferuje flagi oprócz tych, które znajdują się w wyliczeniu [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) , który profiler może określić do metody [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) podczas ładowania.  
  
 [COR_PRF_JIT_CACHE — Wyliczenie](cor-prf-jit-cache-enumeration.md)  
 Wskazuje wynik funkcji wyszukiwania w pamięci podręcznej.  
  
 [COR_PRF_MISC — Wyliczenie](cor-prf-misc-enumeration.md)  
 Zawiera wartości stałe, które określają identyfikatory specjalne.  
  
 [COR_PRF_MODULE_FLAGS — Wyliczenie](cor-prf-module-flags-enumeration.md)  
 Określa właściwości modułu.  
  
 [COR_PRF_MONITOR — Wyliczenie](cor-prf-monitor-enumeration.md)  
 Zawiera wartości, które są używane do określania zachowania, możliwości lub zdarzeń, do których profiler chce subskrybować.  
  
 [COR_PRF_RUNTIME_TYPE — Wyliczenie](cor-prf-runtime-type-enumeration.md)  
 Zawiera wartości wskazujące wersję środowiska uruchomieniowego języka wspólnego.  
  
 [COR_PRF_SNAPSHOT_INFO — Wyliczenie](cor-prf-snapshot-info-enumeration.md)  
 Określa ilość danych, które mają zostać przekazane z migawki stosu w każdym wywołaniu `StackSnapshotCallback` funkcji profilera.  
  
 [COR_PRF_STATIC_TYPE — Wyliczenie](cor-prf-static-type-enumeration.md)  
 Wskazuje, czy pole jest statyczne i, jeśli tak, statyczna jakość stosowana do pola.  
  
 [COR_PRF_SUSPEND_REASON — Wyliczenie](cor-prf-suspend-reason-enumeration.md)  
 Wskazuje przyczynę wstrzymania środowiska uruchomieniowego.  
  
 [COR_PRF_TRANSITION_REASON — Wyliczenie](cor-prf-transition-reason-enumeration.md)  
 Wskazuje przyczynę przejścia z zarządzanego do kodu niezarządzanego lub odwrotnie.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Omówienie profilowania](profiling-overview.md)  
  
 [Interfejsy profilowania](profiling-interfaces.md)  
  
 [Profilowanie statycznych funkcji globalnych](profiling-global-static-functions.md)  
  
 [Profiling — Struktury](profiling-structures.md)
