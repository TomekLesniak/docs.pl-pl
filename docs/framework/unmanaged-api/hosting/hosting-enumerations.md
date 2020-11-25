---
title: Hosting — Wyliczenia
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
ms.openlocfilehash: 907b1343ddbfa28b97ac2210e28b99cd38aa6fd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721832"
---
# <a name="hosting-enumerations"></a>Hosting — Wyliczenia

W tej sekcji opisano niezarządzane wyliczenia używane przez interfejs API hostingu.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [CLSID_RESOLUTION_FLAGS — Wyliczenie](clsid-resolution-flags-enumeration.md)  
 Zawiera wartości wskazujące sposób, w jaki środowisko uruchomieniowe języka wspólnego (CLR) powinno rozwiązać problem `CLSID` .  
  
 [COR_GC_STAT_TYPES — Wyliczenie](cor-gc-stat-types-enumeration.md)  
 Określa statystyki, które mają być rejestrowane w celu wyrzucania elementów bezużytecznych.  
  
 [COR_GC_THREAD_STATS_TYPES — Wyliczenie](cor-gc-thread-stats-types-enumeration.md)  
 Wskazuje statystykę wyrzucania elementów bezużytecznych wątku.  
  
 [EApiCategories — Wyliczenie](eapicategories-enumeration.md)  
 Opisuje kategorie możliwości, które host może blokować z uruchamiania w częściowo zaufanym kodzie.  
  
 [EBindPolicyLevels — Wyliczenie](ebindpolicylevels-enumeration.md)  
 Zawiera flagi określające poziom, na którym należy zastosować lub zmodyfikować zasady zestawu.  
  
 [ECLRAssemblyIdentityFlags — Wyliczenie](eclrassemblyidentityflags-enumeration.md)  
 Wskazuje typ tożsamości zestawu.  
  
 [EClrEvent — Wyliczenie](eclrevent-enumeration.md)  
 Opisuje zdarzenia środowiska CLR, dla których host może rejestrować wywołania zwrotne.  
  
 [EClrFailure — Wyliczenie](eclrfailure-enumeration.md)  
 Opisuje zestaw błędów, dla których host może ustawiać akcje zasad.  
  
 [EClrOperation — Wyliczenie](eclroperation-enumeration.md)  
 Opisuje zestaw operacji, dla których host może stosować akcje zasad.  
  
 [EClrUnhandledException — Wyliczenie](eclrunhandledexception-enumeration.md)  
 Opisuje dostępne opcje zarządzania wyjątkami, które nie są obsługiwane w kodzie użytkownika.  
  
 [EContextType — Wyliczenie](econtexttype-enumeration.md)  
 Opisuje kontekst zabezpieczeń aktualnie wykonywanego wątku.  
  
 [ECustomDumpFlavor — Wyliczenie](ecustomdumpflavor-enumeration.md)  
 Zawiera wartości wskazujące, które elementy mają być uwzględnione w niestandardowym podzestawie zrzutu sterty podczas raportowania błędów.  
  
 [ECustomDumpItemKind — Wyliczenie](ecustomdumpitemkind-enumeration.md)  
 Zarezerwowane dla przyszłego rozszerzenia struktury [struktury CustomDumpItem —](customdumpitem-structure.md) .  
  
 [EHostApplicationPolicy — Wyliczenie](ehostapplicationpolicy-enumeration.md)  
 Wskazuje, jak zmodyfikować obiekt interfejsu [interfejsu IHostAssemblyManager](ihostassemblymanager-interface.md) . To wyliczenie jest przestarzałe.  
  
 [EHostBindingPolicyModifyFlags — Wyliczenie](ehostbindingpolicymodifyflags-enumeration.md)  
 Umożliwia hostowi określenie typu przekierowania, który ma być wykonywany przez środowisko CLR podczas stosowania modyfikacji zasad z zestawu źródłowego do zestawu docelowego.  
  
 [EInitializeNewDomainFlags — Wyliczenie](einitializenewdomainflags-enumeration.md)  
 Umożliwia hostowi zapewnienie środowiska uruchomieniowego z informacjami o inicjalizacji domeny aplikacji.  
  
 [EMemoryAvailable — Wyliczenie](ememoryavailable-enumeration.md)  
 Zawiera wartości wskazujące ilość wolnej pamięci fizycznej na komputerze.  
  
 [EMemoryCriticalLevel — Wyliczenie](ememorycriticallevel-enumeration.md)  
 Zawiera wartości wskazujące wpływ błędu w przypadku żądania określonego przydziału pamięci, ale nie można go spełnić.  
  
 [EPolicyAction — Wyliczenie](epolicyaction-enumeration.md)  
 Opisuje akcje zasad, które host może ustawić dla operacji opisanych przez [Wyliczenie EClrOperation —](eclroperation-enumeration.md) i błędy opisane przez [Wyliczenie EClrFailure —](eclrfailure-enumeration.md).  
  
 [ESymbolReadingPolicy — Wyliczenie](esymbolreadingpolicy-enumeration.md)  
 Zawiera wartości, które ustawiają zasady odczytujące pliki bazy danych (PDB) programu.  
  
 [ETaskType — Wyliczenie](etasktype-enumeration.md)  
 Zawiera wartości wskazujące rodzaj zadania reprezentowanego przez [interfejs ICLRTask](iclrtask-interface.md) lub interfejs [interfejsu IHostTask](ihosttask-interface.md) .  
  
 [HOST_TYPE — Wyliczenie](host-type-enumeration.md)  
 Zawiera wartości określające typ hosta, który uruchamia aplikację.  
  
 [MALLOC_TYPE — Wyliczenie](malloc-type-enumeration.md)  
 Zawiera wartości określające charakterystyki przydzielenia pamięci.  
  
 [METAHOST_CONFIG_FLAGS — Wyliczenie](metahost-config-flags-enumeration.md)  
 Opisuje możliwe flagi zwrócone w `pdwConfigFlags` parametrze metody [ICLRMetaHostPolicy:: GetRequestedRuntime —](iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
 [METAHOST_POLICY_FLAGS — Wyliczenie](metahost-policy-flags-enumeration.md)  
 Program udostępnia zasady powiązań, które są wspólne dla większości hostów środowiska uruchomieniowego.  
  
 [RUNTIME_INFO_FLAGS — Wyliczenie](runtime-info-flags-enumeration.md)  
 Zawiera wartości wskazujące, jakie informacje o środowisku CLR należy zwrócić.  
  
 [StackOverflowType — Wyliczenie](stackoverflowtype-enumeration.md)  
 Zawiera wartości wskazujące podstawową przyczynę zdarzenia przepełnienia stosu.  
  
 [STARTUP_FLAGS — Wyliczenie](startup-flags-enumeration.md)  
 Zawiera wartości, które wskazują zachowanie uruchamiania środowiska CLR.  
  
 [ValidatorFlags — Wyliczenie](validatorflags-enumeration.md)  
 Zawiera wartości wskazujące typ walidacji, który powinien zostać wykonany w wywołaniu [metody walidacji](iclrvalidator-validate-method.md).  
  
 [WAIT_OPTION — Wyliczenie](wait-option-enumeration.md)  
 Wskazuje akcję, którą host powinien wykonać, jeśli operacja zażądała bloków CLR.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Współklasy hostingu](hosting-coclasses.md)  
  
 [Hosting — Interfejsy](hosting-interfaces.md)  
  
 [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)  
  
 [Hosting — Struktury](hosting-structures.md)
