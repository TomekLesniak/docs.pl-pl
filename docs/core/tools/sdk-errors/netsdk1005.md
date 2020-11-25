---
title: 'NETSDK1005 i NETSDK1047: brak elementu docelowego w pliku zasobów'
description: Jak rozwiązać problem braku elementu docelowego w pliku zasobu.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 207c8b0274c13e7af594e05cfac2a95907f85b81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717906"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 i NETSDK1047: brak elementu docelowego w pliku zasobów

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2.1.100 SDK i nowszych wersjach

Gdy zestaw SDK programu .NET wystawia błąd NETSDK1005 lub NETSDK1047, w pliku zasobów projektu brakuje informacji o jednej z platform docelowych. Może to być zwykle ustalone przez zagwarantowanie, że przywracanie jest uruchomione i że brakująca wartość docelowa jest uwzględniona we `TargetFrameworks` właściwości projektu.

> [!NOTE]
> Wystąpił znany problem z wczesnymi kompilacjami programu .NET 5 Preview 8, gdy jest używany z wersjami wersji zapoznawczych programu Visual Studio 16,8, co spowodowało błąd. W przypadku braku elementu docelowego `net5.0-windows7.0` lub upewnij się, `net5.0` że Zaktualizowano do najnowszych wersji programu Visual Studio i zestawu SDK programu .NET 5.
