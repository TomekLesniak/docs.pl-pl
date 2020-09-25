---
description: -noconfig (opcje kompilatora C#)
title: -noconfig (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: d62f16a3926aaa78e79c25b1c9b8d84e4401795a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194079"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="79139-103">-noconfig (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="79139-103">-noconfig (C# Compiler Options)</span></span>

<span data-ttu-id="79139-104">Opcja **-noconfig** informuje kompilator, że nie kompiluje się z plikiem CSC. rsp, który znajduje się w i załadowany z tego samego katalogu co plik csc.exe.</span><span class="sxs-lookup"><span data-stu-id="79139-104">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79139-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="79139-105">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="79139-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="79139-106">Remarks</span></span>  

 <span data-ttu-id="79139-107">Plik csc. rsp odwołuje się do wszystkich zestawów dostarczonych z .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79139-107">The csc.rsp file references all the assemblies shipped with .NET Framework.</span></span> <span data-ttu-id="79139-108">Rzeczywiste odwołania, które zawiera środowisko programistyczne Visual Studio .NET, zależą od typu projektu.</span><span class="sxs-lookup"><span data-stu-id="79139-108">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="79139-109">Można zmodyfikować plik csc. rsp i określić dodatkowe opcje kompilatora, które powinny być zawarte w każdej kompilacji z wiersza polecenia z csc.exe (z wyjątkiem opcji **-noconfig** ).</span><span class="sxs-lookup"><span data-stu-id="79139-109">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="79139-110">Kompilator przetwarza opcje przesłane do polecenia **CSC** jako ostatni.</span><span class="sxs-lookup"><span data-stu-id="79139-110">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="79139-111">W związku z tym każda opcja w wierszu polecenia zastępuje ustawienie tej samej opcji w pliku CSC. rsp.</span><span class="sxs-lookup"><span data-stu-id="79139-111">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="79139-112">Jeśli nie chcesz, aby kompilator wyszukał i używał ustawień w pliku CSC. rsp, określ **-noconfig**.</span><span class="sxs-lookup"><span data-stu-id="79139-112">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="79139-113">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="79139-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79139-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="79139-114">See also</span></span>

- [<span data-ttu-id="79139-115">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="79139-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="79139-116">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="79139-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
