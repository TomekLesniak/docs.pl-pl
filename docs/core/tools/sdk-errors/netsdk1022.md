---
title: 'NETSDK1022: uwzględniono zduplikowane elementy.'
description: Jak rozpoznać komunikat o zduplikowanym elemencie na podstawie domyślnego uwzględnienia.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: bc803f5316bf09c12c563f1a63b8385d1be4e9ce
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506639"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: uwzględniono zduplikowane elementy.

**Ten artykuł ma zastosowanie do:** ✔️ .NET 2.1.100 SDK i nowszych wersji

Począwszy od programu Visual Studio 2017/MSBuild w wersji 15,3, zestaw .NET SDK automatycznie uwzględnia elementy z katalogu projektu domyślnie.  Obejmuje to `Compile` i `Content` cele.  Powinno to znacząco czyścić plik projektu i zmniejszyć jego złożoność.

Aby przywrócić wcześniejsze zachowanie, należy ustawić poprawną właściwość na false.

Przykład dla `Compile` elementów:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
