---
title: 'NETSDK1013: nie rozpoznano wartości TargetFramework.'
description: Jak określić i ustawić prawidłową wartość TargetFramework
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: bcaed878b663f8bc957e8469ffd78caa9babf710
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445773"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: nie rozpoznano wartości TargetFramework

**Ten artykuł ma zastosowanie do:** ✔️ .NET 3.1.100 SDK i nowszych wersji

Zestaw SDK próbuje przeanalizować wartości podane w pliku projektu dla `<TargetFramework>` lub `<TargetFrameworks>` w dobrze znanej wartości.  Jeśli wartość nie jest rozpoznawana, `TargetFrameworkIdentifier` wartość lub `TargetFrameworkVersion` może być ustawiona na pusty ciąg lub `Unsupported` .

Aby rozwiązać ten problem, Sprawdź pisownię `TargetFramework` wartości z listy [obsługiwanych platform](../../../standard/frameworks.md).
Można również ustawić `TargetFrameworkIdentifier` właściwości i, `TargetFrameworkVersion` bezpośrednio w pliku projektu.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
