---
description: '@ (opcje kompilatora C#)'
title: '@ (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: 8f7e222e194fc4ba96159ecd792765f64b4d1c57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193757"
---
# <a name="-c-compiler-options"></a><span data-ttu-id="75a58-103">@ (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="75a58-103">@ (C# Compiler Options)</span></span>

<span data-ttu-id="75a58-104">Opcja @ pozwala określić plik, który zawiera opcje kompilatora i pliki kodu źródłowego do skompilowania.</span><span class="sxs-lookup"><span data-stu-id="75a58-104">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a58-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="75a58-105">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="75a58-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="75a58-106">Arguments</span></span>  

 `response_file`  
 <span data-ttu-id="75a58-107">Plik, który zawiera listę opcji kompilatora lub plików kodu źródłowego do skompilowania.</span><span class="sxs-lookup"><span data-stu-id="75a58-107">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75a58-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="75a58-108">Remarks</span></span>  

 <span data-ttu-id="75a58-109">Opcje kompilatora i pliki kodu źródłowego będą przetwarzane przez kompilator tak, jakby zostały określone w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="75a58-109">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="75a58-110">Aby określić więcej niż jeden plik odpowiedzi w kompilacji, określ wiele opcji plików odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="75a58-110">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="75a58-111">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="75a58-111">For example:</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="75a58-112">W pliku odpowiedzi w jednym wierszu może znajdować się wiele opcji kompilatora i plików kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="75a58-112">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="75a58-113">Jedna Specyfikacja opcji kompilatora musi znajdować się w jednym wierszu (nie może obejmować wielu wierszy).</span><span class="sxs-lookup"><span data-stu-id="75a58-113">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="75a58-114">Pliki odpowiedzi mogą mieć komentarze zaczynające się od znaku #.</span><span class="sxs-lookup"><span data-stu-id="75a58-114">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="75a58-115">Określanie opcji kompilatora z poziomu pliku odpowiedzi jest tak samo samo jak wydawanie tych poleceń w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="75a58-115">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="75a58-116">Aby uzyskać więcej informacji, zobacz [Kompilowanie z wiersza polecenia](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) .</span><span class="sxs-lookup"><span data-stu-id="75a58-116">See [Building from the Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="75a58-117">Kompilator przetwarza opcje polecenia w miarę ich napotkania.</span><span class="sxs-lookup"><span data-stu-id="75a58-117">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="75a58-118">W związku z tym argumenty wiersza polecenia mogą przesłonić wcześniej wymienione opcje w plikach odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="75a58-118">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="75a58-119">Z kolei opcje w pliku odpowiedzi zastępują opcje wymienione wcześniej w wierszu polecenia lub w innych plikach odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="75a58-119">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="75a58-120">C# udostępnia plik csc. rsp, który znajduje się w tym samym katalogu, co plik csc.exe.</span><span class="sxs-lookup"><span data-stu-id="75a58-120">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="75a58-121">Aby uzyskać więcej informacji na temat CSC. rsp, zobacz [-noconfig](./noconfig-compiler-option.md) .</span><span class="sxs-lookup"><span data-stu-id="75a58-121">See [-noconfig](./noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="75a58-122">Nie można ustawić tej opcji kompilatora w środowisku deweloperskim programu Visual Studio, ani programowo zmienić.</span><span class="sxs-lookup"><span data-stu-id="75a58-122">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a58-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="75a58-123">Example</span></span>  

 <span data-ttu-id="75a58-124">Poniżej przedstawiono kilka wierszy z przykładowego pliku odpowiedzi:</span><span class="sxs-lookup"><span data-stu-id="75a58-124">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="75a58-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75a58-125">See also</span></span>

- [<span data-ttu-id="75a58-126">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="75a58-126">C# Compiler Options</span></span>](./index.md)
