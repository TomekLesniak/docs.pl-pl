---
title: 'Nieprzerwana zmiana: CreateCounterSetInstance zgłasza InvalidOperationException, jeśli wystąpienie już istnieje'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, gdzie element CounterSet. CreateCounterSetInstance zgłasza inny wyjątek, jeśli licznik już istnieje.
ms.date: 11/01/2020
ms.openlocfilehash: 28042690b71f9b86e4e54748ec75467bbe232684
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761563"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje

Począwszy od programu .NET 5,0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> zgłasza <xref:System.InvalidOperationException> zamiast tego, <xref:System.ArgumentException> czy zestaw liczników już istnieje.

## <a name="change-description"></a>Zmień opis

W .NET Framework i .NET Core 1,0 do 3,1 można utworzyć wystąpienie zestawu liczników przez wywołanie <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> . Jeśli jednak zestaw liczników już istnieje, metoda zgłasza <xref:System.ArgumentException> wyjątek.

W przypadku programu .NET 5,0 i jego nowszych wersji, gdy wywoływany <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> jest zestaw liczników, <xref:System.InvalidOperationException> zgłaszany jest wyjątek.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

W przypadku przechwytywania <xref:System.ArgumentException> wyjątków w aplikacji podczas wywoływania <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> należy rozważyć również przechwycenie <xref:System.InvalidOperationException> wyjątków.

> [!NOTE]
> <xref:System.ArgumentException>Nie zaleca się przechwytywania wyjątków.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
