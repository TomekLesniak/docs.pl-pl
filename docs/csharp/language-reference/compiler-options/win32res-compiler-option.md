---
description: -win32res — (opcje kompilatora C#)
title: -win32res — (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 442c788595a01db9c0a1196d9e13b2a98963a38c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91204349"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="9a852-103">-win32res — (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="9a852-103">-win32res (C# Compiler Options)</span></span>

<span data-ttu-id="9a852-104">Opcja **-win32res —** wstawia zasób Win32 do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="9a852-104">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a852-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a852-105">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a852-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9a852-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="9a852-107">Plik zasobu, który ma zostać dodany do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="9a852-107">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a852-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9a852-108">Remarks</span></span>  

 <span data-ttu-id="9a852-109">Plik zasobów Win32 można utworzyć za pomocą [kompilatora zasobów](resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9a852-109">A Win32 resource file can be created with the [Resource Compiler](resource-compiler-option.md).</span></span> <span data-ttu-id="9a852-110">Kompilator zasobów jest wywoływany podczas kompilacji programów Visual C++; plik .res jest tworzony z pliku .rc.</span><span class="sxs-lookup"><span data-stu-id="9a852-110">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="9a852-111">Zasób Win32 może zawierać informacje o wersji lub mapie bitowej (ikony), które ułatwią zidentyfikowanie aplikacji w Eksploratorze plików.</span><span class="sxs-lookup"><span data-stu-id="9a852-111">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="9a852-112">Jeśli nie określisz **win32res —**, kompilator generuje informacje o wersji na podstawie wersji zestawu.</span><span class="sxs-lookup"><span data-stu-id="9a852-112">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="9a852-113">Zobacz [-linkresource —](./linkresource-compiler-option.md) (to Reference) lub [-Resource](./resource-compiler-option.md) (aby dołączyć) .NET Framework plik zasobów.</span><span class="sxs-lookup"><span data-stu-id="9a852-113">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9a852-114">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9a852-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="9a852-115">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="9a852-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="9a852-116">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="9a852-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="9a852-117">Kliknij przycisk **plik zasobów** , a następnie wybierz plik za pomocą pola kombi.</span><span class="sxs-lookup"><span data-stu-id="9a852-117">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a852-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="9a852-118">Example</span></span>  

 <span data-ttu-id="9a852-119">Kompiluj `in.cs` i Dołącz plik zasobów Win32 `rf.res` do produkcji `in.exe` :</span><span class="sxs-lookup"><span data-stu-id="9a852-119">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a852-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a852-120">See also</span></span>

- [<span data-ttu-id="9a852-121">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="9a852-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9a852-122">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="9a852-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
