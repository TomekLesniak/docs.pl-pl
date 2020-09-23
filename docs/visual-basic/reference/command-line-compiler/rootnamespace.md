---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: d9388ace03f654458eb955e989673b7441e72f23
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085142"
---
# <a name="-rootnamespace"></a><span data-ttu-id="d73f9-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="d73f9-102">-rootnamespace</span></span>

<span data-ttu-id="d73f9-103">Określa przestrzeń nazw dla wszystkich deklaracji typu.</span><span class="sxs-lookup"><span data-stu-id="d73f9-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d73f9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d73f9-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="d73f9-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d73f9-105">Arguments</span></span>  
  
|<span data-ttu-id="d73f9-106">Termin</span><span class="sxs-lookup"><span data-stu-id="d73f9-106">Term</span></span>|<span data-ttu-id="d73f9-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="d73f9-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="d73f9-108">Nazwa przestrzeni nazw, w której należy ująć wszystkie deklaracje typu dla bieżącego projektu.</span><span class="sxs-lookup"><span data-stu-id="d73f9-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d73f9-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d73f9-109">Remarks</span></span>  

 <span data-ttu-id="d73f9-110">Jeśli używasz pliku wykonywalnego programu Visual Studio (Devenv.exe) do kompilowania projektu utworzonego w zintegrowanym środowisku programistycznym programu Visual Studio, użyj, `-rootnamespace` Aby określić wartość <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="d73f9-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="d73f9-111">Zobacz [przełączniki wiersza polecenia devenv](/visualstudio/ide/reference/devenv-command-line-switches) , aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="d73f9-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="d73f9-112">Użyj Dezasembler MSIL () środowiska uruchomieniowego języka wspólnego, `Ildasm.exe` Aby wyświetlić nazwy przestrzeni nazw w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="d73f9-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="d73f9-113">Aby ustawić-RootNamespace w zintegrowanym środowisku programistycznym programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d73f9-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d73f9-114">1. zaznaczono projekt w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="d73f9-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d73f9-115">W menu **projekt** kliknij polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="d73f9-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d73f9-116">2. Kliknij kartę **aplikacja** .</span><span class="sxs-lookup"><span data-stu-id="d73f9-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="d73f9-117">3. Zmodyfikuj wartość w polu **główna przestrzeń nazw** .</span><span class="sxs-lookup"><span data-stu-id="d73f9-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d73f9-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="d73f9-118">Example</span></span>  

 <span data-ttu-id="d73f9-119">Poniższy kod kompiluje `In.vb` i ujmuje wszystkie deklaracje typów w przestrzeni nazw `mynamespace` .</span><span class="sxs-lookup"><span data-stu-id="d73f9-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d73f9-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d73f9-120">See also</span></span>

- [<span data-ttu-id="d73f9-121">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d73f9-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d73f9-122">Ildasm.exe (IL dezasembler)</span><span class="sxs-lookup"><span data-stu-id="d73f9-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="d73f9-123">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="d73f9-123">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
