---
title: 'NETSDK1022: uwzględniono zduplikowane elementy.'
description: Jak rozpoznać komunikat o zduplikowanym elemencie na podstawie domyślnego uwzględnienia.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717876"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: uwzględniono zduplikowane elementy.

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2.1.100 SDK i nowszych wersjach

Począwszy od programu Visual Studio 2017/MSBuild w wersji 15,3, zestaw .NET SDK automatycznie uwzględnia elementy z katalogu projektu domyślnie.  Obejmuje to `Compile` i `Content` cele.  Powinno to znacząco czyścić plik projektu i zmniejszyć jego złożoność.

Aby przywrócić wcześniejsze zachowanie, należy ustawić poprawną właściwość na false.

Przykład dla `Compile` elementów:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
