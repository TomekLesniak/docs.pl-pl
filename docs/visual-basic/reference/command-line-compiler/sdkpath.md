---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 18bf22861c1cbc3a37ef917b421491c2d01efba8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085116"
---
# <a name="-sdkpath"></a><span data-ttu-id="4de29-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="4de29-102">-sdkpath</span></span>

<span data-ttu-id="4de29-103">Określa lokalizację mscorlib.dll i Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="4de29-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de29-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4de29-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="4de29-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="4de29-105">Arguments</span></span>  

 `path`  
 <span data-ttu-id="4de29-106">Katalog zawierający wersje mscorlib.dll i Microsoft.VisualBasic.dll do użycia podczas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="4de29-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="4de29-107">Ta ścieżka nie jest weryfikowana, dopóki nie zostanie załadowana.</span><span class="sxs-lookup"><span data-stu-id="4de29-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="4de29-108">Nazwa katalogu powinna być ujęta w cudzysłów (""), jeśli zawiera spację.</span><span class="sxs-lookup"><span data-stu-id="4de29-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4de29-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4de29-109">Remarks</span></span>  

 <span data-ttu-id="4de29-110">Ta opcja nakazuje kompilatorowi Visual Basic załadowanie plików mscorlib.dll i Microsoft.VisualBasic.dll z lokalizacji innej niż domyślna.</span><span class="sxs-lookup"><span data-stu-id="4de29-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="4de29-111">`-sdkpath`Opcja została zaprojektowana tak, aby była używana z [-netcf](netcf.md).</span><span class="sxs-lookup"><span data-stu-id="4de29-111">The `-sdkpath` option was designed to be used with [-netcf](netcf.md).</span></span> <span data-ttu-id="4de29-112">.NET Compact Framework wykorzystuje różne wersje tych bibliotek, aby uniknąć używania typów i funkcji języka, które nie zostały odnalezione na urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="4de29-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4de29-113">`-sdkpath`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="4de29-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="4de29-114">`-sdkpath`Opcja jest ustawiana podczas ładowania projektu urządzenia Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4de29-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="4de29-115">Można określić, że kompilator ma kompilować bez odwołania do biblioteki środowiska uruchomieniowego Visual Basic przy użyciu `-vbruntime` opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="4de29-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="4de29-116">Aby uzyskać więcej informacji, zobacz [-vbruntime](vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="4de29-116">For more information, see [-vbruntime](vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de29-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="4de29-117">Example</span></span>  

 <span data-ttu-id="4de29-118">Poniższy kod kompiluje `Myfile.vb` się z .NET Compact Framework przy użyciu wersji Mscorlib.dll i Microsoft.VisualBasic.dll znajdujących się w domyślnym katalogu instalacyjnym .NET Compact Framework na dysku C.</span><span class="sxs-lookup"><span data-stu-id="4de29-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="4de29-119">Zazwyczaj należy użyć najnowszej wersji .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="4de29-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4de29-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4de29-120">See also</span></span>

- [<span data-ttu-id="4de29-121">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4de29-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="4de29-122">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="4de29-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="4de29-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="4de29-123">-netcf</span></span>](netcf.md)
- [<span data-ttu-id="4de29-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="4de29-124">-vbruntime</span></span>](vbruntime.md)
