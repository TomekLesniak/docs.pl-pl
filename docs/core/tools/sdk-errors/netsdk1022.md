---
title: 'NETSDK1022: uwzględniono zduplikowane elementy.'
description: Jak rozpoznać komunikat o zduplikowanym elemencie na podstawie domyślnego uwzględnienia.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: 46c3d7d451e7c9e5b456b6e4e45054c3a4844386
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445787"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: uwzględniono zduplikowane elementy.

**Ten artykuł ma zastosowanie do:** ✔️ .NET 2.1.100 SDK i nowszych wersji

Począwszy od programu Visual Studio 15,3, zestaw .NET SDK automatycznie domyślnie uwzględnia elementy z katalogu projektu.  Obejmuje to `Compile` i `Content` cele.  Powinno to znacząco czyścić plik projektu i zmniejszyć jego złożoność.

Aby przywrócić wcześniejsze zachowanie, należy ustawić poprawną właściwość na false.

Przykład dla `Compile` elementów:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
