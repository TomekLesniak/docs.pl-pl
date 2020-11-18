---
title: Tworzenie aplikacji konsolowych w programie .NET
ms.date: 03/30/2017
helpviewer_keywords:
- .NET, creating console applications
- application development [.NET], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
ms.openlocfilehash: 8046b1b8cb50476860fee53654de93c924d23346
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823975"
---
# <a name="console-apps-in-net"></a>Aplikacje konsolowe w programie .NET

Aplikacje platformy .NET mogą używać <xref:System.Console?displayProperty=nameWithType> klasy do odczytywania znaków z i pisania znaków w konsoli programu. Dane z konsoli są odczytywane ze standardowego strumienia wejściowego, dane do konsoli są zapisywane w standardowym strumieniu wyjściowym, a dane błędów do konsoli są zapisywane w standardowym strumieniu wyjściowym błędu. Te strumienie są automatycznie kojarzone z konsolą programu, gdy aplikacja jest uruchamiana i są prezentowane <xref:System.Console.In%2A> <xref:System.Console.Out%2A> odpowiednio jako właściwości, i <xref:System.Console.Error%2A> .

Wartość <xref:System.Console.In%2A?displayProperty=nameWithType> właściwości jest <xref:System.IO.TextReader?displayProperty=nameWithType> obiektem, natomiast wartości <xref:System.Console.Out%2A?displayProperty=nameWithType> <xref:System.Console.Error%2A?displayProperty=nameWithType> właściwości i są <xref:System.IO.TextWriter?displayProperty=nameWithType> obiektami. Można skojarzyć te właściwości ze strumieniami, które nie reprezentują konsoli, dzięki czemu można wskazywać strumień do innej lokalizacji dla danych wejściowych lub wyjściowych. Na przykład można przekierować dane wyjściowe do pliku przez ustawienie <xref:System.Console.Out%2A?displayProperty=nameWithType> właściwości na <xref:System.IO.StreamWriter?displayProperty=nameWithType> , która hermetyzuje <xref:System.IO.FileStream?displayProperty=nameWithType> za pomocą <xref:System.Console.SetOut%2A?displayProperty=nameWithType> metody. <xref:System.Console.In%2A?displayProperty=nameWithType>Właściwości i <xref:System.Console.Out%2A?displayProperty=nameWithType> nie muszą odwoływać się do tego samego strumienia.

> [!NOTE]
> Aby uzyskać więcej informacji na temat tworzenia aplikacji konsolowych, w tym przykładów w językach C#, Visual Basic i C++, zobacz dokumentację <xref:System.Console> klasy.

Jeśli konsola nie istnieje, na przykład w aplikacji Windows Forms dane wyjściowe zapisane w standardowym strumieniu wyjściowym nie będą widoczne, ponieważ nie ma konsoli do zapisywania informacji. Zapisanie informacji w konsoli niedostępnej nie powoduje wystąpienia wyjątku. (Można zawsze zmienić typ aplikacji na **aplikację konsolową**, na przykład na stronach właściwości projektu w programie Visual Studio).

Klasa **System. Console** ma metody, które mogą odczytywać poszczególne znaki lub wszystkie wiersze z konsoli. Inne metody konwertują dane i ciągi formatowania, a następnie zapisują sformatowane ciągi do konsoli. Aby uzyskać więcej informacji na temat formatowania ciągów, zobacz [Typy formatowania](base-types/formatting-types.md).

> [!TIP]
> Aplikacje konsolowe nie posiadają pompy komunikatów, która jest domyślnie uruchamiana. W związku z tym, wywołania konsoli do czasomierzy Win32 firmy Microsoft mogą zakończyć się niepowodzeniem.

## <a name="see-also"></a>Zobacz także

- <xref:System.Console?displayProperty=nameWithType>
- [Formatowanie typów](base-types/formatting-types.md)
