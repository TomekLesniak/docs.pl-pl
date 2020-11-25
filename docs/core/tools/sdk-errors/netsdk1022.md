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
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="eeeac-103">NETSDK1022: uwzględniono zduplikowane elementy.</span><span class="sxs-lookup"><span data-stu-id="eeeac-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="eeeac-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2.1.100 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="eeeac-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="eeeac-105">Począwszy od programu Visual Studio 2017/MSBuild w wersji 15,3, zestaw .NET SDK automatycznie uwzględnia elementy z katalogu projektu domyślnie.</span><span class="sxs-lookup"><span data-stu-id="eeeac-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="eeeac-106">Obejmuje to `Compile` i `Content` cele.</span><span class="sxs-lookup"><span data-stu-id="eeeac-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="eeeac-107">Powinno to znacząco czyścić plik projektu i zmniejszyć jego złożoność.</span><span class="sxs-lookup"><span data-stu-id="eeeac-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="eeeac-108">Aby przywrócić wcześniejsze zachowanie, należy ustawić poprawną właściwość na false.</span><span class="sxs-lookup"><span data-stu-id="eeeac-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="eeeac-109">Przykład dla `Compile` elementów:</span><span class="sxs-lookup"><span data-stu-id="eeeac-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
