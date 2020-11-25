---
title: 'Nieprzerwana zmiana: wartość FrameworkDescription jest platformą .NET zamiast .NET Core'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, gdzie RuntimeInformation. FrameworkDescription teraz zwraca wartość ".NET" zamiast ".NET Core".
ms.date: 11/01/2020
ms.openlocfilehash: 3925fb092135c26291e1e60b99f359974d21553c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761559"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>FrameworkDescription jest wartością .NET zamiast .NET Core

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> teraz zwraca wartość ".NET" zamiast ".NET Core".

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca wartość ".NET Core" jako część ciągu opisu, na przykład `.NET Core 3.1.1` .

Począwszy od platformy .NET 5,0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca ".NET" jako część ciągu opisu, na przykład `.NET 5.0.0` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Program .NET 5 `netcoreapp` jest zastępowany przez `net` krótką moniker struktury Target. W celu zapewnienia spójności Opis został również zaktualizowany. Zmiana jest Kosmetyka, ponieważ `FrameworkName` nie jest zaszyfrowana w dowolnym miejscu niż we <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> właściwości.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Zaktualizuj dowolny kod, który wyszukuje ".NET Core" w ciągu zwracanym przez <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> .

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
