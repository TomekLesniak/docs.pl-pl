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
ms.openlocfilehash: c220c78a6d2c3109402a20f0de40fe9665d6c730
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140818"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="f7578-103">-win32res — (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="f7578-103">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="f7578-104">Opcja **-win32res —** wstawia zasób Win32 do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="f7578-104">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7578-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f7578-105">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f7578-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f7578-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="f7578-107">Plik zasobu, który ma zostać dodany do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="f7578-107">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7578-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f7578-108">Remarks</span></span>  
 <span data-ttu-id="f7578-109">Plik zasobów Win32 można utworzyć za pomocą [kompilatora zasobów](resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f7578-109">A Win32 resource file can be created with the [Resource Compiler](resource-compiler-option.md).</span></span> <span data-ttu-id="f7578-110">Kompilator zasobów jest wywoływany podczas kompilacji programów Visual C++; plik .res jest tworzony z pliku .rc.</span><span class="sxs-lookup"><span data-stu-id="f7578-110">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="f7578-111">Zasób Win32 może zawierać informacje o wersji lub mapie bitowej (ikony), które ułatwią zidentyfikowanie aplikacji w Eksploratorze plików.</span><span class="sxs-lookup"><span data-stu-id="f7578-111">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="f7578-112">Jeśli nie określisz **win32res —**, kompilator generuje informacje o wersji na podstawie wersji zestawu.</span><span class="sxs-lookup"><span data-stu-id="f7578-112">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="f7578-113">Zobacz [-linkresource —](./linkresource-compiler-option.md) (to Reference) lub [-Resource](./resource-compiler-option.md) (aby dołączyć) .NET Framework plik zasobów.</span><span class="sxs-lookup"><span data-stu-id="f7578-113">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f7578-114">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f7578-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f7578-115">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="f7578-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="f7578-116">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="f7578-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="f7578-117">Kliknij przycisk **plik zasobów** , a następnie wybierz plik za pomocą pola kombi.</span><span class="sxs-lookup"><span data-stu-id="f7578-117">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7578-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="f7578-118">Example</span></span>  
 <span data-ttu-id="f7578-119">Kompiluj `in.cs` i Dołącz plik zasobów Win32 `rf.res` do produkcji `in.exe` :</span><span class="sxs-lookup"><span data-stu-id="f7578-119">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7578-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7578-120">See also</span></span>

- [<span data-ttu-id="f7578-121">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="f7578-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f7578-122">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="f7578-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
