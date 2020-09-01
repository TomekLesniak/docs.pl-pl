---
description: '-target: winmdobj (opcje kompilatora C#)'
title: '-target: winmdobj (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 66a4bddb34832705ad4779829e561afd9442be8f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139089"
---
# <a name="-targetwinmdobj-c-compiler-options"></a><span data-ttu-id="168fd-103">-target: winmdobj (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="168fd-103">-target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="168fd-104">W przypadku użycia opcji kompilatora **-target: winmdobj** kompilator tworzy plik pośredni. winmdobj, który można przekonwertować na środowisko wykonawcze systemu Windows plik binarny (. winmd).</span><span class="sxs-lookup"><span data-stu-id="168fd-104">If you use the **-target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="168fd-105">Plik. winmd może być następnie używany przez programy JavaScript i C++, a także do programów języka zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="168fd-105">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="168fd-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="168fd-106">Syntax</span></span>  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="168fd-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="168fd-107">Remarks</span></span>  
 <span data-ttu-id="168fd-108">Ustawienie **winmdobj** sygnalizuje kompilatorowi, że wymagany jest moduł pośredni.</span><span class="sxs-lookup"><span data-stu-id="168fd-108">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="168fd-109">W odpowiedzi program Visual Studio kompiluje bibliotekę klas C# jako plik. winmdobj.</span><span class="sxs-lookup"><span data-stu-id="168fd-109">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="168fd-110">Plik. winmdobj można następnie uzyskać za pomocą <xref:Microsoft.Build.Tasks.WinMDExp> narzędzia eksportu w celu utworzenia pliku metadanych systemu Windows (WinMD).</span><span class="sxs-lookup"><span data-stu-id="168fd-110">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="168fd-111">Plik. winmd zawiera zarówno kod z oryginalnej biblioteki, jak i metadane WinMD, które są używane przez skrypty JavaScript lub C++ i środowisko wykonawcze systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="168fd-111">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="168fd-112">Dane wyjściowe pliku, który jest kompilowany przy użyciu opcji **-target: winmdobj** kompilatora, jest przeznaczony do użycia tylko jako dane wejściowe dla narzędzia eksportu WimMDExp; sam plik. winmdobj nie jest bezpośrednio przywoływany.</span><span class="sxs-lookup"><span data-stu-id="168fd-112">The output of a file that’s compiled by using the **-target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="168fd-113">O ile nie zostanie użyta opcja [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pierwszego pliku wejściowego.</span><span class="sxs-lookup"><span data-stu-id="168fd-113">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="168fd-114">Metoda [Main](../../programming-guide/main-and-command-args/index.md) nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="168fd-114">A [Main](../../programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="168fd-115">W przypadku określenia opcji-target: winmdobj w wierszu polecenia wszystkie pliki do momentu, w którym zostanie użyta opcja modułu "Następny **-out** " lub ["target: module"](./target-module-compiler-option.md) , są używane do tworzenia programu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="168fd-115">If you specify the -target:winmdobj option at a command prompt, all files until the next **-out** or [-target:module](./target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="168fd-116">Aby ustawić tę opcję kompilatora w programie Visual Studio IDE dla aplikacji magazynu systemu Windows</span><span class="sxs-lookup"><span data-stu-id="168fd-116">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1. <span data-ttu-id="168fd-117">W **Eksplorator rozwiązań**Otwórz menu skrótów dla projektu, a następnie wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="168fd-117">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="168fd-118">Wybierz kartę **aplikacja** .</span><span class="sxs-lookup"><span data-stu-id="168fd-118">Choose the **Application** tab.</span></span>  
  
3. <span data-ttu-id="168fd-119">Na liście **Typ danych wyjściowych** wybierz pozycję **plik WinMD**.</span><span class="sxs-lookup"><span data-stu-id="168fd-119">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="168fd-120">Opcja **plik WinMD** jest dostępna tylko dla szablonów aplikacji ze sklepu Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="168fd-120">The **WinMD File** option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="168fd-121">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="168fd-121">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="168fd-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="168fd-122">Example</span></span>  
 <span data-ttu-id="168fd-123">Następujące polecenie kompiluje `filename.cs` do pośredniego pliku. winmdobj.</span><span class="sxs-lookup"><span data-stu-id="168fd-123">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="168fd-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="168fd-124">See also</span></span>

- [<span data-ttu-id="168fd-125">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="168fd-125">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="168fd-126">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="168fd-126">C# Compiler Options</span></span>](./index.md)
