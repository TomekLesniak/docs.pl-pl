---
description: — zaznaczone (opcje kompilatora C#)
title: — zaznaczone (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: 5c90696edd3031271e16cd2c1a332da5b605f81f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125946"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="639da-103">— zaznaczone (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="639da-103">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="639da-104">Opcja **-** Check określa, czy instrukcja arytmetyczna liczb całkowitych, która skutkuje wartością, która jest poza zakresem danych, i która nie jest w zakresie [zaznaczonego](../keywords/checked.md) lub [niesprawdzonego](../keywords/unchecked.md) słowa kluczowego, powoduje wyjątek czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="639da-104">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../keywords/checked.md) or [unchecked](../keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639da-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="639da-105">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="639da-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="639da-106">Remarks</span></span>  
 <span data-ttu-id="639da-107">Instrukcja arytmetyczna liczb całkowitych, która znajduje się w `checked` zakresie `unchecked` słowa kluczowego or, nie podlega wpływowi opcji **-Checked** .</span><span class="sxs-lookup"><span data-stu-id="639da-107">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="639da-108">Jeśli instrukcja arytmetyczna liczb całkowitych, która nie znajduje się w `checked` zakresie `unchecked` słowa kluczowego lub, powoduje użycie wartości spoza zakresu typu danych i **-Checked +** (lub **-Checked**) jest używana w kompilacji, ta instrukcja powoduje wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="639da-108">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="639da-109">Jeśli **jest** używana w kompilacji, ta instrukcja nie powoduje wyjątku w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="639da-109">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="639da-110">Wartość domyślna dla tej opcji to **-Checked-**; Sprawdzanie przepełnienia jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="639da-110">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>

 <span data-ttu-id="639da-111">Czasami zautomatyzowane narzędzia, które są używane do kompilowania zestawu dużych aplikacji, są sprawdzane w programie +.</span><span class="sxs-lookup"><span data-stu-id="639da-111">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="639da-112">Jednym z scenariuszy użycia-checked-jest zastąpienie globalnego domyślnego narzędzia przez określenie-checked-.</span><span class="sxs-lookup"><span data-stu-id="639da-112">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="639da-113">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="639da-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="639da-114">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="639da-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="639da-115">Aby uzyskać więcej informacji, zobacz [stronę Kompilacja, Projektant projektu (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="639da-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="639da-116">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="639da-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="639da-117">Kliknij przycisk **Zaawansowane** .</span><span class="sxs-lookup"><span data-stu-id="639da-117">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="639da-118">Zmodyfikuj właściwość **sprawdzania przepełnienia arytmetycznego** .</span><span class="sxs-lookup"><span data-stu-id="639da-118">Modify the **Check for arithmetic overflow** property.</span></span>  
  
 <span data-ttu-id="639da-119">Aby programowo uzyskać dostęp do tej opcji kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A> .</span><span class="sxs-lookup"><span data-stu-id="639da-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="639da-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="639da-120">Example</span></span>  
 <span data-ttu-id="639da-121">Następujące polecenie kompiluje `t2.cs` .</span><span class="sxs-lookup"><span data-stu-id="639da-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="639da-122">Użycie `-checked` w poleceniu określa, że jakakolwiek instrukcja arytmetyczna liczb całkowitych w pliku, który nie jest w zakresie `checked` `unchecked` słowa kluczowego or, i powoduje, że wartość jest spoza zakresu typu danych, powoduje wyjątek w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="639da-122">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="639da-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="639da-123">See also</span></span>

- [<span data-ttu-id="639da-124">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="639da-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="639da-125">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="639da-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
