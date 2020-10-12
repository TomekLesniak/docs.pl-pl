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
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="6fc73-103">NETSDK1073: FrameworkReference nie został rozpoznany</span><span class="sxs-lookup"><span data-stu-id="6fc73-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="6fc73-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 2.1.100 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="6fc73-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="6fc73-105">Ten błąd zazwyczaj oznacza, że istnieje wersja określonego FrameworkReference, którą nie można znaleźć w zestawie SDK.</span><span class="sxs-lookup"><span data-stu-id="6fc73-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="6fc73-106">Spróbuj usunąć foldery *obj* i *bin* oraz uruchomić program, `dotnet restore` Aby ponownie pobrać najnowsze pakiety docelowe.</span><span class="sxs-lookup"><span data-stu-id="6fc73-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="6fc73-107">Alternatywnie może wystąpić problem z instalacją, dlatego upewnij się, że korzystasz z najnowszych wersji platformy .NET i programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6fc73-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
