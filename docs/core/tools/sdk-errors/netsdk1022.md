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
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="cc325-103">NETSDK1022: uwzględniono zduplikowane elementy.</span><span class="sxs-lookup"><span data-stu-id="cc325-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="cc325-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 2.1.100 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="cc325-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="cc325-105">Począwszy od programu Visual Studio 2017/MSBuild w wersji 15,3, zestaw .NET SDK automatycznie uwzględnia elementy z katalogu projektu domyślnie.</span><span class="sxs-lookup"><span data-stu-id="cc325-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="cc325-106">Obejmuje to `Compile` i `Content` cele.</span><span class="sxs-lookup"><span data-stu-id="cc325-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="cc325-107">Powinno to znacząco czyścić plik projektu i zmniejszyć jego złożoność.</span><span class="sxs-lookup"><span data-stu-id="cc325-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="cc325-108">Aby przywrócić wcześniejsze zachowanie, należy ustawić poprawną właściwość na false.</span><span class="sxs-lookup"><span data-stu-id="cc325-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="cc325-109">Przykład dla `Compile` elementów:</span><span class="sxs-lookup"><span data-stu-id="cc325-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
