---
title: 'NETSDK1073: FrameworkReference nie został rozpoznany'
description: Jak rozwiązać problem polegający na tym, że nie można znaleźć FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713031"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="92395-103">NETSDK1073: FrameworkReference nie został rozpoznany</span><span class="sxs-lookup"><span data-stu-id="92395-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="92395-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2.1.100 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="92395-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="92395-105">Ten błąd zazwyczaj oznacza, że istnieje wersja określonego FrameworkReference, którą nie można znaleźć w zestawie SDK.</span><span class="sxs-lookup"><span data-stu-id="92395-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="92395-106">Spróbuj usunąć foldery *obj* i *bin* oraz uruchomić program, `dotnet restore` Aby ponownie pobrać najnowsze pakiety docelowe.</span><span class="sxs-lookup"><span data-stu-id="92395-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="92395-107">Alternatywnie może wystąpić problem z instalacją, dlatego upewnij się, że korzystasz z najnowszych wersji platformy .NET i programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92395-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
