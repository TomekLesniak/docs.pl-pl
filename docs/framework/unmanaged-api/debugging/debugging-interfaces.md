---
title: Debugowanie — Interfejsy
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: a3dd81ceaab2ba467d4c8ca091c1c2219040a273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676299"
---
# <a name="debugging-interfaces"></a>Debugowanie — Interfejsy

W tej sekcji opisano niezarządzane interfejsy obsługujące debugowanie programu wykonywanego w środowisku uruchomieniowym języka wspólnego (CLR).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [ICLRDataEnumMemoryRegions, interfejs](iclrdataenummemoryregions-interface.md)\
 Zapewnia metodę pozwalającą wyliczyć obszary pamięci, które są określone przez obiekty wywołujące.  
  
 [ICLRDataEnumMemoryRegionsCallback, interfejs](iclrdataenummemoryregionscallback-interface.md)\
 Udostępnia metodę wywołania zwrotnego dla programu w `EnumMemoryRegions` celu zgłaszania do debugera, wynik próby wyliczenia określonego regionu pamięci.  
  
 [ICLRDataTarget, interfejs](iclrdatatarget-interface.md)\
 Zapewnia metody interakcji z obiektem docelowym procesu CLR.  
  
 [ICLRDataTarget2, interfejs](iclrdatatarget2-interface.md)\
 Podklasa `ICLRDataTarget` , która jest używana przez warstwę usług dostępu do danych do manipulowania regionami pamięci wirtualnej w procesie docelowym.  
  
 [ICLRDataTarget3, interfejs](iclrdatatarget3-interface.md)\
 Podklasa elementu [ICLRDataTarget2](iclrdatatarget2-interface.md) , która zapewnia dostęp do informacji o wyjątku.  
  
 [ICLRDebugging, interfejs](iclrdebugging-interface.md)\
 Zapewnia metody obsługujące ładowanie i wyładowanie modułów do debugowania.  
  
 [ICLRDebuggingLibraryProvider, interfejs](iclrdebugginglibraryprovider-interface.md)\
 Obejmuje metodę [metody ProvideLibrary —](iclrdebugginglibraryprovider-providelibrary-method.md) , która pobiera interfejs wywołania zwrotnego dostawcy biblioteki, który umożliwia zlokalizowanie i załadowanie bibliotek debugowania specyficznych dla wersji środowiska uruchomieniowego języka wspólnego na żądanie.  
  
 [ICLRMetadataLocator, interfejs](iclrmetadatalocator-interface.md)\
 Interfejs używany przez warstwę usług dostępu do danych do lokalizowania metadane zestawów w procesie docelowym.  
  
 [ICorDebug, interfejs](icordebug-interface.md)\
 Dostarcza metody, które umożliwiają programistom debugowanie aplikacji w środowisku CLR.  
  
 [ICorDebugAppDomain, interfejs](icordebugappdomain-interface.md)\
 Dostarcza metody do debugowania domen aplikacji.  
  
 [ICorDebugAppDomain2, interfejs](icordebugappdomain2-interface.md)\
 Dostarcza metody do pracy z tablicami, wskaźnikami, wskaźnikami funkcji i typami ByRef. Ten interfejs jest rozszerzeniem `ICorDebugAppDomain` interfejsu.  
  
 [ICorDebugAppDomain3, interfejs](icordebugappdomain3-interface.md)\
 Zapewnia metody do pracy z typami środowisko wykonawcze systemu Windows w domenie aplikacji. Ten interfejs jest rozszerzeniem `ICorDebugAppDomain` `ICorDebugAppDomain2` interfejsów i.  
  
 [ICorDebugAppDomain4, interfejs](icordebugappdomain4-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugAppDomain](icordebugappdomain-interface.md) w celu uzyskania obiektu zarządzanego z przywywoływanej otoki com.  
  
 [ICorDebugAppDomainEnum, interfejs](icordebugappdomainenum-interface.md)\
 Zapewnia metodę, która zwraca określoną liczbę wartości, `ICorDebugAppDomain` Zaczynając od następnej lokalizacji w wyliczeniu.  
  
 [ICorDebugArrayValue, interfejs](icordebugarrayvalue-interface.md)\
 Podklasa `ICorDebugHeapValue` reprezentująca tablicę jednowymiarową lub wielowymiarową.  
  
 [ICorDebugAssembly, interfejs](icordebugassembly-interface.md)\
 Reprezentuje zestaw.  
  
 [ICorDebugAssembly2, interfejs](icordebugassembly2-interface.md)\
 Reprezentuje zestaw. Ten interfejs jest rozszerzeniem `ICorDebugAssembly` interfejsu.  
  
 [ICorDebugAssembly3, interfejs](icordebugassembly3-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugAssembly](icordebugassembly-interface.md) w celu zapewnienia obsługi zestawów kontenerów i zawartych w nich zestawów. **Dostępne tylko .NET Native.**  
  
 [ICorDebugAssemblyEnum, interfejs](icordebugassemblyenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugAssembly` tablice.  
  
 [ICorDebugBlockingObjectEnum, interfejs](icordebugblockingobjectenum-interface.md)\
 Dostarcza moduł wyliczający listę struktur [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 [ICorDebugBoxValue, interfejs](icordebugboxvalue-interface.md)\
 Podklasa `ICorDebugHeapValue` reprezentująca obiekt klasy wartości w ramce.  
  
 [ICorDebugBreakpoint, interfejs](icordebugbreakpoint-interface.md)\
 Reprezentuje punkt przerwania w funkcji lub punkt obserwacji wartości.  
  
 [ICorDebugBreakpointEnum, interfejs](icordebugbreakpointenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugBreakpoint` tablice.  
  
 [ICorDebugChain, interfejs](icordebugchain-interface.md)\
 Reprezentuje segment stosu wywołań fizycznych lub logicznych.  
  
 [ICorDebugChainEnum, interfejs](icordebugchainenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugChain` tablice.  
  
 [ICorDebugClass, interfejs](icordebugclass-interface.md)\
 Reprezentuje typ, który może być podstawowy lub złożony (to jest zdefiniowany przez użytkownika). Jeśli typ jest ogólny, `ICorDebugClass` reprezentuje typ ogólny bez wystąpień.  
  
 [ICorDebugClass2, interfejs](icordebugclass2-interface.md)\
 Reprezentuje klasę generyczną lub klasę z parametrem metody typu <xref:System.Type> . Ten interfejs rozszerza `ICorDebugClass` .  
  
 [ICorDebugCode, interfejs](icordebugcode-interface1.md)\
 Reprezentuje segment kodu języka pośredniego firmy Microsoft (MSIL) lub kodu natywnego.  
  
 [ICorDebugCode2, interfejs](icordebugcode2-interface.md)\
 Dostarcza metody, które zwiększają możliwości programu `ICorDebugCode` .  
  
 [ICorDebugCode3, interfejs](icordebugcode3-interface.md)\
 Zapewnia metodę, która rozszerza [ICorDebugCode](icordebugcode-interface1.md) i [ICorDebugCode2](icordebugcode2-interface.md) , aby zapewnić informacje o zarządzanej wartości zwracanej.  
  
 [ICorDebugCode4, interfejs](icordebugcode4-interface.md)\
 Zapewnia metodę, która umożliwia debugerowi Wyliczenie zmiennych lokalnych i argumentów w funkcji.  
  
 [ICorDebugCodeEnum, interfejs](icordebugcodeenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugCode` tablice.  
  
 [ICorDebugComObjectValue, interfejs](icordebugcomobjectvalue-interface.md)\
 Dostarcza metody pobierania obiektów interfejsu w pamięci podręcznej.  
  
 [ICorDebugContext —, interfejs](icordebugcontext-interface.md)\
 Reprezentuje obiekt kontekstu. Ten Interfejs nie został jeszcze implementowany.  
  
 [ICorDebugController, interfejs](icordebugcontroller-interface.md)\
 Reprezentuje zakres, albo <xref:System.Diagnostics.Process> lub <xref:System.AppDomain> , w którym można kontrolować kontekst wykonywania kodu.  
  
 [ICorDebugDataTarget, interfejs](icordebugdatatarget-interface.md)\
 Dostarcza interfejs wywołania zwrotnego, który zapewnia dostęp do konkretnego procesu docelowego.  
  
 [Metoda ICorDebugDataTarget2, interfejs](icordebugdatatarget2-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) . **Dostępne tylko .NET Native.**  
  
 [ICorDebugDataTarget3, interfejs](icordebugdatatarget3-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) w celu dostarczenia informacji o załadowanych modułach. **Dostępne tylko .NET Native.**  
  
 [ICorDebugDebugEvent, interfejs](icordebugdebugevent-interface.md)\
 Definiuje interfejs podstawowy, z którego `ICorDebug` pochodzą wszystkie zdarzenia debugowania. **Dostępne tylko .NET Native.**  
  
 [ICorDebugEditAndContinueErrorInfo, interfejs](icordebugeditandcontinueerrorinfo-interface.md)\
 Nieaktualne. Nie używaj tego interfejsu.  
  
 [ICorDebugEditAndContinueSnapshot, interfejs](icordebugeditandcontinuesnapshot-interface.md)\
 Nieaktualne. Nie używaj tego interfejsu.  
  
 [ICorDebugEnum, interfejs](icordebugenum-interface1.md)\
 Służy jako abstrakcyjny interfejs podstawowy do debugowania modułów wyliczających.  
  
 [ICorDebugErrorInfoEnum, interfejs](icordebugerrorinfoenum-interface.md)\
 Nieaktualne. Nie używaj tego interfejsu.  
  
 [ICorDebugEval, interfejs](icordebugeval-interface.md)\
 Dostarcza metody umożliwiające debugerowi wykonywanie kodu w kontekście debugowanego kodu.  
  
 [ICorDebugEval2, interfejs](icordebugeval2-interface.md)\
 Rozszerza `ICorDebugEval` , aby zapewnić obsługę typów ogólnych.  
  
 [ICorDebugExceptionDebugEvent, interfejs](icordebugexceptiondebugevent-interface.md)\
 Rozszerza interfejs [ICorDebugDebugEvent](icordebugdebugevent-interface.md) w celu obsługi zdarzeń wyjątków. **Dostępne tylko .NET Native.**  
  
 [ICorDebugExceptionObjectCallStackEnum, interfejs](icordebugexceptionobjectcallstackenum-interface.md)\
 Dostarcza moduł wyliczający informacje stosu wywołań, który jest wbudowany w obiekt wyjątku.  
  
 [ICorDebugExceptionObjectValue, interfejs](icordebugexceptionobjectvalue-interface.md)\
 Rozszerza interfejs [ICorDebugObjectValue](icordebugobjectvalue-interface.md) w celu udostępnienia informacji o śledzeniu stosu z obiektu wyjątku zarządzanego.  
  
 [ICorDebugFrame, interfejs](icordebugframe-interface.md)\
 Reprezentuje ramkę na bieżącym stosie.  
  
 [ICorDebugFrameEnum, interfejs](icordebugframeenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugFrame` tablice.  
  
 [ICorDebugFunction, interfejs](icordebugfunction-interface1.md)\
 Reprezentuje zarządzaną funkcję lub metodę.  
  
 [ICorDebugFunction2, interfejs](icordebugfunction2-interface.md)\
 Rozszerzenie logicznie rozszerza `ICorDebugFunction` , aby zapewnić obsługę tylko mój kod debugowania krok po kroku.  
  
 [ICorDebugFunction3, interfejs](icordebugfunction3-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugFunction](icordebugfunction-interface1.md) w celu zapewnienia dostępu do kodu z żądania ReJIT.  
  
 [ICorDebugFunctionBreakpoint, interfejs](icordebugfunctionbreakpoint-interface.md)\
 Rozszerza `ICorDebugBreakpoint` do obsługi punktów przerwania w funkcjach.  
  
 [ICorDebugGCReferenceEnum, interfejs](icordebuggcreferenceenum-interface.md)\
 Dostarcza moduł wyliczający dla obiektów, które zostaną usunięte jako elementy bezużyteczne.  
  
 [ICorDebugGenericValue, interfejs](icordebuggenericvalue-interface.md)\
 Podklasa `ICorDebugValue` , która ma zastosowanie do wszystkich wartości. Ten interfejs zapewnia metody Get i Set dla wartości.  
  
 [ICorDebugGuidToTypeEnum, interfejs](icordebugguidtotypeenum-interface.md)\
 Dostarcza moduł wyliczający dla obiektu, który mapuje identyfikatory GUID i odpowiadające im `ICorDebugType` obiekty.  
  
 [ICorDebugHandleValue, interfejs](icordebughandlevalue-interface.md)\
 Podklasa `ICorDebugReferenceValue` reprezentująca wartość odniesienia, do której debuger utworzył dojście do wyrzucania elementów bezużytecznych.  
  
 [ICorDebugHeapEnum, interfejs](icordebugheapenum-interface.md)\
 Dostarcza moduł wyliczający dla obiektów na zarządzanej stercie.  
  
 [ICorDebugHeapSegmentEnum, interfejs](icordebugheapsegmentenum-interface.md)\
 Zawiera moduł wyliczający dla obszarów pamięci zarządzanej sterty.  
  
 [ICorDebugHeapValue, interfejs](icordebugheapvalue-interface.md)\
 Podklasa `ICorDebugValue` reprezentująca obiekt, który został zebrany przez moduł wyrzucania elementów bezużytecznych CLR.  
  
 [ICorDebugHeapValue2, interfejs](icordebugheapvalue2-interface1.md)\
 Rozszerzenie `ICorDebugHeapValue` , które zapewnia obsługę uchwytów środowiska uruchomieniowego.  
  
 [ICorDebugHeapValue3, interfejs](icordebugheapvalue3-interface.md)\
 Udostępnia właściwości blokady monitora obiektów.  
  
 [ICorDebugILCode, interfejs](icordebugilcode-interface.md)\
 Reprezentuje segment kodu języka pośredniego (IL).  
  
 [ICorDebugILCode2, interfejs](icordebugilcode2-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugILCode](icordebugilcode-interface.md) w celu zapewnienia metod, które zwracają token dla sygnatury zmiennej lokalnej funkcji, i mapuje przesunięcia języka pośredniego (IL) narzędzia profilera do oryginalnej metody do przesunięcia Il.  
  
 [ICorDebugILFrame, interfejs](icordebugilframe-interface.md)\
 Reprezentuje ramkę stosu kodu MSIL.  
  
 [ICorDebugILFrame2, interfejs](icordebugilframe2-interface.md)\
 Logiczne rozszerzenie `ICorDebugILFrame` .  
  
 [ICorDebugILFrame3, interfejs](icordebugilframe3-interface.md)\
 Dostarcza metodę, która hermetyzuje wartość zwracaną przez funkcję.  
  
 [Metoda ICorDebugILFrame4, interfejs](icordebugilframe4-interface.md)\
 Zapewnia metody umożliwiające dostęp do zmiennych lokalnych i kodu w ramce stosu kodu języka pośredniego (IL). Parametr określa, czy debuger ma dostęp do zmiennych i kodu dodanych w Instrumentacji ReJIT profilera.  
  
 [ICorDebugInstanceFieldSymbol, interfejs](icordebuginstancefieldsymbol-interface.md)\
 Przedstawia informacje o symbolu debugowania dla pola wystąpienia. **Dostępne tylko .NET Native.**  
  
 [ICorDebugInternalFrame, interfejs](icordebuginternalframe-interface.md)\
 Identyfikuje typy ramek dla debugera.  
  
 [ICorDebugInternalFrame2, interfejs](icordebuginternalframe2-interface.md)\
 Zawiera informacje o ramkach wewnętrznych, łącznie z adresem stosu i pozycją w odniesieniu do obiektów [ICorDebugFrame](icordebugframe-interface.md) .  
  
 [ICorDebugLoadedModule, interfejs](icordebugloadedmodule-interface.md)\
 Zawiera informacje o załadowanym module. **Dostępne tylko .NET Native.**  
  
 [ICorDebugManagedCallback, interfejs](icordebugmanagedcallback-interface.md)\
 Dostarcza metody do przetwarzania wywołań zwrotnych debugera.  
  
 [ICorDebugManagedCallback2, interfejs](icordebugmanagedcallback2-interface.md)\
 Dostarcza metody umożliwiające obsługę wyjątków debugera i obsługujące asystentów zarządzanego debugowania (MDA). `ICorDebugManagedCallback2` jest logicznym rozszerzeniem `ICorDebugManagedCallback` .  
  
 [ICorDebugManagedCallback3, interfejs](icordebugmanagedcallback3-interface.md)\
 Dostarcza metodę wywołania zwrotnego, która wskazuje, że zgłoszono powiadomienie włączenia niestandardowego debugera.  
  
 [ICorDebugMDA, interfejs](icordebugmda-interface.md)\
 Reprezentuje komunikat asystenta zarządzanego debugowania (MDA).  
  
 [ICorDebugMemoryBuffer, interfejs](icordebugmemorybuffer-interface.md)\
 Reprezentuje bufor w pamięci. **Dostępne tylko .NET Native.**  
  
 [ICorDebugMergedAssemblyRecord, interfejs](icordebugmergedassemblyrecord-interface.md)\
 Zawiera informacje o scalonym zestawie. **Dostępne tylko .NET Native.**  
  
 [ICorDebugMetaDataLocator, interfejs](icordebugmetadatalocator-interface.md)\
 Dostarcza informacje o metadanych do debugera.  
  
 [ICorDebugModule, interfejs](icordebugmodule-interface.md)\
 Reprezentuje moduł CLR, który jest albo plikiem wykonywalnym lub biblioteką DLL.  
  
 [ICorDebugModule2, interfejs](icordebugmodule2-interface.md)\
 Służy jako rozszerzenie logiczne do `ICorDebugModule` .  
  
 [ICorDebugModule3, interfejs](icordebugmodule3-interface.md)\
 Tworzy czytnik symbolu dla modułu dynamicznego.  
  
 [ICorDebugModuleBreakpoint, interfejs](icordebugmodulebreakpoint-interface.md)\
 Rozszerza `ICorDebugBreakpoint` , aby zapewnić dostęp do określonych modułów.  
  
 [ICorDebugModuleDebugEvent, interfejs](icordebugmoduledebugevent-interface.md)\
 Rozszerza interfejs [ICorDebugDebugEvent](icordebugdebugevent-interface.md) w celu obsługi zdarzeń na poziomie modułu. **Dostępne tylko .NET Native.**  
  
 [ICorDebugModuleEnum, interfejs](icordebugmoduleenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugModule` tablice.  
  
 [ICorDebugMutableDataTarget, interfejs](icordebugmutabledatatarget-interface.md)\
 Rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) w celu obsługi modyfikowalnych obiektów docelowych danych.  
  
 [ICorDebugNativeFrame, interfejs](icordebugnativeframe-interface.md)\
 Wyspecjalizowana implementacja `ICorDebugFrame` używana dla ramek natywnych.  
  
 [ICorDebugNativeFrame2, interfejs](icordebugnativeframe2-interface.md)\
 Dostarcza metody testowania relacji podrzędnych i nadrzędnych ramek.  
  
 [ICorDebugObjectEnum, interfejs](icordebugobjectenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza tablice obiektów według ich względnych adresów wirtualnych (RVA).  
  
 [ICorDebugObjectValue, interfejs](icordebugobjectvalue-interface.md)\
 Podklasa `ICorDebugValue` reprezentująca wartość, która zawiera obiekt.  
  
 [ICorDebugObjectValue2, interfejs](icordebugobjectvalue2-interface.md)\
 Rozszerza `ICorDebugObjectValue` do obsługi dziedziczenia i zastąpień.  
  
 [ICorDebugProcess, interfejs](icordebugprocess-interface.md)\
 Reprezentuje proces, który wykonuje kod zarządzany.  
  
 [ICorDebugProcess2, interfejs](icordebugprocess2-interface1.md)\
 Logiczne rozszerzenie `ICorDebugProcess` .  
  
 [ICorDebugProcess3, interfejs](icordebugprocess3-interface.md)\
 Steruje niestandardowymi powiadomieniami debugera.

 [ICorDebugProcess4, interfejs](icordebugprocess4-interface.md)\
 Zapewnia obsługę kontroli wykonywania poza procesem.
  
 [ICorDebugProcess5, interfejs](icordebugprocess5-interface.md)\
 Rozszerza interfejs [ICorDebugProcess](icordebugprocess-interface.md) w celu obsługi dostępu do zarządzanej sterty, zapewnia informacje o wyrzucaniu elementów bezużytecznych obiektów zarządzanych i określa, czy debuger ładuje obrazy z lokalnej pamięci podręcznej obrazów natywnych aplikacji.  
  
 [Metoda ICorDebugProcess6, interfejs](icordebugprocess6-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugProcess](icordebugprocess-interface.md) w celu włączenia takich funkcji, jak dekodowanie zdarzeń debugowania zarządzanego, które są kodowane w natywnych zdarzeniach debugowania wyjątków i dzielenia modułu wirtualnego. **Dostępne tylko .NET Native.**  
  
 [ICorDebugProcess7, interfejs](icordebugprocess7-interface.md)\
 Zapewnia metodę, która umożliwia skonfigurowanie debugera do obsługi aktualizacji metadanych w pamięci w procesie docelowym.  
  
 [ICorDebugProcess8, interfejs](icordebugprocess8-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugProcess](icordebugprocess-interface.md) w celu włączenia lub wyłączenia niektórych typów wywołań zwrotnych wyjątków [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
 [ICorDebugProcessEnum, interfejs](icordebugprocessenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugProcess` tablice.  
  
 [ICorDebugReferenceValue, interfejs](icordebugreferencevalue-interface.md)\
 Podklasa `ICorDebugValue` , która obsługuje typy odwołań.  
  
 [ICorDebugRegisterSet, interfejs](icordebugregisterset-interface.md)\
 Reprezentuje zestaw rejestrów dostępnych na komputerze, który aktualnie wykonuje kod.  
  
 [ICorDebugRegisterSet2, interfejs](icordebugregisterset2-interface.md)\
 Rozszerza możliwości programu `ICorDebugRegisterSet` dla platform sprzętowych, które mają ponad 64 rejestrów.  
  
 [ICorDebugRemote, interfejs](icordebugremote-interface.md)\
 Zapewnia zdalnemu procesowi docelowemu możliwość uruchamiania lub dołączenia zarządzanych debugerów.  
  
 [ICorDebugRemoteTarget, interfejs](icordebugremotetarget-interface.md)\
 Dostarcza metody, które umożliwiają debugowania aplikacji opartych na dodatku Silverlight w środowisku CLR.  
  
 [ICorDebugRuntimeUnwindableFrame, interfejs](icordebugruntimeunwindableframe-interface.md)\
 Zapewnia obsługę niezarządzanych metod, które wymagają środowiska uruchomieniowego języka wspólnego (CLR), aby zwolnić ramkę.  
  
 [ICorDebugStackWalk, interfejs](icordebugstackwalk-interface.md)\
 Dostarcza metody pobierania zarządzanych metod, lub ramek, znajdujących się na stosie wątku.  
  
 [ICorDebugStaticFieldSymbol, interfejs](icordebugstaticfieldsymbol-interface.md)\
 Przedstawia informacje o symbolu debugowania dla pola statycznego. **Dostępne tylko .NET Native.**  
  
 [ICorDebugStepper, interfejs](icordebugstepper-interface.md)\
 Reprezentuje krok wykonaniu kodu, który jest realizowany przez debuger; służy jako identyfikator między wydaniem i zakończeniem polecenia i zapewnia sposób anulowania kroku.  
  
 [ICorDebugStepper2, interfejs](icordebugstepper2-interface1.md)\
 Zapewnia obsługę debugowania Tylko mój kod (JMC).  
  
 [ICorDebugStepperEnum, interfejs](icordebugstepperenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugStepper` tablice.  
  
 [ICorDebugStringValue, interfejs](icordebugstringvalue-interface.md)\
 Podklasa `ICorDebugHeapValue` , która ma zastosowanie do wartości ciągu.  
  
 [ICorDebugSymbolProvider, interfejs](icordebugsymbolprovider-interface.md)\
 Dostarcza metody, których można użyć do pobrania informacji o symbolach debugowania. **Dostępne tylko .NET Native.**  
  
 [ICorDebugSymbolProvider2, interfejs](icordebugsymbolprovider2-interface.md)\
 Logicznie rozszerza interfejs [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) w celu pobrania dodatkowych informacji o symbolach debugowania. **Dostępne tylko .NET Native.**  
  
 [ICorDebugThread, interfejs](icordebugthread-interface.md)\
 Reprezentuje wątek w procesie. Okres istnienia `ICorDebugThread` wystąpienia jest taki sam jak okres istnienia wątku, który reprezentuje.  
  
 [ICorDebugThread2, interfejs](icordebugthread2-interface.md)\
 Służy jako rozszerzenie logiczne do `ICorDebugThread` .  
  
 [ICorDebugThread3, interfejs](icordebugthread3-interface.md)\
 Udostępnia punkt wejścia do [ICorDebugStackWalk](icordebugstackwalk-interface.md) i odpowiednich interfejsów.  
  
 [ICorDebugThread4, interfejs](icordebugthread4-interface.md)\
 Dostarcza informacje o blokowaniu wątku.  
  
 [ICorDebugThreadEnum, interfejs](icordebugthreadenum-interface1.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugThread` tablice.  
  
 [ICorDebugType, interfejs](icordebugtype-interface.md)\
 Reprezentuje typ, który może być podstawowy lub złożony (to jest zdefiniowany przez użytkownika). Jeśli typ jest ogólny, `ICorDebugType` reprezentuje typ ogólny wystąpienia.  
  
 [ICorDebugType2, interfejs](icordebugtype2-interface.md)\
 Rozszerza interfejs [ICorDebugType](icordebugtype-interface.md) w celu pobrania identyfikatora typu podstawowego lub złożonego (zdefiniowanego przez użytkownika).  
  
 [ICorDebugTypeEnum, interfejs](icordebugtypeenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugType` tablice.  
  
 [ICorDebugUnmanagedCallback, interfejs](icordebugunmanagedcallback-interface.md)\
 Zapewnia powiadomienie macierzystych zdarzeń, które nie dotyczą bezpośrednio środowiska CLR.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Reprezentuje wartość odczytu lub zapisu w procesie debugowania.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Rozszerza `ICorDebugValue` , aby zapewnić pomoc techniczną `ICorDebugType` .  
  
 [ICorDebugValue3, interfejs](icordebugvalue3-interface.md)\
 Rozszerza interfejsy "ICorDebugValue" i "ICorDebugValue2", aby zapewnić obsługę tablic o rozmiarze większym niż 2 GB.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Rozszerza `ICorDebugBreakpoint` , aby zapewnić dostęp do określonych wartości.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementuje `ICorDebugEnum` metody i wylicza `ICorDebugValue` tablice.  
  
 [ICorDebugVariableHome, interfejs](icordebugvariablehome-interface.md)\
 Reprezentuje zmienną lokalną lub argument funkcji.  
  
 [ICorDebugVariableHomeEnum, interfejs](icordebugvariablehomeenum-interface.md)\
 Dostarcza moduł wyliczający do zmiennych lokalnych i argumentów w funkcji.  
  
 [ICorDebugVariableSymbol, interfejs](icordebugvariablesymbol-interface.md)\
 Pobiera informacje o symbolach debugowania dla zmiennej. **Dostępne tylko .NET Native.**  
  
 [ICorDebugVirtualUnwinder, interfejs](icordebugvirtualunwinder-interface.md)\
 Zapewnia metody pomagające w rozwinięcia stosu. **Dostępne tylko .NET Native.**  
  
 [ICorPublish, interfejs](icorpublish-interface.md)\
 Służy jako ogólny interfejs dla procesów publikowania.  
  
 [ICorPublishAppDomain, interfejs](icorpublishappdomain-interface.md)\
 Reprezentuje i dostarcza informacje dotyczące domeny aplikacji.  
  
 [ICorPublishAppDomainEnum, interfejs](icorpublishappdomainenum-interface.md)\
 Dostarcza metody, które przechodzą kolekcję `ICorPublishAppDomain` obiektów, które aktualnie istnieją w ramach procesu.  
  
 [ICorPublishEnum, interfejs](icorpublishenum-interface.md)\
 Służy jako abstrakcyjna podstawowa do publikowania modułów wyliczających.  
  
 [ICorPublishProcess, interfejs](icorpublishprocess-interface.md)\
 Dostarcza metody, które mają dostęp do informacji dotyczących procesu.  
  
 [ICorPublishProcessEnum, interfejs](icorpublishprocessenum-interface.md)\
 Dostarcza metody, które przechodzą przez kolekcję `ICorPublishProcess` obiektów.  

 [ISOSDacInterface, interfejs](isosdacinterface-interface.md)\
 Zapewnia metody pomocnika do uzyskiwania dostępu do danych `SOS` .

 [IXCLRDataMethodDefinition, interfejs](ixclrdatamethoddefinition-interface.md)\
 Zapewnia metody wykonywania zapytań dotyczących informacji o definicji metody.

 [IXCLRDataMethodInstance, interfejs](ixclrdatamethodinstance-interface.md)\
 Zapewnia metody wykonywania zapytań dotyczących informacji o wystąpieniu metody.

 [IXCLRDataModule, interfejs](ixclrdatamodule-interface.md)\
 Zapewnia metody wykonywania zapytania o informacje o załadowanym module.

 [IXCLRDataProcess, interfejs](ixclrdataprocess-interface.md)\
 Dostarcza metody do wykonywania zapytań dotyczących informacji o procesie.
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Klasy coclass debugowania](debugging-coclasses.md)\
 [Debugowanie globalnych funkcji statycznych](debugging-global-static-functions.md)\
 [Wyliczenia debugowania](debugging-enumerations.md)\
 [Struktury debugowania](debugging-structures.md)\
