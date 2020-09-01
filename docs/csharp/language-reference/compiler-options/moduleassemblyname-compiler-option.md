---
description: -moduleassemblyname — (opcja kompilatora C#)
title: -moduleassemblyname — (opcja kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: d669a1687abe496b921d5670b9149b0e933b2d95
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125257"
---
# <a name="-moduleassemblyname-c-compiler-option"></a><span data-ttu-id="75b50-103">-moduleassemblyname — (opcja kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="75b50-103">-moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="75b50-104">Określa zestaw, którego typy niepubliczne a. module mogą uzyskać dostęp.</span><span class="sxs-lookup"><span data-stu-id="75b50-104">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b50-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="75b50-105">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="75b50-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="75b50-106">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="75b50-107">Nazwa zestawu, którego typy niepubliczne mogą uzyskać dostęp do modułu.</span><span class="sxs-lookup"><span data-stu-id="75b50-107">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75b50-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="75b50-108">Remarks</span></span>  
 <span data-ttu-id="75b50-109">**-moduleassemblyname —** należy używać podczas kompilowania modułu. sieci i, gdy są spełnione następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="75b50-109">**-moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
- <span data-ttu-id="75b50-110">Moduł. Webmusi mieć dostęp do niepublicznych typów w istniejącym zestawie.</span><span class="sxs-lookup"><span data-stu-id="75b50-110">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
- <span data-ttu-id="75b50-111">Znasz nazwę zestawu, do którego zostanie skompilowany moduł.</span><span class="sxs-lookup"><span data-stu-id="75b50-111">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
- <span data-ttu-id="75b50-112">Istniejący zestaw przydzieli znajomemu dostęp do zestawu, do którego zostanie skompilowany moduł.</span><span class="sxs-lookup"><span data-stu-id="75b50-112">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="75b50-113">Aby uzyskać więcej informacji na temat tworzenia modułu., zobacz [-target: module (opcje kompilatora C#)](./target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="75b50-113">For more information on building a .netmodule, see [-target:module (C# Compiler Options)](./target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="75b50-114">Aby uzyskać więcej informacji o znajomych zestawach, zobacz [zaprzyjaźnione zestawy](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="75b50-114">For more information on friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
 <span data-ttu-id="75b50-115">Ta opcja jest niedostępna w środowisku programistycznym; jest on dostępny tylko w przypadku kompilowania z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="75b50-115">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="75b50-116">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="75b50-116">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75b50-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="75b50-117">Example</span></span>  
 <span data-ttu-id="75b50-118">Ten przykład kompiluje zestaw z typem prywatnym i zapewnia znajomemu dostęp do zestawu o nazwie csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="75b50-118">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class
{  
    public void Test()
    {
        Console.WriteLine("An_Internal_Class.Test called");
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="75b50-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="75b50-119">Example</span></span>  
 <span data-ttu-id="75b50-120">Ten przykład tworzy moduł. Service, który uzyskuje dostęp do typu niepublicznego w zestawie moduleassemblyname_1.dll.</span><span class="sxs-lookup"><span data-stu-id="75b50-120">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="75b50-121">Wiedząc, że ten moduł. module zostanie skompilowany w zestawie o nazwie csman_an_assembly, możemy określić wartość **-moduleassemblyname —**, zezwalając na dostęp do niepublicznych typów w zestawie, który udzielił znajomemu dostęp do zestawu csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="75b50-121">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **-moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="75b50-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="75b50-122">Example</span></span>  
 <span data-ttu-id="75b50-123">Ten przykładowy kod kompiluje csman_an_assembly zestawu, odwołujący się do poprzednio skompilowanego zestawu i modułu.</span><span class="sxs-lookup"><span data-stu-id="75b50-123">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
<span data-ttu-id="75b50-124">**An_Internal_Class. test wywołany**</span><span class="sxs-lookup"><span data-stu-id="75b50-124">**An_Internal_Class.Test called**</span></span>

## <a name="see-also"></a><span data-ttu-id="75b50-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75b50-125">See also</span></span>

- [<span data-ttu-id="75b50-126">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="75b50-126">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="75b50-127">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="75b50-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
