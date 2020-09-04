---
description: -linkresource — (opcje kompilatora C#)
title: -linkresource — (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: cd1150f3fa0dd0eca4e9352ce3809e73a15126c7
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466108"
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="cb718-103">-linkresource — (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="cb718-103">-linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="cb718-104">Tworzy łącze do zasobu .NET w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="cb718-104">Creates a link to a .NET resource in the output file.</span></span> <span data-ttu-id="cb718-105">Plik zasobów nie został dodany do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="cb718-105">The resource file is not added to the output file.</span></span> <span data-ttu-id="cb718-106">Różni się to od opcji [-Resource](./resource-compiler-option.md) , która osadza plik zasobów w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="cb718-106">This differs from the [-resource](./resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb718-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="cb718-107">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb718-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cb718-108">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="cb718-109">Plik zasobów platformy .NET, który ma zostać połączony z zestawu.</span><span class="sxs-lookup"><span data-stu-id="cb718-109">The .NET resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="cb718-110">`identifier` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="cb718-110">`identifier` (optional)</span></span>  
 <span data-ttu-id="cb718-111">Nazwa logiczna zasobu; Nazwa, która jest używana do ładowania zasobu.</span><span class="sxs-lookup"><span data-stu-id="cb718-111">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="cb718-112">Wartość domyślna to nazwa pliku.</span><span class="sxs-lookup"><span data-stu-id="cb718-112">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="cb718-113">`accessibility-modifier` (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="cb718-113">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="cb718-114">Dostępność zasobu: Public lub Private.</span><span class="sxs-lookup"><span data-stu-id="cb718-114">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="cb718-115">Wartość domyślna to Public.</span><span class="sxs-lookup"><span data-stu-id="cb718-115">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb718-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cb718-116">Remarks</span></span>  
 <span data-ttu-id="cb718-117">Domyślnie połączone zasoby są publiczne w zestawie, gdy są tworzone za pomocą kompilatora języka C#.</span><span class="sxs-lookup"><span data-stu-id="cb718-117">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="cb718-118">Aby udostępnić zasoby jako prywatne, określ `private` jako modyfikator dostępności.</span><span class="sxs-lookup"><span data-stu-id="cb718-118">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="cb718-119">Inny modyfikator inny niż `public` lub `private` jest niedozwolony.</span><span class="sxs-lookup"><span data-stu-id="cb718-119">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="cb718-120">**-linkresource —** wymaga jednej z opcji [-Target](./target-compiler-option.md) innych niż **-target: module**.</span><span class="sxs-lookup"><span data-stu-id="cb718-120">**-linkresource** requires one of the [-target](./target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="cb718-121">Jeśli `filename` plik zasobów platformy .NET został utworzony na przykład przez [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku programistycznym, dostęp do niego można uzyskać za pomocą elementów członkowskich w <xref:System.Resources> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="cb718-121">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="cb718-122">Aby uzyskać więcej informacji, zobacz <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb718-122">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cb718-123">W przypadku wszystkich innych zasobów Użyj `GetManifestResource` metod w klasie, <xref:System.Reflection.Assembly> Aby uzyskać dostęp do zasobu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="cb718-123">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="cb718-124">Plik określony w `filename` może być dowolnym formatem.</span><span class="sxs-lookup"><span data-stu-id="cb718-124">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="cb718-125">Można na przykład utworzyć natywną bibliotekę DLL zestawu, tak aby można ją było zainstalować w globalnej pamięci podręcznej zestawów i uzyskać do niej dostęp z kodu zarządzanego w zestawie.</span><span class="sxs-lookup"><span data-stu-id="cb718-125">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="cb718-126">W drugim z poniższych przykładów pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="cb718-126">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="cb718-127">Tę samą czynność można wykonać w konsolidatorze zestawu.</span><span class="sxs-lookup"><span data-stu-id="cb718-127">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="cb718-128">Trzeci z poniższych przykładów pokazuje, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="cb718-128">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="cb718-129">Aby uzyskać więcej informacji, zobacz [Al.exe (Konsolidator zestawu)](../../../framework/tools/al-exe-assembly-linker.md) i [Praca z zestawami i globalną pamięcią podręczną zestawów](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="cb718-129">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="cb718-130">**-linkres** jest krótką formą **-linkresource —**.</span><span class="sxs-lookup"><span data-stu-id="cb718-130">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="cb718-131">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="cb718-131">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb718-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="cb718-132">Example</span></span>  
 <span data-ttu-id="cb718-133">Kompiluj `in.cs` i Połącz z plikiem zasobów `rf.resource` :</span><span class="sxs-lookup"><span data-stu-id="cb718-133">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="cb718-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="cb718-134">Example</span></span>  
 <span data-ttu-id="cb718-135">Kompiluj do `A.cs` biblioteki DLL, Połącz się z natywną biblioteką dll N.dll i umieść dane wyjściowe w globalnej pamięci podręcznej zestawów (GAC).</span><span class="sxs-lookup"><span data-stu-id="cb718-135">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="cb718-136">W tym przykładzie zarówno A.dll, jak i N.dll będą przechowywane w pamięci podręcznej GAC.</span><span class="sxs-lookup"><span data-stu-id="cb718-136">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="cb718-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="cb718-137">Example</span></span>  
 <span data-ttu-id="cb718-138">Ten przykład wykonuje te same czynności co w poprzednim, ale przy użyciu opcji konsolidatora zestawu.</span><span class="sxs-lookup"><span data-stu-id="cb718-138">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb718-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cb718-139">See also</span></span>

- [<span data-ttu-id="cb718-140">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="cb718-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cb718-141">Al.exe (Konsolidator zestawu)</span><span class="sxs-lookup"><span data-stu-id="cb718-141">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="cb718-142">Praca z zestawami i globalną pamięcią podręczną zestawów</span><span class="sxs-lookup"><span data-stu-id="cb718-142">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="cb718-143">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="cb718-143">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
