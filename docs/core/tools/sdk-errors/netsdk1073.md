---
title: 'NETSDK1073: FrameworkReference nie został rozpoznany'
description: Jak rozwiązać problem polegający na tym, że nie można znaleźć FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957162"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: FrameworkReference nie został rozpoznany

**Ten artykuł ma zastosowanie do:** ✔️ .NET 2.1.100 SDK i nowszych wersji

Ten błąd zazwyczaj oznacza, że istnieje wersja określonego FrameworkReference, którą nie można znaleźć w zestawie SDK. Spróbuj usunąć foldery *obj* i *bin* oraz uruchomić program, `dotnet restore` Aby ponownie pobrać najnowsze pakiety docelowe.

Alternatywnie może wystąpić problem z instalacją, dlatego upewnij się, że korzystasz z najnowszych wersji platformy .NET i programu Visual Studio
