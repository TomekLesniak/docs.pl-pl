---
title: 'NETSDK1005 i NETSDK1047: brak elementu docelowego w pliku zasobów'
description: Jak rozwiązać problem braku elementu docelowego w pliku zasobu.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 6c22fd8c79c2ac6e024b46b4f67e08011d42efc6
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957171"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="eb5dd-103">NETSDK1005 i NETSDK1047: brak elementu docelowego w pliku zasobów</span><span class="sxs-lookup"><span data-stu-id="eb5dd-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="eb5dd-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 2.1.100 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="eb5dd-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="eb5dd-105">Gdy zestaw SDK programu .NET wystawia błąd NETSDK1005 lub NETSDK1047, w pliku zasobów projektu brakuje informacji o jednej z platform docelowych.</span><span class="sxs-lookup"><span data-stu-id="eb5dd-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="eb5dd-106">Może to być zwykle ustalone przez zagwarantowanie, że przywracanie jest uruchomione i że brakująca wartość docelowa jest uwzględniona we `TargetFrameworks` właściwości projektu.</span><span class="sxs-lookup"><span data-stu-id="eb5dd-106">This can usually be fixed by ensuring that restore is run and that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>

> [!NOTE]
> <span data-ttu-id="eb5dd-107">Wystąpił znany problem z wczesnymi kompilacjami programu .NET 5 Preview 8, gdy jest używany z wersjami wersji zapoznawczych programu Visual Studio 16,8, co spowodowało błąd.</span><span class="sxs-lookup"><span data-stu-id="eb5dd-107">There was a known issue with early builds of .NET 5 preview 8 when used with versions of Visual Studio 16.8 previews which resulted in this error.</span></span> <span data-ttu-id="eb5dd-108">W przypadku braku elementu docelowego `net5.0-windows7.0` lub upewnij się, `net5.0` że Zaktualizowano do najnowszych wersji programu Visual Studio i zestawu SDK programu .NET 5.</span><span class="sxs-lookup"><span data-stu-id="eb5dd-108">Specifically, if the missing target is `net5.0-windows7.0` or `net5.0`, ensure that you have updated to the latest versions of Visual Studio and the .NET 5 SDK.</span></span>
