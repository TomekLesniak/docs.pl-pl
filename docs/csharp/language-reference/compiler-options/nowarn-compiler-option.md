---
description: -nowarn (opcje kompilatora C#)
title: -nowarn (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: 31a7ee5eacb2e7cd6b24c4a2276ce6e07fcc67e1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91194027"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="e1b82-103">-nowarn (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="e1b82-103">-nowarn (C# Compiler Options)</span></span>

<span data-ttu-id="e1b82-104">Opcja **-nowarn** pozwala pominąć kompilator z wyświetlania jednego lub kilku ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="e1b82-104">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="e1b82-105">Oddziel wiele numerów ostrzeżeń przecinkami.</span><span class="sxs-lookup"><span data-stu-id="e1b82-105">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b82-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="e1b82-106">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e1b82-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e1b82-107">Arguments</span></span>  

 <span data-ttu-id="e1b82-108">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="e1b82-108">`number1`, `number2`</span></span>  
 <span data-ttu-id="e1b82-109">Liczba ostrzeżeń, które kompilator ma pominąć.</span><span class="sxs-lookup"><span data-stu-id="e1b82-109">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1b82-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e1b82-110">Remarks</span></span>  

 <span data-ttu-id="e1b82-111">Należy określić tylko liczbowe części identyfikatora ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="e1b82-111">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="e1b82-112">Na przykład jeśli chcesz pominąć CS0028, możesz określić `-nowarn:28` .</span><span class="sxs-lookup"><span data-stu-id="e1b82-112">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="e1b82-113">Kompilator zignoruje w sposób cichy odpowiednie numery ostrzeżeń `-nowarn` , które były prawidłowe w poprzednich wersjach, ale zostały usunięte z kompilatora.</span><span class="sxs-lookup"><span data-stu-id="e1b82-113">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="e1b82-114">Na przykład CS0679 był prawidłowy w kompilatorze w Visual Studio .NET 2002, ale został następnie usunięty.</span><span class="sxs-lookup"><span data-stu-id="e1b82-114">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="e1b82-115">Następujące ostrzeżenia nie mogą być pomijane przez `-nowarn` opcję:</span><span class="sxs-lookup"><span data-stu-id="e1b82-115">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
- <span data-ttu-id="e1b82-116">Ostrzeżenie kompilatora (poziom 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="e1b82-116">Compiler Warning (level 1) CS2002</span></span>  
  
- <span data-ttu-id="e1b82-117">Ostrzeżenie kompilatora (poziom 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="e1b82-117">Compiler Warning (level 1) CS2023</span></span>  
  
- <span data-ttu-id="e1b82-118">Ostrzeżenie kompilatora (poziom 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="e1b82-118">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e1b82-119">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e1b82-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="e1b82-120">Otwórz stronę **Właściwości** dla projektu.</span><span class="sxs-lookup"><span data-stu-id="e1b82-120">Open the **Properties** page for the project.</span></span> <span data-ttu-id="e1b82-121">Aby uzyskać szczegółowe informacje, zobacz [stronę Kompilacja, Projektant projektu (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="e1b82-121">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="e1b82-122">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="e1b82-122">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="e1b82-123">Zmodyfikuj właściwość **Pomijaj ostrzeżenia** .</span><span class="sxs-lookup"><span data-stu-id="e1b82-123">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="e1b82-124">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.DelaySign%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1b82-124">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b82-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e1b82-125">See also</span></span>

- [<span data-ttu-id="e1b82-126">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="e1b82-126">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e1b82-127">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="e1b82-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e1b82-128">Błędy kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="e1b82-128">C# Compiler Errors</span></span>](../compiler-messages/index.md)
