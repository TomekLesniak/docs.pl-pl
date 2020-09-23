---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 726f3dd179aedb39b578c8580c9632182af2d5e0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085129"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="e7723-102">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7723-102">-resource (Visual Basic)</span></span>

<span data-ttu-id="e7723-103">Osadza zasób zarządzany w zestawie.</span><span class="sxs-lookup"><span data-stu-id="e7723-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7723-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e7723-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="e7723-105">lub</span><span class="sxs-lookup"><span data-stu-id="e7723-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7723-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e7723-106">Arguments</span></span>  
  
|<span data-ttu-id="e7723-107">Termin</span><span class="sxs-lookup"><span data-stu-id="e7723-107">Term</span></span>|<span data-ttu-id="e7723-108">Definicja</span><span class="sxs-lookup"><span data-stu-id="e7723-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="e7723-109">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="e7723-109">Required.</span></span> <span data-ttu-id="e7723-110">Nazwa pliku zasobu do osadzenia w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="e7723-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="e7723-111">Domyślnie jest on `filename` publiczny w zestawie.</span><span class="sxs-lookup"><span data-stu-id="e7723-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="e7723-112">Nazwa pliku należy ująć w cudzysłów (""), jeśli zawiera spację.</span><span class="sxs-lookup"><span data-stu-id="e7723-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="e7723-113">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="e7723-113">Optional.</span></span> <span data-ttu-id="e7723-114">Nazwa logiczna zasobu; Nazwa użyta do załadowania.</span><span class="sxs-lookup"><span data-stu-id="e7723-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="e7723-115">Wartość domyślna to nazwa pliku.</span><span class="sxs-lookup"><span data-stu-id="e7723-115">The default is the name of the file.</span></span> <span data-ttu-id="e7723-116">Opcjonalnie można określić, czy zasób jest publiczny, czy prywatny w manifeście zestawu, tak jak w przypadku następujących: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="e7723-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7723-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e7723-117">Remarks</span></span>  

 <span data-ttu-id="e7723-118">Służy `-linkresource` do łączenia zasobu z zestawem bez umieszczania pliku zasobów w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="e7723-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="e7723-119">Jeśli `filename` jest .NET Framework utworzony plik zasobów, na przykład przez [Resgen.exe (Generator plików zasobów)](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku deweloperskim, dostęp do niego można uzyskać za pomocą elementów członkowskich w <xref:System.Resources> przestrzeni nazw (Zobacz, <xref:System.Resources.ResourceManager> Aby uzyskać więcej informacji).</span><span class="sxs-lookup"><span data-stu-id="e7723-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="e7723-120">Aby uzyskać dostęp do wszystkich innych zasobów w czasie wykonywania, należy użyć jednej z następujących metod: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A> , <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> , lub <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> .</span><span class="sxs-lookup"><span data-stu-id="e7723-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="e7723-121">Krótka forma `-resource` to `-res` .</span><span class="sxs-lookup"><span data-stu-id="e7723-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="e7723-122">Aby uzyskać informacje na temat sposobu ustawiania `-resource` w środowisku IDE programu Visual Studio, zobacz [Zarządzanie zasobami aplikacji (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e7723-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7723-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="e7723-123">Example</span></span>  

 <span data-ttu-id="e7723-124">Poniższy kod kompiluje `In.vb` i dołącza plik zasobów `Rf.resource` .</span><span class="sxs-lookup"><span data-stu-id="e7723-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7723-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e7723-125">See also</span></span>

- [<span data-ttu-id="e7723-126">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7723-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e7723-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="e7723-127">-win32resource</span></span>](win32resource.md)
- [<span data-ttu-id="e7723-128">-linkresource — (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7723-128">-linkresource (Visual Basic)</span></span>](linkresource.md)
- [<span data-ttu-id="e7723-129">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7723-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="e7723-130">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="e7723-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
