---
description: -Optymalizuj (opcje kompilatora C#)
title: -Optymalizuj (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 1862794e4d823e38ce19780300a0b04f4e57dc44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193988"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="ab15d-103">-Optymalizuj (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="ab15d-103">-optimize (C# Compiler Options)</span></span>

<span data-ttu-id="ab15d-104">Opcja **-Optimize** włącza lub wyłącza optymalizacje wykonywane przez kompilator, aby plik wyjściowy był mniejszy, szybszy i bardziej wydajny.</span><span class="sxs-lookup"><span data-stu-id="ab15d-104">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab15d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ab15d-105">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="ab15d-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ab15d-106">Remarks</span></span>  

 <span data-ttu-id="ab15d-107">**-Optymalizuj** również informuje środowisko uruchomieniowe języka wspólnego, aby zoptymalizować kod w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ab15d-107">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="ab15d-108">Optymalizacje są domyślnie wyłączone.</span><span class="sxs-lookup"><span data-stu-id="ab15d-108">By default, optimizations are disabled.</span></span> <span data-ttu-id="ab15d-109">Określ **-Optimize +** , aby włączyć optymalizacje.</span><span class="sxs-lookup"><span data-stu-id="ab15d-109">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="ab15d-110">Podczas kompilowania modułu, który ma być używany przez zestaw, należy użyć **tych samych ustawień** , co w przypadku zestawu.</span><span class="sxs-lookup"><span data-stu-id="ab15d-110">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="ab15d-111">**-o** jest krótką formą **optymalizacji**.</span><span class="sxs-lookup"><span data-stu-id="ab15d-111">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="ab15d-112">Istnieje możliwość połączenia opcji **-Optimize** i [-Debug](./debug-compiler-option.md) .</span><span class="sxs-lookup"><span data-stu-id="ab15d-112">It is possible to combine the **-optimize** and [-debug](./debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ab15d-113">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ab15d-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ab15d-114">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="ab15d-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="ab15d-115">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="ab15d-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="ab15d-116">Zmodyfikuj właściwość **Optimize Code** .</span><span class="sxs-lookup"><span data-stu-id="ab15d-116">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="ab15d-117">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A> .</span><span class="sxs-lookup"><span data-stu-id="ab15d-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab15d-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="ab15d-118">Example</span></span>  

 <span data-ttu-id="ab15d-119">Kompiluj `t2.cs` i Włącz optymalizacje kompilatora:</span><span class="sxs-lookup"><span data-stu-id="ab15d-119">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab15d-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ab15d-120">See also</span></span>

- [<span data-ttu-id="ab15d-121">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="ab15d-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ab15d-122">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="ab15d-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
