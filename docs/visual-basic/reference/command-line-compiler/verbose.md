---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: c5bf988d819a8df8aed99588abbb30e19d14b1ac
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084986"
---
# <a name="-verbose"></a><span data-ttu-id="905a7-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="905a7-102">-verbose</span></span>

<span data-ttu-id="905a7-103">Powoduje, że kompilator tworzy pełny stan i komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="905a7-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="905a7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="905a7-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="905a7-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="905a7-105">Arguments</span></span>  

 <span data-ttu-id="905a7-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="905a7-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="905a7-107">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="905a7-107">Optional.</span></span> <span data-ttu-id="905a7-108">Określanie `-verbose` jest takie samo jak określanie `-verbose+` , co powoduje, że kompilator emituje pełne komunikaty.</span><span class="sxs-lookup"><span data-stu-id="905a7-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="905a7-109">Wartość domyślna dla tej opcji to `-verbose-` .</span><span class="sxs-lookup"><span data-stu-id="905a7-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="905a7-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="905a7-110">Remarks</span></span>  

 <span data-ttu-id="905a7-111">`-verbose`Opcja wyświetla informacje o całkowitej liczbie błędów wydanych przez kompilator, raporty, które zestawy są ładowane przez moduł, i wyświetla pliki, które są obecnie kompilowane.</span><span class="sxs-lookup"><span data-stu-id="905a7-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="905a7-112">`-verbose`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="905a7-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="905a7-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="905a7-113">Example</span></span>  

 <span data-ttu-id="905a7-114">Poniższy kod kompiluje `In.vb` i kieruje kompilator, aby wyświetlić pełne informacje o stanie.</span><span class="sxs-lookup"><span data-stu-id="905a7-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="905a7-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="905a7-115">See also</span></span>

- [<span data-ttu-id="905a7-116">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="905a7-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="905a7-117">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="905a7-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
