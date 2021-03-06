---
title: Zdarzenia metod ETW
description: Zobacz zdarzenia ETW, które zbierają informacje specyficzne dla metod, takich jak zdarzenia metody CLR, znacznik metody CLR lub zdarzenia verbose języka CLR i MethodJittingStarted.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
ms.openlocfilehash: f48867a0aef417ad0b19a15d78e0c0f01a7c30a1
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474322"
---
# <a name="method-etw-events"></a>Zdarzenia metod ETW

Te zdarzenia zbierają informacje, które są specyficzne dla metod. Ładunek tych zdarzeń jest wymagany do rozpoznawania symboli. Ponadto te zdarzenia zapewniają przydatne informacje, takie jak liczba przypadków wywołania metody.

Wszystkie zdarzenia metody mają poziom "informacyjny (4)". Wszystkie zdarzenia verbose metody mają poziom "verbose (5)".

Wszystkie zdarzenia metod są wywoływane za pomocą słowa `JITKeyword` kluczowego (0x10) lub `NGenKeyword` słowa kluczowego (0x20) w ramach dostawcy środowiska uruchomieniowego, lub `JitRundownKeyword` (0x10) lub `NGENRundownKeyword` (0x20) w ramach dostawcy uwalniania.

## <a name="clr-method-events"></a>Zdarzenia metody CLR

W poniższej tabeli przedstawiono słowo kluczowe i poziom. Aby uzyskać więcej informacji, zobacz [słowa kluczowe i poziomy ETW CLR](clr-etw-keywords-and-levels.md).

|Słowo kluczowe do podniesienia zdarzenia|Poziom|
|-----------------------------------|-----------|
|`JITKeyword`(0x10) dostawca środowiska uruchomieniowego|Informacyjny (4)|
|`NGenKeyword`(0x20) dostawca środowiska uruchomieniowego|Informacyjny (4)|
|`JitRundownKeyword`(0x10) — dostawca uwalniania|Informacyjny (4)|
|`NGENRundownKeyword`(0x20) — dostawca uwalniania|Informacyjny (4)|

W poniższej tabeli przedstawiono informacje o zdarzeniu:

|Zdarzenie|Identyfikator zdarzenia|Opis|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|136|Uruchamiany, gdy metoda jest załadowana w czasie just-in-Time (załadowano JIT) lub obraz NGEN zostanie załadowany. Metody dynamiczne i ogólne nie używają tej wersji do ładowania metod. Pomocników JIT nigdy nie używają tej wersji.|
|`MethodUnLoad_V1`|137|Uruchamiany, gdy moduł jest zwolniony, lub domena aplikacji jest niszczona. Metody dynamiczne nigdy nie używają tej wersji do zwalniania metod.|
|`MethodDCStart_V1`|137|Wylicza metody podczas początkowego uwalniania.|
|`MethodDCEnd_V1`|138|Wylicza metody podczas końcowego uwalniania.|

W poniższej tabeli przedstawiono dane zdarzenia:

|Nazwa pola|Typ danych|Opis|
|----------------|---------------|-----------------|
|MethodID|win: UInt64|Unikatowy identyfikator metody. W przypadku metod pomocniczych JIT jest ustawiony na adres początkowy metody.|
|ModuleID|win: UInt64|Identyfikator modułu, do którego należy ta metoda (0 dla pomocników JIT).|
|MethodStartAddress|win: UInt64|Adres początkowy metody.|
|MethodSize|win: UInt32|Rozmiar metody.|
|MethodToken|win: UInt32|0 w przypadku metod dynamicznych i pomocników JIT.|
|MethodFlags|win: UInt32|0x1: metoda dynamiczna.<br /><br /> 0x2: Metoda ogólna.<br /><br /> 0x4: Metoda kodu skompilowana przez JIT (w przeciwnym razie kod natywnego obrazu NGEN).<br /><br /> 0x8: metoda pomocnika.|
|ClrInstanceID|win: UInt16|Unikatowy identyfikator wystąpienia CLR lub CoreCLR.|

## <a name="clr-method-marker-events"></a>Zdarzenia znacznika metody CLR

Te zdarzenia są wywoływane tylko w ramach dostawcy uwalniania. Oznacza to koniec wyliczenia metody podczas początkowego lub końcowego uwalniania. (Oznacza to, że są wywoływane, gdy `NGENRundownKeyword` `JitRundownKeyword` `LoaderRundownKeyword` `AppDomainResourceManagementRundownKeyword` jest włączone słowo kluczowe,, lub.)

W poniższej tabeli przedstawiono słowo kluczowe i poziom:

|Słowo kluczowe do podniesienia zdarzenia|Poziom|
|-----------------------------------|-----------|
|`AppDomainResourceManagementRundownKeyword`(0x800) — dostawca uwalniania|Informacyjny (4)|
|`JitRundownKeyword`(0x10) — dostawca uwalniania|Informacyjny (4)|
|`NGENRundownKeyword`(0x20) — dostawca uwalniania|Informacyjny (4)|

W poniższej tabeli przedstawiono informacje o zdarzeniu:

|Zdarzenie|Identyfikator zdarzenia|Opis|
|-----------|--------------|----------------|
|`DCStartInit_V1`|147|Wysyłany przed rozpoczęciem wyliczania podczas początkowego uwalniania.|
|`DCStartComplete_V1`|145|Wysyłany na końcu wyliczenia podczas początkowego uwalniania.|
|`DCEndInit_V1`|148|Wysyłany przed rozpoczęciem wyliczania podczas końcowego uwalniania.|
|`DCEndComplete_V1`|146|Wysyłany na końcu wyliczenia podczas końcowego uwalniania.|

W poniższej tabeli przedstawiono dane zdarzenia:

|Nazwa pola|Typ danych|Opis|
|----------------|---------------|-----------------|
|ClrInstanceID|win: UInt16|Unikatowy identyfikator wystąpienia CLR lub CoreCLR.|

## <a name="clr-method-verbose-events"></a>Zdarzenia verbose dla metody CLR

W poniższej tabeli przedstawiono słowo kluczowe i poziom:

|Słowo kluczowe do podniesienia zdarzenia|Poziom|
|-----------------------------------|-----------|
|`JITKeyword`(0x10) dostawca środowiska uruchomieniowego|Verbose (5)|
|`NGenKeyword`(0x20) dostawca środowiska uruchomieniowego|Verbose (5)|
|`JitRundownKeyword`(0x10) — dostawca uwalniania|Verbose (5)|
|`NGENRundownKeyword`(0x20) — dostawca uwalniania|Verbose (5)|

W poniższej tabeli przedstawiono informacje o zdarzeniu:

|Zdarzenie|Identyfikator zdarzenia|Opis|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Uruchamiany, gdy metoda jest załadowana przy użyciu JIT lub jest ładowany obraz NGEN. Metody dynamiczne i ogólne zawsze używają tej wersji do ładowania metod. Pomocników JIT zawsze używają tej wersji.|
|`MethodUnLoadVerbose_V1`|144|Uruchamiany, gdy metoda dynamiczna jest niszczona, moduł jest zwalniany lub domena aplikacji jest niszczona. Metody dynamiczne zawsze używają tej wersji do zwalniania metod.|
|`MethodDCStartVerbose_V1`|141|Wylicza metody podczas początkowego uwalniania.|
|`MethodDCEndVerbose_V1`|142|Wylicza metody podczas końcowego uwalniania.|

W poniższej tabeli przedstawiono dane zdarzenia:

|Nazwa pola|Typ danych|Opis|
|----------------|---------------|-----------------|
|MethodID|win: UInt64|Unikatowy identyfikator metody. Dla metod pomocniczych JIT Ustaw adres początkowy metody.|
|ModuleID|win: UInt64|Identyfikator modułu, do którego należy ta metoda (0 dla pomocników JIT).|
|MethodStartAddress|win: UInt64|Adres początkowy.|
|MethodSize|win: UInt32|Długość metody.|
|MethodToken|win: UInt32|0 w przypadku metod dynamicznych i pomocników JIT.|
|MethodFlags|win: UInt32|0x1: metoda dynamiczna.<br /><br /> 0x2: Metoda ogólna.<br /><br /> 0x4: Metoda skompilowana JIT (w przeciwnym razie wygenerowana przez NGen.exe)<br /><br /> 0x8: metoda pomocnika.|
|MethodNameSpace|win: UnicodeString|Pełna nazwa przestrzeni nazw skojarzona z metodą.|
|MethodName|win: UnicodeString|Pełna nazwa klasy skojarzona z metodą.|
|MethodSignature|win: UnicodeString|Sygnatura metody (rozdzielana przecinkami lista nazw typów).|
|ClrInstanceID|win: UInt16|Unikatowy identyfikator wystąpienia CLR lub CoreCLR.|

## <a name="methodjittingstarted-event"></a>Zdarzenie MethodJittingStarted

W poniższej tabeli przedstawiono słowo kluczowe i poziom:

|Słowo kluczowe do podniesienia zdarzenia|Poziom|
|-----------------------------------|-----------|
|`JITKeyword`(0x10) dostawca środowiska uruchomieniowego|Verbose (5)|
|`NGenKeyword`(0x20) dostawca środowiska uruchomieniowego|Verbose (5)|
|`JitRundownKeyword`(0x10) — dostawca uwalniania|Verbose (5)|
|`NGENRundownKeyword`(0x20) — dostawca uwalniania|Verbose (5)|

W poniższej tabeli przedstawiono informacje o zdarzeniu:

|Zdarzenie|Identyfikator zdarzenia|Opis|
|-----------|--------------|-----------------|
|`MethodJittingStarted`|145|Uruchamiany, gdy metoda jest skompilowana w trybie JIT.|

W poniższej tabeli przedstawiono dane zdarzenia:

|Nazwa pola|Typ danych|Opis|
|----------------|---------------|-----------------|
|MethodID|win: UInt64|Unikatowy identyfikator metody.|
|ModuleID|win: UInt64|Identyfikator modułu, do którego należy ta metoda.|
|MethodToken|win: UInt32|0 w przypadku metod dynamicznych i pomocników JIT.|
|MethodILSize|win: UInt32|Rozmiar języka pośredniego firmy Microsoft (MSIL) dla metody, która jest skompilowana w trybie JIT.|
|MethodNameSpace|win: UnicodeString|Pełna nazwa klasy skojarzona z metodą.|
|MethodName|win: UnicodeString|Nazwa metody.|
|MethodSignature|win: UnicodeString|Sygnatura metody (rozdzielana przecinkami lista nazw typów).|
|ClrInstanceID|win: UInt16|Unikatowy identyfikator wystąpienia CLR lub CoreCLR.|

## <a name="see-also"></a>Zobacz także

- [Zdarzenia ETW CLR](clr-etw-events.md)
