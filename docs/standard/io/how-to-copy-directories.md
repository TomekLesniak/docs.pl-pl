---
title: 'Instrukcje: kopiowanie katalogów'
description: Zapoznaj się z tematem jak kopiować katalogi przy użyciu klas we/wy, które synchronicznie kopiują zawartość katalogu do innej lokalizacji.
ms.date: 12/27/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: dfe45d8529eb927a6b174a7bb411afa8072035f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679068"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="67b7b-103">Instrukcje: kopiowanie katalogów</span><span class="sxs-lookup"><span data-stu-id="67b7b-103">How to: Copy directories</span></span>

<span data-ttu-id="67b7b-104">W tym artykule pokazano, jak używać klas we/wy do synchronicznego kopiowania zawartości katalogu do innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="67b7b-104">This article demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span>

<span data-ttu-id="67b7b-105">Aby zapoznać się z przykładem asynchronicznego kopiowania plików, zobacz [asynchroniczne operacje we/wy na plikach](asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="67b7b-105">For an example of asynchronous file copy, see [Asynchronous file I/O](asynchronous-file-i-o.md).</span></span>

<span data-ttu-id="67b7b-106">Ten przykład kopiuje podkatalogi przez ustawienie `copySubDirs` `DirectoryCopy` metody na `true` .</span><span class="sxs-lookup"><span data-stu-id="67b7b-106">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="67b7b-107">`DirectoryCopy`Metoda cyklicznie kopiuje podkatalogi przez wywołanie ich w każdym podkatalogu, dopóki nie będzie więcej do kopiowania.</span><span class="sxs-lookup"><span data-stu-id="67b7b-107">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67b7b-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="67b7b-108">Example</span></span>  

 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a><span data-ttu-id="67b7b-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="67b7b-109">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="67b7b-110">We/wy plików i strumieni</span><span class="sxs-lookup"><span data-stu-id="67b7b-110">File and stream I/O</span></span>](index.md)
- [<span data-ttu-id="67b7b-111">Typowe zadania we/wy</span><span class="sxs-lookup"><span data-stu-id="67b7b-111">Common I/O tasks</span></span>](common-i-o-tasks.md)
- [<span data-ttu-id="67b7b-112">Asynchroniczne operacje we/wy pliku</span><span class="sxs-lookup"><span data-stu-id="67b7b-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)
