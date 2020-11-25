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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="db3d5-103">NETSDK1013: nie rozpoznano wartości TargetFramework</span><span class="sxs-lookup"><span data-stu-id="db3d5-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="db3d5-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.100 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="db3d5-104">**This article applies to:** ✔️ .NET Core 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="db3d5-105">Zestaw SDK próbuje przeanalizować wartości podane w pliku projektu dla `<TargetFramework>` lub `<TargetFrameworks>` w dobrze znanej wartości.</span><span class="sxs-lookup"><span data-stu-id="db3d5-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="db3d5-106">Jeśli wartość nie jest rozpoznawana, `TargetFrameworkIdentifier` wartość lub `TargetFrameworkVersion` może być ustawiona na pusty ciąg lub `Unsupported` .</span><span class="sxs-lookup"><span data-stu-id="db3d5-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="db3d5-107">Aby rozwiązać ten problem, Sprawdź pisownię `TargetFramework` wartości z listy [obsługiwanych platform](../../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="db3d5-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="db3d5-108">Można również ustawić `TargetFrameworkIdentifier` właściwości i, `TargetFrameworkVersion` bezpośrednio w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="db3d5-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
