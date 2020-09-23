---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: c6d5e054063592db5777a76fe19da79337ed5034
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084960"
---
# <a name="-win32icon"></a><span data-ttu-id="d730c-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="d730c-102">-win32icon</span></span>

<span data-ttu-id="d730c-103">Wstawia plik. ico w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="d730c-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="d730c-104">Ten plik. ico reprezentuje plik wyjściowy w **Eksploratorze plików**.</span><span class="sxs-lookup"><span data-stu-id="d730c-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d730c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d730c-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="d730c-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d730c-106">Arguments</span></span>  
  
|<span data-ttu-id="d730c-107">Termin</span><span class="sxs-lookup"><span data-stu-id="d730c-107">Term</span></span>|<span data-ttu-id="d730c-108">Definicja</span><span class="sxs-lookup"><span data-stu-id="d730c-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="d730c-109">Plik. ico, który ma zostać dodany do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="d730c-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="d730c-110">Nazwa pliku należy ująć w cudzysłów (""), jeśli zawiera spację.</span><span class="sxs-lookup"><span data-stu-id="d730c-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d730c-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d730c-111">Remarks</span></span>  

 <span data-ttu-id="d730c-112">Plik. ico można utworzyć za pomocą kompilatora zasobów systemu Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="d730c-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="d730c-113">Kompilator zasobów jest wywoływany podczas kompilowania programu Visual C++owego; plik. ico jest tworzony na podstawie pliku. rc.</span><span class="sxs-lookup"><span data-stu-id="d730c-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="d730c-114">`-win32icon`Opcje i `-win32resource` wzajemnie się wykluczają.</span><span class="sxs-lookup"><span data-stu-id="d730c-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="d730c-115">Zobacz [-linkresource — (Visual Basic)](linkresource.md) , aby odwołać się do .NET Framework pliku zasobów, lub [-Resource (Visual Basic)](resource.md) , aby dołączyć plik zasobów .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d730c-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="d730c-116">Aby zaimportować plik. res, zobacz temat [-win32resource](win32resource.md) .</span><span class="sxs-lookup"><span data-stu-id="d730c-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="d730c-117">Aby ustawić-win32icon w środowisku IDE programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d730c-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="d730c-118">1. zaznaczono projekt w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="d730c-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d730c-119">W menu **projekt** kliknij polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="d730c-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d730c-120">2. Kliknij kartę **aplikacja** .</span><span class="sxs-lookup"><span data-stu-id="d730c-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="d730c-121">3. Zmodyfikuj wartość w polu **ikony** .</span><span class="sxs-lookup"><span data-stu-id="d730c-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d730c-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="d730c-122">Example</span></span>  

 <span data-ttu-id="d730c-123">Poniższy kod kompiluje `In.vb` i dołącza plik. ico, `Rf.ico` .</span><span class="sxs-lookup"><span data-stu-id="d730c-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d730c-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d730c-124">See also</span></span>

- [<span data-ttu-id="d730c-125">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d730c-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d730c-126">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="d730c-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
