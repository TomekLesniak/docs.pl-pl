---
description: -Resource (opcje kompilatora C#)
title: -Resource (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 6f90ce6c1590784cefbd5f15ca8a36941aad77ed
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193780"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="0d060-103">-Resource (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="0d060-103">-resource (C# Compiler Options)</span></span>

<span data-ttu-id="0d060-104">Osadza określony zasób w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="0d060-104">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d060-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0d060-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d060-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0d060-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="0d060-107">Plik zasobów platformy .NET, który ma zostać osadzony w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="0d060-107">The .NET resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="0d060-108">`identifier` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="0d060-108">`identifier` (optional)</span></span>  
 <span data-ttu-id="0d060-109">Nazwa logiczna zasobu; Nazwa, która jest używana do ładowania zasobu.</span><span class="sxs-lookup"><span data-stu-id="0d060-109">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="0d060-110">Wartość domyślna to nazwa pliku.</span><span class="sxs-lookup"><span data-stu-id="0d060-110">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="0d060-111">`accessibility-modifier` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="0d060-111">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="0d060-112">Dostępność zasobu: Public lub Private.</span><span class="sxs-lookup"><span data-stu-id="0d060-112">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="0d060-113">Wartość domyślna to Public.</span><span class="sxs-lookup"><span data-stu-id="0d060-113">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d060-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0d060-114">Remarks</span></span>  

 <span data-ttu-id="0d060-115">Użyj polecenia [-linkresource —](./linkresource-compiler-option.md) , aby połączyć zasób z zestawem, a nie dodać pliku zasobów do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="0d060-115">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="0d060-116">Domyślnie zasoby są publiczne w zestawie, gdy są tworzone przy użyciu kompilatora języka C#.</span><span class="sxs-lookup"><span data-stu-id="0d060-116">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="0d060-117">Aby udostępnić zasoby jako prywatne, określ `private` jako modyfikator dostępności.</span><span class="sxs-lookup"><span data-stu-id="0d060-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="0d060-118">Żadna inna dostępność jest inna niż `public` lub `private` niedozwolona.</span><span class="sxs-lookup"><span data-stu-id="0d060-118">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="0d060-119">Jeśli `filename` plik zasobów platformy .NET został utworzony na przykład przez [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku programistycznym, dostęp do niego można uzyskać za pomocą elementów członkowskich w <xref:System.Resources> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0d060-119">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="0d060-120">Aby uzyskać więcej informacji, zobacz <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0d060-120">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0d060-121">W przypadku wszystkich innych zasobów Użyj `GetManifestResource` metod w klasie, <xref:System.Reflection.Assembly> Aby uzyskać dostęp do zasobu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0d060-121">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="0d060-122">**-res** to krótka forma **zasobu**.</span><span class="sxs-lookup"><span data-stu-id="0d060-122">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="0d060-123">Kolejność zasobów w pliku wyjściowym jest określana na podstawie kolejności określonej w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="0d060-123">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0d060-124">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0d060-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="0d060-125">Dodaj plik zasobów do projektu.</span><span class="sxs-lookup"><span data-stu-id="0d060-125">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="0d060-126">Wybierz plik, który ma zostać osadzony w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="0d060-126">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="0d060-127">Wybierz pozycję **Akcja kompilacji** dla pliku w oknie **Właściwości** .</span><span class="sxs-lookup"><span data-stu-id="0d060-127">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="0d060-128">Ustaw **akcję kompilacji** na **zasób osadzony**.</span><span class="sxs-lookup"><span data-stu-id="0d060-128">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="0d060-129">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.FileProperties2.BuildAction%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d060-129">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d060-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="0d060-130">Example</span></span>  

 <span data-ttu-id="0d060-131">Kompiluj `in.cs` i Dołącz plik zasobu `rf.resource` :</span><span class="sxs-lookup"><span data-stu-id="0d060-131">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d060-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d060-132">See also</span></span>

- [<span data-ttu-id="0d060-133">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="0d060-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="0d060-134">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="0d060-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
