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
ms.openlocfilehash: 963004820f56272b4f1b1d92ccc4d0a60493a4a0
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128702"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="5cb54-103">-Resource (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="5cb54-103">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="5cb54-104">Osadza określony zasób w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="5cb54-104">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb54-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5cb54-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5cb54-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="5cb54-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="5cb54-107">Plik zasobów .NET Framework, który ma zostać osadzony w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="5cb54-107">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="5cb54-108">`identifier` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="5cb54-108">`identifier` (optional)</span></span>  
 <span data-ttu-id="5cb54-109">Nazwa logiczna zasobu; Nazwa, która jest używana do ładowania zasobu.</span><span class="sxs-lookup"><span data-stu-id="5cb54-109">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="5cb54-110">Wartość domyślna to nazwa pliku.</span><span class="sxs-lookup"><span data-stu-id="5cb54-110">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="5cb54-111">`accessibility-modifier` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="5cb54-111">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="5cb54-112">Dostępność zasobu: Public lub Private.</span><span class="sxs-lookup"><span data-stu-id="5cb54-112">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="5cb54-113">Wartość domyślna to Public.</span><span class="sxs-lookup"><span data-stu-id="5cb54-113">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cb54-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5cb54-114">Remarks</span></span>  
 <span data-ttu-id="5cb54-115">Użyj polecenia [-linkresource —](./linkresource-compiler-option.md) , aby połączyć zasób z zestawem, a nie dodać pliku zasobów do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="5cb54-115">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="5cb54-116">Domyślnie zasoby są publiczne w zestawie, gdy są tworzone przy użyciu kompilatora języka C#.</span><span class="sxs-lookup"><span data-stu-id="5cb54-116">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="5cb54-117">Aby udostępnić zasoby jako prywatne, określ `private` jako modyfikator dostępności.</span><span class="sxs-lookup"><span data-stu-id="5cb54-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="5cb54-118">Żadna inna dostępność jest inna niż `public` lub `private` niedozwolona.</span><span class="sxs-lookup"><span data-stu-id="5cb54-118">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="5cb54-119">Jeśli `filename` jest .NET Framework utworzony plik zasobów, na przykład przez [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku deweloperskim, dostęp do niego można uzyskać za pomocą elementów członkowskich w <xref:System.Resources> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5cb54-119">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="5cb54-120">Aby uzyskać więcej informacji, zobacz <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5cb54-120">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5cb54-121">W przypadku wszystkich innych zasobów Użyj `GetManifestResource` metod w klasie, <xref:System.Reflection.Assembly> Aby uzyskać dostęp do zasobu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5cb54-121">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="5cb54-122">**-res** to krótka forma **zasobu**.</span><span class="sxs-lookup"><span data-stu-id="5cb54-122">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="5cb54-123">Kolejność zasobów w pliku wyjściowym jest określana na podstawie kolejności określonej w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="5cb54-123">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5cb54-124">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5cb54-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="5cb54-125">Dodaj plik zasobów do projektu.</span><span class="sxs-lookup"><span data-stu-id="5cb54-125">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="5cb54-126">Wybierz plik, który ma zostać osadzony w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="5cb54-126">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="5cb54-127">Wybierz pozycję **Akcja kompilacji** dla pliku w oknie **Właściwości** .</span><span class="sxs-lookup"><span data-stu-id="5cb54-127">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="5cb54-128">Ustaw **akcję kompilacji** na **zasób osadzony**.</span><span class="sxs-lookup"><span data-stu-id="5cb54-128">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="5cb54-129">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.FileProperties2.BuildAction%2A> .</span><span class="sxs-lookup"><span data-stu-id="5cb54-129">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cb54-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="5cb54-130">Example</span></span>  
 <span data-ttu-id="5cb54-131">Kompiluj `in.cs` i Dołącz plik zasobu `rf.resource` :</span><span class="sxs-lookup"><span data-stu-id="5cb54-131">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cb54-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5cb54-132">See also</span></span>

- [<span data-ttu-id="5cb54-133">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="5cb54-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5cb54-134">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="5cb54-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
