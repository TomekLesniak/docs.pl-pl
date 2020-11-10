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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="fb400-103">NETSDK1013: nie rozpoznano wartości TargetFramework</span><span class="sxs-lookup"><span data-stu-id="fb400-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="fb400-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 3.1.100 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="fb400-104">**This article applies to:** ✔️ .NET 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="fb400-105">Zestaw SDK próbuje przeanalizować wartości podane w pliku projektu dla `<TargetFramework>` lub `<TargetFrameworks>` w dobrze znanej wartości.</span><span class="sxs-lookup"><span data-stu-id="fb400-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="fb400-106">Jeśli wartość nie jest rozpoznawana, `TargetFrameworkIdentifier` wartość lub `TargetFrameworkVersion` może być ustawiona na pusty ciąg lub `Unsupported` .</span><span class="sxs-lookup"><span data-stu-id="fb400-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="fb400-107">Aby rozwiązać ten problem, Sprawdź pisownię `TargetFramework` wartości z listy [obsługiwanych platform](../../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="fb400-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="fb400-108">Można również ustawić `TargetFrameworkIdentifier` właściwości i, `TargetFrameworkVersion` bezpośrednio w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="fb400-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
