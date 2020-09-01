---
description: -filealign (opcje kompilatora C#)
title: -filealign (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: d4abe6c3825de211d737f402a745c8953adca4b8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125712"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="ae081-103">-filealign (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="ae081-103">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="ae081-104">Opcja **-filealign** umożliwia określenie rozmiaru sekcji w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="ae081-104">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae081-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ae081-105">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae081-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ae081-106">Arguments</span></span>  
 `number`  
 <span data-ttu-id="ae081-107">Wartość określająca rozmiar sekcji w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="ae081-107">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="ae081-108">Prawidłowe wartości to 512, 1024, 2048, 4096 i 8192.</span><span class="sxs-lookup"><span data-stu-id="ae081-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="ae081-109">Te wartości są w bajtach.</span><span class="sxs-lookup"><span data-stu-id="ae081-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae081-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ae081-110">Remarks</span></span>  
 <span data-ttu-id="ae081-111">Każda sekcja zostanie wyrównana na granicy, która jest wielokrotnością wartości **filealign** .</span><span class="sxs-lookup"><span data-stu-id="ae081-111">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="ae081-112">Nie ma żadnych stałych ustawień domyślnych.</span><span class="sxs-lookup"><span data-stu-id="ae081-112">There is no fixed default.</span></span> <span data-ttu-id="ae081-113">Jeśli nie określono parametru **-filealign** , środowisko uruchomieniowe języka wspólnego wybiera wartość domyślną w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ae081-113">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="ae081-114">Określenie rozmiaru sekcji wpływa na rozmiar pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="ae081-114">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="ae081-115">Modyfikowanie rozmiaru sekcji może być przydatne w przypadku programów, które będą uruchamiane na mniejszych urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="ae081-115">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="ae081-116">Użyj [polecenia DUMPBIN](/cpp/build/reference/dumpbin-options) , aby wyświetlić informacje o sekcjach w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="ae081-116">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ae081-117">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae081-117">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ae081-118">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="ae081-118">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="ae081-119">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="ae081-119">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="ae081-120">Kliknij przycisk **Zaawansowane** .</span><span class="sxs-lookup"><span data-stu-id="ae081-120">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="ae081-121">Zmodyfikuj właściwość **wyrównania pliku** .</span><span class="sxs-lookup"><span data-stu-id="ae081-121">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="ae081-122">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A> .</span><span class="sxs-lookup"><span data-stu-id="ae081-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae081-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ae081-123">See also</span></span>

- [<span data-ttu-id="ae081-124">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="ae081-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ae081-125">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="ae081-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
