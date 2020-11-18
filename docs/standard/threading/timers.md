---
title: Czasomierze
description: Dowiedz się, jakie czasomierze .NET mają być używane w środowisku wielowątkowym.
ms.date: 07/03/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: 1ab612bc32a84c1248d311b0603a01a32a25199f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826108"
---
# <a name="timers"></a>Czasomierze

Platforma .NET oferuje dwa czasomierze do użycia w środowisku wielowątkowym:

- <xref:System.Threading.Timer?displayProperty=nameWithType>, która wykonuje pojedynczą metodę wywołania zwrotnego w <xref:System.Threading.ThreadPool> wątku w regularnych odstępach czasu.
- <xref:System.Timers.Timer?displayProperty=nameWithType>, które domyślnie wywołuje zdarzenie w <xref:System.Threading.ThreadPool> wątku w regularnych odstępach czasu.

> [!NOTE]
> Niektóre implementacje platformy .NET mogą obejmować dodatkowe czasomierze:
>
> - <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: składnik Windows Forms, który uruchamia zdarzenie w regularnych odstępach czasu. Składnik nie ma interfejsu użytkownika i jest przeznaczony do użytku w środowisku jednowątkowym.  
> - <xref:System.Web.UI.Timer?displayProperty=nameWithType>: składnik ASP.NET, który wykonuje asynchroniczne lub synchroniczne ogłaszanie stron sieci Web w regularnych odstępach czasu.
> - <xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: czasomierz, który jest zintegrowany z <xref:System.Windows.Threading.Dispatcher> kolejką, która jest przetwarzana w określonym przedziale czasu i o określonym priorytecie.

## <a name="the-systemthreadingtimer-class"></a>Klasa System. Threading. Timer

<xref:System.Threading.Timer?displayProperty=nameWithType>Klasa umożliwia ciągłe wywoływanie delegata w określonych przedziałach czasowych. Tej klasy można również użyć do zaplanowania pojedynczego wywołania delegata w określonym przedziale czasu. Delegat jest wykonywany w <xref:System.Threading.ThreadPool> wątku.

Podczas tworzenia <xref:System.Threading.Timer?displayProperty=nameWithType> obiektu należy określić <xref:System.Threading.TimerCallback> delegata, który definiuje metodę wywołania zwrotnego, opcjonalny obiekt stanu, który jest przesyłany do wywołania zwrotnego, ilość czasu oczekiwania przed pierwszym wywołaniem wywołania zwrotnego oraz odstęp czasu między wywołaniami wywołania zwrotnego. Aby anulować oczekujący czasomierz, wywołaj <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> metodę.

Poniższy przykład tworzy czasomierz, który wywołuje dostarczony delegat po raz pierwszy po jednej sekundzie (1000 milisekund), a następnie wywołuje ją co dwie sekundy. Obiekt State w przykładzie służy do zliczania, ile razy obiekt delegowany jest wywoływany. Czasomierz jest zatrzymany, gdy delegat został wywołany co najmniej 10 razy.

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Threading.Timer?displayProperty=nameWithType> .

## <a name="the-systemtimerstimer-class"></a>Klasa System. Timers. czasomierz

Innym czasomierzem, który może być używany w środowisku wielowątkowym, jest to <xref:System.Timers.Timer?displayProperty=nameWithType> , że domyślnie wywołuje zdarzenie na <xref:System.Threading.ThreadPool> wątku.

Podczas tworzenia <xref:System.Timers.Timer?displayProperty=nameWithType> obiektu można określić przedział czasu, w którym ma zostać zgłoszone <xref:System.Timers.Timer.Elapsed> zdarzenie. Użyj <xref:System.Timers.Timer.Enabled%2A> właściwości, aby wskazać, czy czasomierz powinien zgłosić <xref:System.Timers.Timer.Elapsed> zdarzenie. Jeśli potrzebujesz <xref:System.Timers.Timer.Elapsed> zdarzenia, które ma zostać zgłoszone tylko raz po upływie określonego interwału, ustaw wartość <xref:System.Timers.Timer.AutoReset%2A> na `false` . Wartość domyślna <xref:System.Timers.Timer.AutoReset%2A> Właściwości to `true` , co oznacza, że <xref:System.Timers.Timer.Elapsed> zdarzenie jest zgłaszane regularnie w interwale zdefiniowanym przez <xref:System.Timers.Timer.Interval%2A> Właściwość.

Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Timers.Timer?displayProperty=nameWithType> .
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [Wątkowość obiektów i funkcji](threading-objects-and-features.md)
