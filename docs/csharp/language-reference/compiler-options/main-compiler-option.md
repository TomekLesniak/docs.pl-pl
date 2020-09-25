---
description: -Main (opcje kompilatora C#)
title: -Main (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: c27898de2a7cc2f3c01c51f8de1122e81b2233b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194118"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="ac100-103">-Main (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="ac100-103">-main (C# Compiler Options)</span></span>

<span data-ttu-id="ac100-104">Ta opcja określa klasę, która zawiera punkt wejścia do programu, jeśli więcej niż jedna Klasa zawiera metodę **Main** .</span><span class="sxs-lookup"><span data-stu-id="ac100-104">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac100-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac100-105">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="ac100-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ac100-106">Arguments</span></span>

 `class`  
 <span data-ttu-id="ac100-107">Typ, który zawiera metodę **Main** .</span><span class="sxs-lookup"><span data-stu-id="ac100-107">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="ac100-108">Podana nazwa klasy musi być w pełni kwalifikowana; musi zawierać pełną przestrzeń nazw zawierającą klasę, a po niej nazwę klasy.</span><span class="sxs-lookup"><span data-stu-id="ac100-108">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="ac100-109">Na przykład, gdy metoda znajduje się `Main` wewnątrz `Program` klasy w `MyApplication.Core` przestrzeni nazw, opcja kompilatora musi mieć wartość `-main:MyApplication.Core.Program` .</span><span class="sxs-lookup"><span data-stu-id="ac100-109">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac100-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ac100-110">Remarks</span></span>

<span data-ttu-id="ac100-111">Jeśli kompilacja zawiera więcej niż jeden typ z metodą [Main](../../programming-guide/main-and-command-args/index.md) , można określić, który typ zawiera metodę **Main** , która ma być używana jako punkt wejścia do programu.</span><span class="sxs-lookup"><span data-stu-id="ac100-111">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="ac100-112">Ta opcja jest używana podczas kompilowania pliku *. exe* .</span><span class="sxs-lookup"><span data-stu-id="ac100-112">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ac100-113">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac100-113">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="ac100-114">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="ac100-114">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="ac100-115">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="ac100-115">Click the **Application** property page.</span></span>

3. <span data-ttu-id="ac100-116">Zmodyfikuj właściwość **obiektu uruchomieniowego** .</span><span class="sxs-lookup"><span data-stu-id="ac100-116">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="ac100-117">Aby programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.StartupObject%2A> .</span><span class="sxs-lookup"><span data-stu-id="ac100-117">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="ac100-118">Aby ustawić tę opcję kompilatora, ręcznie edytując plik *. csproj*</span><span class="sxs-lookup"><span data-stu-id="ac100-118">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="ac100-119">Tę opcję można ustawić, edytując plik. csproj i dodając element `StartupObject` w `PropertyGroup` sekcji.</span><span class="sxs-lookup"><span data-stu-id="ac100-119">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="ac100-120">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="ac100-120">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="ac100-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="ac100-121">Example</span></span>

<span data-ttu-id="ac100-122">Kompiluj `t2.cs` i `t3.cs` , określając, że metoda **Main** zostanie znaleziona w `Test2` :</span><span class="sxs-lookup"><span data-stu-id="ac100-122">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="ac100-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac100-123">See also</span></span>

- [<span data-ttu-id="ac100-124">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="ac100-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ac100-125">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="ac100-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
