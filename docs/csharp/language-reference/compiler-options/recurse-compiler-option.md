---
description: -rekursywnie (opcje kompilatora C#)
title: -rekursywnie (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 3edd7e23358bc0569dae6204d519209df1ade290
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124828"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="52748-103">-rekursywnie (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="52748-103">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="52748-104">Opcja-rekursywnie umożliwia skompilowanie plików kodu źródłowego we wszystkich katalogach podrzędnych określonego katalogu (dir) lub katalogu projektu.</span><span class="sxs-lookup"><span data-stu-id="52748-104">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52748-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="52748-105">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="52748-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="52748-106">Arguments</span></span>  
 <span data-ttu-id="52748-107">`dir` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="52748-107">`dir` (optional)</span></span>  
 <span data-ttu-id="52748-108">Katalog, w którym ma zostać rozpoczęte wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="52748-108">The directory in which you want the search to begin.</span></span> <span data-ttu-id="52748-109">Jeśli ta wartość nie jest określona, wyszukiwanie rozpoczyna się w katalogu projektu.</span><span class="sxs-lookup"><span data-stu-id="52748-109">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="52748-110">Pliki do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="52748-110">The file(s) to search for.</span></span> <span data-ttu-id="52748-111">Symbole wieloznaczne są dozwolone.</span><span class="sxs-lookup"><span data-stu-id="52748-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52748-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="52748-112">Remarks</span></span>  
 <span data-ttu-id="52748-113">Opcja **-rekursywnie** umożliwia skompilowanie plików kodu źródłowego we wszystkich katalogach podrzędnych określonego katalogu ( `dir` ) lub katalogu projektu.</span><span class="sxs-lookup"><span data-stu-id="52748-113">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="52748-114">W nazwie pliku można użyć symboli wieloznacznych, aby skompilować wszystkie zgodne pliki w katalogu projektu bez użycia opcji **-rekursywnie**.</span><span class="sxs-lookup"><span data-stu-id="52748-114">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="52748-115">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="52748-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52748-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="52748-116">Example</span></span>  
 <span data-ttu-id="52748-117">Kompiluje wszystkie pliki C# w bieżącym katalogu:</span><span class="sxs-lookup"><span data-stu-id="52748-117">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="52748-118">Kompiluje wszystkie pliki C# w katalogu dir1\dir2 i wszystkie znajdujące się w nim katalogi i generuje dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="52748-118">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="52748-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="52748-119">See also</span></span>

- [<span data-ttu-id="52748-120">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="52748-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="52748-121">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="52748-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
