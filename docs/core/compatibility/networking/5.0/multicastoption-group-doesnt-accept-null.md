---
title: 'Nieprzerwana zmiana: MulticastOption. Group nie akceptuje wartości null.'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, gdzie MulticastOption. Group nie akceptuje już wartości null.
ms.date: 08/18/2020
ms.openlocfilehash: 164ac8c2c8dd14f9e0758017e54eeb377f88a7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761439"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption. Group nie akceptuje wartości null

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> nie akceptuje już wartości `null` . Jeśli właściwość zostanie ustawiona na `null` , <xref:System.ArgumentNullException> zostanie zgłoszony.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

We wcześniejszych wersjach programu .NET można ustawić <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> Właściwość na `null` . Jeśli <xref:System.Net.Sockets.MulticastOption> przeszedł później do <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> , środowisko uruchomieniowe wygeneruje <xref:System.NullReferenceException> .

W programie .NET 5,0 i nowszych <xref:System.ArgumentNullException> jest zgłaszany, jeśli właściwość zostanie ustawiona na `null` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Aby zachować zgodność ze wskazówkami dotyczącymi projektowania struktury, właściwość została zaktualizowana w celu wygenerowania <xref:System.ArgumentNullException> wartości `null` .

## <a name="recommended-action"></a>Zalecana akcja

Upewnij się, że nie ustawiono <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> opcji `null` .

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
