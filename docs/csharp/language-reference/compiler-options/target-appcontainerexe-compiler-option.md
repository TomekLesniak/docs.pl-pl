---
description: '-target: appcontainerexe (opcje kompilatora C#)'
title: '-target: appcontainerexe (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: e4aa60ebc9dcc1a63b63863385b0ee9f13d6d78d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193741"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="22091-103">-target: appcontainerexe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="22091-103">-target:appcontainerexe (C# Compiler Options)</span></span>

<span data-ttu-id="22091-104">W przypadku użycia opcji kompilatora **-target: appcontainerexe** kompilator tworzy plik wykonywalny systemu Windows (exe), który musi być uruchamiany w kontenerze aplikacji.</span><span class="sxs-lookup"><span data-stu-id="22091-104">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="22091-105">Ta opcja jest równoznaczna z parametrem [-target: winexe](./target-winexe-compiler-option.md) , ale jest przeznaczona dla aplikacji ze sklepu Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="22091-105">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22091-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="22091-106">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="22091-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="22091-107">Remarks</span></span>  

 <span data-ttu-id="22091-108">Aby wymagać uruchamiania aplikacji w kontenerze aplikacji, ta opcja ustawia bit w [przenośnym pliku wykonywalnym](/windows/desktop/Debug/pe-format) (PE).</span><span class="sxs-lookup"><span data-stu-id="22091-108">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="22091-109">Gdy ten bit jest ustawiony, występuje błąd, jeśli metoda CreateProcess podejmie próbę uruchomienia pliku wykonywalnego poza kontenerem aplikacji.</span><span class="sxs-lookup"><span data-stu-id="22091-109">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="22091-110">O ile nie zostanie użyta opcja [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera metodę [Main](../../programming-guide/main-and-command-args/index.md) .</span><span class="sxs-lookup"><span data-stu-id="22091-110">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="22091-111">Po określeniu tej opcji w wierszu polecenia wszystkie pliki do momentu użycia opcji **Dalej lub** **-Target** są używane do tworzenia pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="22091-111">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="22091-112">Aby ustawić tę opcję kompilatora w IDE</span><span class="sxs-lookup"><span data-stu-id="22091-112">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="22091-113">W **Eksplorator rozwiązań**Otwórz menu skrótów dla projektu, a następnie wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="22091-113">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="22091-114">Na karcie **aplikacja** na liście **Typ danych wyjściowych** wybierz pozycję **aplikacja ze sklepu Windows**.</span><span class="sxs-lookup"><span data-stu-id="22091-114">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="22091-115">Ta opcja jest dostępna tylko dla szablonów aplikacji ze sklepu Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="22091-115">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="22091-116">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="22091-116">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22091-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="22091-117">Example</span></span>  

 <span data-ttu-id="22091-118">Następujące polecenie kompiluje `filename.cs` do pliku wykonywalnego systemu Windows, który można uruchomić tylko w kontenerze aplikacji.</span><span class="sxs-lookup"><span data-stu-id="22091-118">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="22091-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="22091-119">See also</span></span>

- [<span data-ttu-id="22091-120">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="22091-120">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="22091-121">-target: winexe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="22091-121">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="22091-122">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="22091-122">C# Compiler Options</span></span>](./index.md)
