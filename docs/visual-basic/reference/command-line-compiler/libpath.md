---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: a91bd74d0be4f1cb223091ee2527f9567b4ca5db
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058472"
---
# <a name="-libpath"></a><span data-ttu-id="f5d6d-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="f5d6d-102">-libpath</span></span>

<span data-ttu-id="f5d6d-103">Określa lokalizację przywoływanych zestawów.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d6d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f5d6d-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f5d6d-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f5d6d-105">Arguments</span></span>  
  
|<span data-ttu-id="f5d6d-106">Termin</span><span class="sxs-lookup"><span data-stu-id="f5d6d-106">Term</span></span>|<span data-ttu-id="f5d6d-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="f5d6d-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="f5d6d-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-108">Required.</span></span> <span data-ttu-id="f5d6d-109">Rozdzielana średnikami lista katalogów, które mają być używane przez kompilator, jeśli zestaw, do którego się odwoływano, nie został znaleziony w bieżącym katalogu roboczym (katalog, z którego prowadzisz kompilator) lub katalog systemowy środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="f5d6d-110">Jeśli nazwa katalogu zawiera spację, należy ująć ją w cudzysłów ("").</span><span class="sxs-lookup"><span data-stu-id="f5d6d-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5d6d-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f5d6d-111">Remarks</span></span>  

 <span data-ttu-id="f5d6d-112">`-libpath`Opcja określa lokalizację zestawów, do których odwołuje się opcja [-Reference](reference.md) .</span><span class="sxs-lookup"><span data-stu-id="f5d6d-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](reference.md) option.</span></span>  
  
 <span data-ttu-id="f5d6d-113">Kompilator wyszukuje odwołania do zestawów, które nie są w pełni kwalifikowane w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="f5d6d-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="f5d6d-114">Bieżący katalog roboczy.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-114">Current working directory.</span></span> <span data-ttu-id="f5d6d-115">Jest to katalog, z którego wywołano kompilator.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="f5d6d-116">Katalog systemowy środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="f5d6d-117">Katalogi określone przez `-libpath` .</span><span class="sxs-lookup"><span data-stu-id="f5d6d-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="f5d6d-118">Katalogi określone przez zmienną środowiskową LIB.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="f5d6d-119">`-libpath`Opcja jest dodatkiem; określenie, że więcej niż raz dołącza do poprzednich wartości.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="f5d6d-120">Użyj `-reference` , aby określić odwołanie do zestawu.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="f5d6d-121">Aby ustawić-LIBPATH w zintegrowanym środowisku programistycznym programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f5d6d-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f5d6d-122">1. zaznaczono projekt w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f5d6d-123">W menu **projekt** kliknij polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f5d6d-124">2. Kliknij kartę **odwołania** .</span><span class="sxs-lookup"><span data-stu-id="f5d6d-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="f5d6d-125">3. kliknij przycisk **ścieżki odwołania...** .</span><span class="sxs-lookup"><span data-stu-id="f5d6d-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="f5d6d-126">4. w oknie dialogowym **ścieżki odwołań** wprowadź nazwę katalogu w polu **folder:** .</span><span class="sxs-lookup"><span data-stu-id="f5d6d-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="f5d6d-127">5. kliknij pozycję **Dodaj folder**.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5d6d-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="f5d6d-128">Example</span></span>  

 <span data-ttu-id="f5d6d-129">Poniższy kod kompiluje `T2.vb` się w celu utworzenia pliku. exe.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="f5d6d-130">Kompilator przeszukuje katalog roboczy, w katalogu głównym dysku C: i w nowym katalogu zestawów dysku C: na potrzeby odwołań do zestawu.</span><span class="sxs-lookup"><span data-stu-id="f5d6d-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5d6d-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f5d6d-131">See also</span></span>

- [<span data-ttu-id="f5d6d-132">Zestawy w środowisku .NET</span><span class="sxs-lookup"><span data-stu-id="f5d6d-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="f5d6d-133">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5d6d-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f5d6d-134">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="f5d6d-134">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
