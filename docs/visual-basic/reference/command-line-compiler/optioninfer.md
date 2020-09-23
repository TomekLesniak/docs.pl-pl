---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: 3edb1f74ab63497aeda0d72847bce92ad315a1a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098920"
---
# <a name="-optioninfer"></a><span data-ttu-id="6333c-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="6333c-102">-optioninfer</span></span>

<span data-ttu-id="6333c-103">Umożliwia korzystanie z wnioskowania o typie lokalnym w deklaracjach zmiennych.</span><span class="sxs-lookup"><span data-stu-id="6333c-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6333c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6333c-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6333c-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6333c-105">Arguments</span></span>  
  
|<span data-ttu-id="6333c-106">Termin</span><span class="sxs-lookup"><span data-stu-id="6333c-106">Term</span></span>|<span data-ttu-id="6333c-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="6333c-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="6333c-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6333c-108">`+` &#124; `-`</span></span>|<span data-ttu-id="6333c-109">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="6333c-109">Optional.</span></span> <span data-ttu-id="6333c-110">Określ `-optioninfer+` , aby włączyć wnioskowanie o typie lokalnym lub `-optioninfer-` je zablokować.</span><span class="sxs-lookup"><span data-stu-id="6333c-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="6333c-111">`-optioninfer`Opcja bez określonej wartości jest taka sama jak `-optioninfer+` .</span><span class="sxs-lookup"><span data-stu-id="6333c-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="6333c-112">Wartość domyślna, gdy `-optioninfer` przełącznik nie jest obecny, jest również `-optioninfer+` .</span><span class="sxs-lookup"><span data-stu-id="6333c-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="6333c-113">Wartość domyślna jest ustawiana w pliku odpowiedzi VBC. rsp.</span><span class="sxs-lookup"><span data-stu-id="6333c-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="6333c-114">Można użyć opcji, `-noconfig` Aby zachować wewnętrzne wartości domyślne kompilatora zamiast opcji określonych w vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="6333c-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="6333c-115">Wartość domyślna kompilatora dla tej opcji to `-optioninfer-` .</span><span class="sxs-lookup"><span data-stu-id="6333c-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6333c-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6333c-116">Remarks</span></span>  

 <span data-ttu-id="6333c-117">Jeśli plik kodu źródłowego zawiera [instrukcję opcji wnioskowania](../../language-reference/statements/option-infer-statement.md), instrukcja zastępuje `-optioninfer` ustawienie kompilatora wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="6333c-117">If the source code file contains an [Option Infer Statement](../../language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="6333c-118">Aby ustawić-optioninfer w środowisku IDE programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6333c-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="6333c-119">Wybierz projekt w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="6333c-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="6333c-120">W menu **projekt** kliknij polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="6333c-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="6333c-121">Na karcie **kompilacja** Zmień wartość w polu **wnioskowanie o opcji** .</span><span class="sxs-lookup"><span data-stu-id="6333c-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6333c-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="6333c-122">Example</span></span>  

 <span data-ttu-id="6333c-123">Poniższy kod kompiluje `test.vb` z włączonym wnioskem o typie lokalnym.</span><span class="sxs-lookup"><span data-stu-id="6333c-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6333c-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6333c-124">See also</span></span>

- [<span data-ttu-id="6333c-125">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6333c-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6333c-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="6333c-126">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="6333c-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="6333c-127">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="6333c-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="6333c-128">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="6333c-129">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="6333c-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="6333c-130">Option Infer — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="6333c-130">Option Infer Statement</span></span>](../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="6333c-131">Wnioskowanie o typie lokalnym</span><span class="sxs-lookup"><span data-stu-id="6333c-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="6333c-132">Domyślne ustawienia programu Visual Basic, Projekty, Opcje — okno dialogowe</span><span class="sxs-lookup"><span data-stu-id="6333c-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="6333c-133">Strona kompilowania, Projektant projektu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6333c-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="6333c-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="6333c-134">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="6333c-135">Tworzenie z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="6333c-135">Building from the Command Line</span></span>](building-from-the-command-line.md)
