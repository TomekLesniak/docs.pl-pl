---
description: -elemencie pathmap (opcje kompilatora C#)
title: -elemencie pathmap (opcje kompilatora C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 707a37c6946cfcaf429552f0aeece6b87f3ad71d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125010"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="5a423-103">-elemencie pathmap (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="5a423-103">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="5a423-104">Opcja kompilatora **-elemencie pathmap** określa sposób mapowania ścieżek fizycznych do nazw ścieżek źródłowych wyjściowych przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="5a423-104">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a423-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5a423-105">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="5a423-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5a423-106">Arguments</span></span>

 <span data-ttu-id="5a423-107">`path1` Pełna ścieżka do plików źródłowych w bieżącym środowisku</span><span class="sxs-lookup"><span data-stu-id="5a423-107">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="5a423-108">`sourcePath1` Ścieżka źródłowa zastępują dla `path1` plików wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="5a423-108">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="5a423-109">Aby określić wiele mapowanych ścieżek źródłowych, rozdziel je przecinkami.</span><span class="sxs-lookup"><span data-stu-id="5a423-109">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a423-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5a423-110">Remarks</span></span>

<span data-ttu-id="5a423-111">Kompilator zapisuje ścieżkę źródłową do danych wyjściowych z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="5a423-111">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="5a423-112">Ścieżka źródłowa jest zastępowana argumentem, gdy <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> jest stosowany do opcjonalnego parametru.</span><span class="sxs-lookup"><span data-stu-id="5a423-112">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="5a423-113">Ścieżka źródłowa jest osadzona w pliku PDB.</span><span class="sxs-lookup"><span data-stu-id="5a423-113">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="5a423-114">Ścieżka pliku PDB jest osadzona w pliku PE (przenośny plik wykonywalny).</span><span class="sxs-lookup"><span data-stu-id="5a423-114">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="5a423-115">Ta opcja mapuje każdą ścieżkę fizyczną na komputerze, na którym kompilator jest uruchamiany do odpowiedniej ścieżki, która powinna być zapisywana w plikach wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="5a423-115">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="5a423-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="5a423-116">Example</span></span>

<span data-ttu-id="5a423-117">Kompiluj `t.cs` w katalogu **C: \\ Work \\ Tests** i Mapuj ten katalog na **\publish** w danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="5a423-117">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="5a423-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5a423-118">See also</span></span>

- [<span data-ttu-id="5a423-119">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="5a423-119">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5a423-120">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="5a423-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
