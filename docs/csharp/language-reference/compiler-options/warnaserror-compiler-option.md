---
description: -warnaserror — (opcje kompilatora C#)
title: -warnaserror — (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 9c3b307668968865b401aedc04c79f95d4f32513
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91171341"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="0797e-103">-warnaserror — (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="0797e-103">-warnaserror (C# Compiler Options)</span></span>

<span data-ttu-id="0797e-104">Opcja **-warnaserror — +** traktuje wszystkie ostrzeżenia jako błędy</span><span class="sxs-lookup"><span data-stu-id="0797e-104">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0797e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0797e-105">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="0797e-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0797e-106">Remarks</span></span>  

 <span data-ttu-id="0797e-107">Wszystkie komunikaty, które zwykle są raportowane jako ostrzeżenia, są raportowane jako błędy, a proces kompilacji jest zatrzymany (nie skompilowano plików wyjściowych).</span><span class="sxs-lookup"><span data-stu-id="0797e-107">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="0797e-108">Domyślnie **— warnaserror — —** obowiązuje, co powoduje, że ostrzeżenia nie uniemożliwiają generowania pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="0797e-108">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="0797e-109">**-warnaserror —**, która jest taka sama jak **-warnaserror — +**, powoduje, że ostrzeżenia są traktowane jako błędy.</span><span class="sxs-lookup"><span data-stu-id="0797e-109">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="0797e-110">Opcjonalnie, jeśli chcesz, aby tylko kilka określonych ostrzeżeń było traktowane jako błędy, możesz określić rozdzieloną przecinkami listę numerów ostrzeżeń, które będą traktowane jako błędy.</span><span class="sxs-lookup"><span data-stu-id="0797e-110">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="0797e-111">Zestaw wszystkich ostrzeżeń o wartości null można określić za pomocą skrótu **dopuszczający wartość** null.</span><span class="sxs-lookup"><span data-stu-id="0797e-111">The set of all nullability warnings can be specified with the **nullable** shorthand.</span></span>
  
 <span data-ttu-id="0797e-112">Użyj [-warn](./warn-compiler-option.md) , aby określić poziom ostrzeżeń, które mają być wyświetlane w kompilatorze.</span><span class="sxs-lookup"><span data-stu-id="0797e-112">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="0797e-113">Użyj [-nowarn](./nowarn-compiler-option.md) , aby wyłączyć niektóre ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="0797e-113">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0797e-114">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0797e-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="0797e-115">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="0797e-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="0797e-116">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="0797e-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="0797e-117">Zmodyfikuj właściwość **Traktuj ostrzeżenia jako błędy** .</span><span class="sxs-lookup"><span data-stu-id="0797e-117">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="0797e-118">Aby programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors> .</span><span class="sxs-lookup"><span data-stu-id="0797e-118">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0797e-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="0797e-119">Example</span></span>  

 <span data-ttu-id="0797e-120">Kompiluj `in.cs` i czy kompilator nie wyświetli żadnych ostrzeżeń:</span><span class="sxs-lookup"><span data-stu-id="0797e-120">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0797e-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0797e-121">See also</span></span>

- [<span data-ttu-id="0797e-122">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="0797e-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="0797e-123">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="0797e-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
