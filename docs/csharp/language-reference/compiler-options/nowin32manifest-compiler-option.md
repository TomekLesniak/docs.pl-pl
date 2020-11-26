---
description: -nowin32manifest (opcje kompilatora C#)
title: -nowin32manifest (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 13bbee66901149d54632d9b164431f8898cdf52e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91194001"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="b5c98-103">-nowin32manifest (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="b5c98-103">-nowin32manifest (C# Compiler Options)</span></span>

<span data-ttu-id="b5c98-104">Użyj opcji **-nowin32manifest** , aby nakazać kompilatorowi nie osadzenie żadnego manifestu aplikacji w pliku wykonywalnym.</span><span class="sxs-lookup"><span data-stu-id="b5c98-104">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c98-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b5c98-105">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="b5c98-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b5c98-106">Remarks</span></span>  

 <span data-ttu-id="b5c98-107">Gdy ta opcja jest używana, aplikacja będzie podlegać wirtualizacji w systemie Windows Vista, o ile nie podajesz manifestu aplikacji w pliku zasobów Win32 lub w późniejszym kroku kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b5c98-107">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="b5c98-108">W programie Visual Studio Ustaw tę opcję na stronie **właściwości aplikacji** , wybierając opcję **Utwórz aplikację bez manifestu** na liście rozwijanej **manifestu** .</span><span class="sxs-lookup"><span data-stu-id="b5c98-108">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="b5c98-109">Aby uzyskać więcej informacji, zobacz [Strona aplikacji, Projektant projektu (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="b5c98-109">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="b5c98-110">Aby uzyskać więcej informacji na temat tworzenia manifestu, zobacz [-WIN32MANIFEST (opcje kompilatora C#)](./win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b5c98-110">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c98-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5c98-111">See also</span></span>

- [<span data-ttu-id="b5c98-112">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="b5c98-112">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="b5c98-113">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="b5c98-113">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
