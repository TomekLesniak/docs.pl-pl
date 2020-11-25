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
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="e5820-103">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="e5820-103">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="e5820-104">Począwszy od programu .NET 5,0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> zgłasza <xref:System.InvalidOperationException> zamiast tego, <xref:System.ArgumentException> czy zestaw liczników już istnieje.</span><span class="sxs-lookup"><span data-stu-id="e5820-104">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

## <a name="change-description"></a><span data-ttu-id="e5820-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="e5820-105">Change description</span></span>

<span data-ttu-id="e5820-106">W .NET Framework i .NET Core 1,0 do 3,1 można utworzyć wystąpienie zestawu liczników przez wywołanie <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> .</span><span class="sxs-lookup"><span data-stu-id="e5820-106">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="e5820-107">Jeśli jednak zestaw liczników już istnieje, metoda zgłasza <xref:System.ArgumentException> wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e5820-107">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="e5820-108">W przypadku programu .NET 5,0 i jego nowszych wersji, gdy wywoływany <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> jest zestaw liczników, <xref:System.InvalidOperationException> zgłaszany jest wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e5820-108">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e5820-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="e5820-109">Version introduced</span></span>

<span data-ttu-id="e5820-110">5,0</span><span class="sxs-lookup"><span data-stu-id="e5820-110">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e5820-111">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="e5820-111">Recommended action</span></span>

<span data-ttu-id="e5820-112">W przypadku przechwytywania <xref:System.ArgumentException> wyjątków w aplikacji podczas wywoływania <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> należy rozważyć również przechwycenie <xref:System.InvalidOperationException> wyjątków.</span><span class="sxs-lookup"><span data-stu-id="e5820-112">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="e5820-113"><xref:System.ArgumentException>Nie zaleca się przechwytywania wyjątków.</span><span class="sxs-lookup"><span data-stu-id="e5820-113">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e5820-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="e5820-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
