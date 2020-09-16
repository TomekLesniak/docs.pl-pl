---
title: 'Instrukcje: Wyświetlanie zawartości globalnej pamięci podręcznej zestawów'
description: Dowiedz się, jak wyświetlić zawartość globalnej pamięci podręcznej zestawów w programie .NET przy użyciu narzędzia globalnej pamięci podręcznej zestawów (GAC) (gacutil.exe).
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: 8b81f78f4ea28b3b9fca374029fe49f809826d8e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558566"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="28aa9-103">Instrukcje: wyświetlanie zawartości globalnej pamięci podręcznej zestawów</span><span class="sxs-lookup"><span data-stu-id="28aa9-103">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="28aa9-104">Użyj [Narzędzia globalnej pamięci podręcznej zestawów (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) , aby wyświetlić zawartość globalnej pamięci podręcznej zestawów (GAC).</span><span class="sxs-lookup"><span data-stu-id="28aa9-104">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="28aa9-105">Wyświetlanie zestawów w globalnej pamięci podręcznej</span><span class="sxs-lookup"><span data-stu-id="28aa9-105">View the assemblies in the GAC</span></span>

<span data-ttu-id="28aa9-106">Aby wyświetlić listę zestawów w globalnej pamięci podręcznej zestawów, Otwórz [wiersz polecenia dla deweloperów dla programu Visual Studio](../tools/developer-command-prompt-for-vs.md), a następnie wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="28aa9-106">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="28aa9-107">-lub-</span><span class="sxs-lookup"><span data-stu-id="28aa9-107">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="28aa9-108">We wcześniejszych wersjach .NET Framework rozszerzenie powłoki systemu Windows zostało włączone [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) , aby wyświetlić globalną pamięć podręczną zestawów w Eksploratorze plików.</span><span class="sxs-lookup"><span data-stu-id="28aa9-108">In earlier versions of the .NET Framework, the [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="28aa9-109">Począwszy od .NET Framework 4 Shfusion.dll jest przestarzały.</span><span class="sxs-lookup"><span data-stu-id="28aa9-109">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="28aa9-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="28aa9-110">See also</span></span>

- [<span data-ttu-id="28aa9-111">Praca z zestawami i globalną pamięcią podręczną zestawów</span><span class="sxs-lookup"><span data-stu-id="28aa9-111">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="28aa9-112">Gacutil.exe (Global Assembly Cache Tool)</span><span class="sxs-lookup"><span data-stu-id="28aa9-112">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
