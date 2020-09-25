---
description: -win32icon (opcje kompilatora C#)
title: -win32icon (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 5b62bbfe28bb5aa82605a88a83cf82eff9278807
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168871"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="d7336-103">-win32icon (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="d7336-103">-win32icon (C# Compiler Options)</span></span>

<span data-ttu-id="d7336-104">Opcja **-win32icon** wstawia plik. ico w pliku wyjściowym, co daje plikowi wyjściowemu odpowiedni wygląd w Eksploratorze plików.</span><span class="sxs-lookup"><span data-stu-id="d7336-104">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7336-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d7336-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7336-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d7336-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="d7336-107">Plik ICO, który ma zostać dodany do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="d7336-107">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7336-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d7336-108">Remarks</span></span>  

 <span data-ttu-id="d7336-109">Plik. ico można utworzyć za pomocą [kompilatora zasobów](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="d7336-109">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="d7336-110">Kompilator zasobów jest wywoływany podczas kompilowania programu Visual C++owego; plik. ico jest tworzony na podstawie pliku. rc.</span><span class="sxs-lookup"><span data-stu-id="d7336-110">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="d7336-111">Zobacz [-linkresource —](./linkresource-compiler-option.md) (to Reference) lub [-Resource](./resource-compiler-option.md) (aby dołączyć) .NET Framework plik zasobów.</span><span class="sxs-lookup"><span data-stu-id="d7336-111">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="d7336-112">Aby zaimportować plik. res, zobacz temat [-win32res —](./win32res-compiler-option.md) .</span><span class="sxs-lookup"><span data-stu-id="d7336-112">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d7336-113">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7336-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="d7336-114">Otwórz strony **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="d7336-114">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="d7336-115">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="d7336-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="d7336-116">Zmodyfikuj właściwość **ikony aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="d7336-116">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="d7336-117">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A> .</span><span class="sxs-lookup"><span data-stu-id="d7336-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7336-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="d7336-118">Example</span></span>  

 <span data-ttu-id="d7336-119">Kompiluj `in.cs` i Dołącz plik. ico `rf.ico` do produkcji `in.exe` :</span><span class="sxs-lookup"><span data-stu-id="d7336-119">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7336-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d7336-120">See also</span></span>

- [<span data-ttu-id="d7336-121">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="d7336-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d7336-122">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="d7336-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
