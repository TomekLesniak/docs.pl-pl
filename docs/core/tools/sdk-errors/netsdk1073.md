---
title: 'NETSDK1073: FrameworkReference nie został rozpoznany'
description: Jak rozwiązać problem polegający na tym, że nie można znaleźć FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713031"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: FrameworkReference nie został rozpoznany

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2.1.100 SDK i nowszych wersjach

Ten błąd zazwyczaj oznacza, że istnieje wersja określonego FrameworkReference, którą nie można znaleźć w zestawie SDK. Spróbuj usunąć foldery *obj* i *bin* oraz uruchomić program, `dotnet restore` Aby ponownie pobrać najnowsze pakiety docelowe.

Alternatywnie może wystąpić problem z instalacją, dlatego upewnij się, że korzystasz z najnowszych wersji platformy .NET i programu Visual Studio
