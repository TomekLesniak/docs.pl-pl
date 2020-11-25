---
title: 'NETSDK1013: nie rozpoznano wartości TargetFramework.'
description: Jak określić i ustawić prawidłową wartość TargetFramework
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: 915ac22ad822d17c082498b469acbfb3f1a93efc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717877"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: nie rozpoznano wartości TargetFramework

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.100 SDK i nowszych wersjach

Zestaw SDK próbuje przeanalizować wartości podane w pliku projektu dla `<TargetFramework>` lub `<TargetFrameworks>` w dobrze znanej wartości.  Jeśli wartość nie jest rozpoznawana, `TargetFrameworkIdentifier` wartość lub `TargetFrameworkVersion` może być ustawiona na pusty ciąg lub `Unsupported` .

Aby rozwiązać ten problem, Sprawdź pisownię `TargetFramework` wartości z listy [obsługiwanych platform](../../../standard/frameworks.md).
Można również ustawić `TargetFrameworkIdentifier` właściwości i, `TargetFrameworkVersion` bezpośrednio w pliku projektu.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
