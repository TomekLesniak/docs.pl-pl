---
title: Option Explicit, instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 44bf8205ec071710ee3660968ab3c3e9af33f74d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874946"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="72bdd-102">Option Explicit — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72bdd-102">Option Explicit Statement (Visual Basic)</span></span>

<span data-ttu-id="72bdd-103">Wymusza jawną deklarację wszystkich zmiennych w pliku lub zezwala na niejawne deklaracje zmiennych.</span><span class="sxs-lookup"><span data-stu-id="72bdd-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bdd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="72bdd-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="72bdd-105">Części</span><span class="sxs-lookup"><span data-stu-id="72bdd-105">Parts</span></span>  

 `On`  
 <span data-ttu-id="72bdd-106">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="72bdd-106">Optional.</span></span> <span data-ttu-id="72bdd-107">Włącza `Option Explicit` Sprawdzanie.</span><span class="sxs-lookup"><span data-stu-id="72bdd-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="72bdd-108">Jeśli `On` lub `Off` nie jest określony, wartość domyślna to `On` .</span><span class="sxs-lookup"><span data-stu-id="72bdd-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="72bdd-109">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="72bdd-109">Optional.</span></span> <span data-ttu-id="72bdd-110">Wyłącza `Option Explicit` Sprawdzanie.</span><span class="sxs-lookup"><span data-stu-id="72bdd-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72bdd-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="72bdd-111">Remarks</span></span>  

 <span data-ttu-id="72bdd-112">Gdy `Option Explicit On` lub `Option Explicit` pojawia się w pliku, należy jawnie zadeklarować wszystkie zmienne przy użyciu `Dim` instrukcji or `ReDim` .</span><span class="sxs-lookup"><span data-stu-id="72bdd-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="72bdd-113">Jeśli spróbujesz użyć niezadeklarowanej nazwy zmiennej, wystąpi błąd w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="72bdd-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="72bdd-114">`Option Explicit Off`Instrukcja umożliwia niejawną deklarację zmiennych.</span><span class="sxs-lookup"><span data-stu-id="72bdd-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="72bdd-115">Jeśli jest używana, `Option Explicit` instrukcja musi pojawić się w pliku przed innymi instrukcjami kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="72bdd-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72bdd-116">Ustawienie `Option Explicit` na `Off` ogół nie jest dobrym sposobem.</span><span class="sxs-lookup"><span data-stu-id="72bdd-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="72bdd-117">W co najmniej jednej lokalizacji można wypróbować nazwę zmiennej, co spowodowałoby nieoczekiwane wyniki, gdy program zostanie uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="72bdd-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="72bdd-118">Gdy nie ma instrukcji Option Explicit</span><span class="sxs-lookup"><span data-stu-id="72bdd-118">When an Option Explicit Statement Is Not Present</span></span>  

 <span data-ttu-id="72bdd-119">Jeśli kod źródłowy nie zawiera `Option Explicit` instrukcji, zostanie użyta **opcja jawne** ustawienie na [stronie kompilowania, Projektant projektu (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="72bdd-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="72bdd-120">Jeśli jest używany kompilator wiersza polecenia, opcja kompilatora [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) jest używana.</span><span class="sxs-lookup"><span data-stu-id="72bdd-120">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="72bdd-121">Aby ustawić opcję jawną w środowisku IDE</span><span class="sxs-lookup"><span data-stu-id="72bdd-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="72bdd-122">W **Eksplorator rozwiązań**wybierz projekt.</span><span class="sxs-lookup"><span data-stu-id="72bdd-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="72bdd-123">W menu **projekt** kliknij polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="72bdd-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="72bdd-124">Kliknij kartę **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="72bdd-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="72bdd-125">Ustaw wartość w polu **opcja jawna** .</span><span class="sxs-lookup"><span data-stu-id="72bdd-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="72bdd-126">Podczas tworzenia nowego projektu **opcja ustawienie jawne** na karcie **kompilowania** jest ustawiona na wartość ustawienie **jawne** w oknie dialogowym **Ustawienia domyślne języka vb** .</span><span class="sxs-lookup"><span data-stu-id="72bdd-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="72bdd-127">Aby uzyskać dostęp do okna dialogowego **Ustawienia domyślne VB** , w menu **Narzędzia** kliknij polecenie **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="72bdd-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="72bdd-128">W oknie dialogowym **Opcje** rozwiń węzeł **projekty i rozwiązania**, a następnie kliknij pozycję **Ustawienia domyślne w języku VB**.</span><span class="sxs-lookup"><span data-stu-id="72bdd-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="72bdd-129">Początkowe domyślne ustawienie w **języku VB** domyślnie ma wartość `On` .</span><span class="sxs-lookup"><span data-stu-id="72bdd-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="72bdd-130">Aby ustawić opcję jawną w wierszu polecenia</span><span class="sxs-lookup"><span data-stu-id="72bdd-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="72bdd-131">Dołącz opcję kompilatora [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) w poleceniu **VBC** .</span><span class="sxs-lookup"><span data-stu-id="72bdd-131">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72bdd-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="72bdd-132">Example</span></span>  

 <span data-ttu-id="72bdd-133">Poniższy przykład używa instrukcji, `Option Explicit` Aby wymusić jawną deklarację wszystkich zmiennych.</span><span class="sxs-lookup"><span data-stu-id="72bdd-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="72bdd-134">Próba użycia niezadeklarowanej zmiennej powoduje błąd w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="72bdd-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="72bdd-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72bdd-135">See also</span></span>

- [<span data-ttu-id="72bdd-136">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="72bdd-136">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="72bdd-137">ReDim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="72bdd-137">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="72bdd-138">Option Compare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="72bdd-138">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="72bdd-139">Option Strict — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="72bdd-139">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="72bdd-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="72bdd-140">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="72bdd-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="72bdd-141">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="72bdd-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="72bdd-142">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="72bdd-143">Domyślne ustawienia programu Visual Basic, Projekty, Opcje — okno dialogowe</span><span class="sxs-lookup"><span data-stu-id="72bdd-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
