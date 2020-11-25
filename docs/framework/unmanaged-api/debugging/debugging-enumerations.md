---
title: Debugowanie — wyliczenia
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: bdd4b60d068677ae2a0874b589294ba220f0d854
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723002"
---
# <a name="debugging-enumerations"></a>Debugowanie — wyliczenia

W tej sekcji opisano niezarządzane wyliczenia używane przez interfejs API debugowania.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [CLR_DEBUGGING_PROCESS_FLAGS — Wyliczenie](clr-debugging-process-flags-enumeration.md)  
 Dostarcza wartości, które są używane przez metodę [ICLRDebugging:: OpenVirtualProcess —](iclrdebugging-openvirtualprocess-method.md) .  
  
 [CLRDataEnumMemoryFlags — Wyliczenie](clrdataenummemoryflags-enumeration.md)  
 Wskazuje, które regiony pamięci są wywoływane przez wywołanie metody [ICLRDataEnumMemoryRegions:: EnumMemoryRegions —](iclrdataenummemoryregions-enummemoryregions-method.md) .  
  
 [COR_PUB_ENUMPROCESS — Wyliczenie](cor-pub-enumprocess-enumeration.md)  
 Identyfikuje typ procesu do wyliczenia.  
  
 [CorDebugBlockingReason — Wyliczenie](cordebugblockingreason-enumeration.md)  
 Określa przyczyny, dla których wątek może zostać zablokowany dla danego obiektu.  
  
 CorDebugChainReason —  
 Wskazuje przyczynę lub przyczyny inicjacji łańcucha wywołań.  
  
 [Wyliczenie CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)  
 Opisuje sposób, w jaki wyeksportowana funkcja wywołuje kod zarządzany.  
  
 [Wyliczenie CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)  
 Opisuje, dlaczego wyeksportowana funkcja wywołuje kod zarządzany.  
  
 CorDebugCreateProcessFlags —  
 Zapewnia dodatkowe opcje debugowania, których można użyć w wywołaniu metody [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .  
  
 [Wyliczenie CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md)  
 Wskazuje typ zdarzenia, którego informacje są dekodowane przez metodę [DecodeEvent](icordebugprocess6-decodeevent-method.md) .  
  
 [Wyliczenie CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)  
 Zawiera dodatkowe informacje na temat zdarzeń debugowania na platformie Windows.  
  
 CorDebugExceptionCallbackType —  
 Wskazuje typ wywołania zwrotnego, które jest wykonywane z [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) zdarzenia.  
  
 [CorDebugExceptionFlags — Wyliczenie](cordebugexceptionflags-enumeration.md)  
 Zawiera dodatkowe informacje o wyjątku.  
  
 CorDebugExceptionUnwindCallbackType —  
 Wskazuje zdarzenie, które jest sygnalizowane przez wywołanie zwrotne w fazie unwind.  
  
 [CorDebugGCType — Wyliczenie](cordebuggctype-enumeration.md)  
 Wskazuje, czy moduł wyrzucania elementów bezużytecznych jest uruchomiony na stacji roboczej lub na serwerze.  
  
 [CorDebugGenerationTypes — Wyliczenie](cordebuggenerationtypes-enumeration.md)  
 Określa generowanie regionu pamięci na zarządzanym stosie.  
  
 CorDebugHandleType —  
 Wskazuje typ dojścia.  
  
 [CorDebugIlToNativeMappingTypes — Wyliczenie](cordebugiltonativemappingtypes-enumeration.md)  
 Wskazuje, czy konkretny zakres instrukcji macierzystych odpowiada specjalnemu regionowi kodu.  
  
 CorDebugIntercept —  
 Wskazuje typy kodu, do którego można wykonać te działania.  
  
 [CorDebugInterfaceVersion — Wyliczenie](cordebuginterfaceversion-enumeration.md)  
 Określa wersję .NET Framework lub wersję .NET Framework, w której został wprowadzony interfejs.  
  
 CorDebugInternalFrameType —  
 Identyfikuje typ ramki stosu.  
  
 [CorDebugJITCompilerFlags — Wyliczenie](cordebugjitcompilerflags-enumeration.md)  
 Zawiera wartości wpływające na zachowanie kompilatora zarządzanego (just-in-Time).  
  
 [CorDebugJITCompilerFlagsDeprecated — Wyliczenie](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Nieaktualne. `CORDEBUG_JIT_DEFAULT`Zamiast tego użyj elementu członkowskiego wyliczenia [CorDebugJITCompilerFlags —](cordebugjitcompilerflags-enumeration.md) .  
  
 CorDebugMappingResult —  
 Zawiera szczegółowe informacje o sposobie uzyskiwania wartości wskaźnika instrukcji (IP).  
  
 [CorDebugMDAFlags — Wyliczenie](cordebugmdaflags-enumeration.md)  
 Określa stan wątku, w którym jest uruchamiany Asystent debugowania zarządzanego (MDA).  
  
 [CorDebugNGenPolicy — Wyliczenie](cordebugngenpolicy-enumeration.md)  
 Zapewnia wartość określającą, czy debuger ładuje obrazy natywne (NGen) z pamięci podręcznej obrazów natywnych.  
  
 [Wyliczenie CorDebugPlatform](cordebugplatform-enumeration.md)  
 Zapewnia wartości platformy docelowej, które są używane przez metodę [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) .  
  
 [Wyliczenie CorDebugRecordFormat](cordebugrecordformat-enumeration.md)  
 Opisuje format danych w tablicy bajtów, który zawiera informacje na temat natywnego zdarzenia debugowania wyjątku.  
  
 CorDebugRegister —  
 Określa rejestry skojarzone z daną architekturą procesora.  
  
 [CorDebugSetContextFlag — Wyliczenie](cordebugsetcontextflag-enumeration.md)  
 Wskazuje, czy kontekst pochodzi z aktywnej ramki (lub liściowej) na stosie czy został obliczony przez odróżnienie od innej ramki.  
  
 [Wyliczenie CorDebugStateChange](cordebugstatechange-enumeration.md)  
 Opisuje ilość danych buforowanych, które muszą zostać odrzucone na podstawie zmian w procesie.  
  
 CorDebugStepReason —  
 Wskazuje wynik pojedynczego kroku.  
  
 CorDebugThreadState —  
 Określa stan wątku do debugowania.  
  
 \>CorDebugUnmappedStop —  
 Określa typ niezamapowanego kodu, który może wyzwolić zatrzymanie w wykonaniu kodu przez stepper.  
  
 CorDebugUserState —  
 Wskazuje stan użytkownika wątku.  
  
 [CorGCReferenceType — Wyliczenie](corgcreferencetype-enumeration.md)  
 Określa źródło obiektu, które ma zostać pobrane jako elementy bezużyteczne.  
  
 [Wyliczenie ILCodeKind](ilcodekind-enumeration.md)  
 Zawiera wartości, które określają, czy debuger może uzyskać dostęp do zmiennych lokalnych lub kodu dodanego w instrumentacji profilera ReJIT.  
  
 [LoggingLevelEnum — Wyliczenie](logginglevelenum-enumeration.md)  
 Wskazuje poziom ważności komunikatu opisowego, który jest zapisywana w dzienniku zdarzeń, gdy zarządzany wątek rejestruje zdarzenie.  
  
 [LogSwitchCallReason — Wyliczenie](logswitchcallreason-enumeration.md)  
 Wskazuje operację wykonywaną na przełączniku debugowania/śledzenia.  
  
 [VariableLocationType, wyliczenie](variablelocationtype-enumeration.md)  
 Wskazuje typ lokalizacji natywnej zmiennej.  
  
 [Wyliczenie WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md)  
 Zawiera wartości, które określają, czy aktualizacje w pamięci mają być widoczne dla debugera.

 [ClrDataSourceType, Wyliczenie](clrdatasourcetype-enumeration.md) Dostarcza wartości, które są używane przez strukturę CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Sekcje pokrewne  

 [Klasy coclass debugowania](debugging-coclasses.md)  
  
 [Debugowanie — Interfejsy](debugging-interfaces.md)  
  
 [Debugowanie statycznych funkcji globalnych](debugging-global-static-functions.md)  
  
 [Struktury debugowania](debugging-structures.md)
