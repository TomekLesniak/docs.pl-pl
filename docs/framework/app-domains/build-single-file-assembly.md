---
title: 'Instrukcje: Kompilowanie zestawu .NET Framework jednego pliku'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98f06e62e1070f78faa77ef7d83fd80a62984684
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991249"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="fa6a0-102">Instrukcje: Kompilowanie zestawu .NET Framework jednego pliku</span><span class="sxs-lookup"><span data-stu-id="fa6a0-102">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="fa6a0-103">Zestaw jednoplikowy, który jest najprostszym typem zestawu, zawiera informacje o typie i implementację, a także [manifest zestawu](../../standard/assembly/manifest.md).</span><span class="sxs-lookup"><span data-stu-id="fa6a0-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="fa6a0-104">Można użyć kompilatorów wiersza polecenia lub programu Visual Studio, aby utworzyć zestaw jednoplikowy, który jest przeznaczony dla .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-104">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="fa6a0-105">Domyślnie kompilator tworzy plik zestawu z rozszerzeniem *. exe* .</span><span class="sxs-lookup"><span data-stu-id="fa6a0-105">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="fa6a0-106">Programu Visual Studio C# for i Visual Basic można używać tylko do tworzenia zestawów jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="fa6a0-107">Jeśli chcesz utworzyć zestawy wieloplikowe, musisz użyć kompilatorów wiersza polecenia lub wizualizacji C++.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="fa6a0-108">W poniższych procedurach pokazano, jak utworzyć zestawy Jednoplikowe za pomocą kompilatorów wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="fa6a0-109">Utwórz zestaw z rozszerzeniem. exe</span><span class="sxs-lookup"><span data-stu-id="fa6a0-109">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="fa6a0-110">W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="fa6a0-111">\<> *Nazwa modułu* poleceń\<kompilatora></span><span class="sxs-lookup"><span data-stu-id="fa6a0-111">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="fa6a0-112">W tym poleceniu *kompilator* jest poleceniem kompilatora dla języka używanego w module kodu, a *Nazwa modułu* to nazwa modułu kodu do skompilowania do zestawu.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="fa6a0-113">Poniższy przykład tworzy zestaw o nazwie mój *Code. exe* z modułu kodu o nazwie `myCode`.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-113">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="fa6a0-114">Tworzenie zestawu z rozszerzeniem. exe i Określanie nazwy pliku wyjściowego</span><span class="sxs-lookup"><span data-stu-id="fa6a0-114">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="fa6a0-115">W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-115">At the command prompt, type the following command:</span></span>

<span data-ttu-id="fa6a0-116">\<*polecenie*\<kompilatora/out: nazwa pliku nazwamodułu\<> > ></span><span class="sxs-lookup"><span data-stu-id="fa6a0-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="fa6a0-117">W tym poleceniu *kompilator* jest poleceniem kompilatora dla języka używanego w module kodu, *Nazwa pliku* jest nazwą pliku wyjściowego, a *Nazwa modułu* to nazwa modułu kodu do skompilowania do zestawu.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="fa6a0-118">Poniższy przykład tworzy zestaw o nazwie mój *Assembly. exe* z modułu kodu o nazwie `myCode`.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-118">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="fa6a0-119">Utwórz zestawy bibliotek</span><span class="sxs-lookup"><span data-stu-id="fa6a0-119">Create library assemblies</span></span>
 <span data-ttu-id="fa6a0-120">Zestaw biblioteki jest podobny do biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="fa6a0-121">Zawiera typy, do których odwołują się inne zestawy, ale nie ma punktu wejścia, aby rozpocząć wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="fa6a0-122">Aby utworzyć zestaw biblioteki, w wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-122">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="fa6a0-123">\<polecenie> kompilatora — *Nazwa modułu* **t:Library** \<></span><span class="sxs-lookup"><span data-stu-id="fa6a0-123">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="fa6a0-124">W tym poleceniu *kompilator* jest poleceniem kompilatora dla języka używanego w module kodu, a *Nazwa modułu* to nazwa modułu kodu do skompilowania do zestawu.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-124">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="fa6a0-125">Można również użyć innych opcji kompilatora, takich jak opcja **-out:** .</span><span class="sxs-lookup"><span data-stu-id="fa6a0-125">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="fa6a0-126">Poniższy przykład tworzy zestaw biblioteki o nazwie *myCodeAssembly. dll* z modułu kodu o nazwie `myCode`.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-126">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="fa6a0-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fa6a0-127">See also</span></span>

- [<span data-ttu-id="fa6a0-128">Tworzenie zestawów</span><span class="sxs-lookup"><span data-stu-id="fa6a0-128">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="fa6a0-129">Zestawy wieloplikowe</span><span class="sxs-lookup"><span data-stu-id="fa6a0-129">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="fa6a0-130">Instrukcje: Kompilowanie zestawu wieloplikowego</span><span class="sxs-lookup"><span data-stu-id="fa6a0-130">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="fa6a0-131">Program z zestawami</span><span class="sxs-lookup"><span data-stu-id="fa6a0-131">Program with assemblies</span></span>](../../standard/assembly/program.md)