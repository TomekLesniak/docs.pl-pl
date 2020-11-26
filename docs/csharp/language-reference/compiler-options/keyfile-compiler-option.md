---
description: -keyfile (opcje kompilatora C#)
title: -keyfile (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: 5af40da18895d47933cb809d710e31a40f14513b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91152432"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="dc59f-103">-keyfile (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="dc59f-103">-keyfile (C# Compiler Options)</span></span>

<span data-ttu-id="dc59f-104">Określa nazwę pliku zawierającego klucz kryptograficzny.</span><span class="sxs-lookup"><span data-stu-id="dc59f-104">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc59f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="dc59f-105">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="dc59f-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="dc59f-106">Arguments</span></span>  
  
|<span data-ttu-id="dc59f-107">Termin</span><span class="sxs-lookup"><span data-stu-id="dc59f-107">Term</span></span>|<span data-ttu-id="dc59f-108">Definicja</span><span class="sxs-lookup"><span data-stu-id="dc59f-108">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="dc59f-109">Nazwa pliku zawierającego klucz silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="dc59f-109">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc59f-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc59f-110">Remarks</span></span>  

 <span data-ttu-id="dc59f-111">Gdy ta opcja jest używana, kompilator wstawia klucz publiczny z określonego pliku do manifestu zestawu, a następnie podpisuje końcowy zestaw kluczem prywatnym.</span><span class="sxs-lookup"><span data-stu-id="dc59f-111">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="dc59f-112">Aby wygenerować plik klucza, wpisz SN-k `file` w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="dc59f-112">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="dc59f-113">W przypadku kompilowania z **modułem-target:** nazwa pliku klucza jest przechowywana w module i wbudowana w zestaw, który jest tworzony podczas kompilowania zestawu za pomocą [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dc59f-113">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="dc59f-114">Możesz również przekazać informacje o szyfrowaniu do kompilatora z [kontenerem](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dc59f-114">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="dc59f-115">Użyj [-delaysign](./delaysign-compiler-option.md) , jeśli chcesz użyć częściowo podpisanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="dc59f-115">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="dc59f-116">W przypadku określenia zarówno parametru-KeyFile, jak i-containerer (za pomocą opcji wiersza polecenia lub przez atrybut niestandardowy) w tej samej kompilacji kompilator najpierw spróbuje kontener kluczy.</span><span class="sxs-lookup"><span data-stu-id="dc59f-116">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="dc59f-117">Jeśli to się powiedzie, zestaw zostanie podpisany przy użyciu informacji z kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="dc59f-117">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="dc59f-118">Jeśli kompilator nie odnajdzie kontenera kluczy, podejmie próbę pliku określonego za pomocą parametru-keyfile.</span><span class="sxs-lookup"><span data-stu-id="dc59f-118">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="dc59f-119">Jeśli to się powiedzie, zestaw zostanie podpisany przy użyciu informacji w pliku klucza, a informacje o kluczu zostaną zainstalowane w kontenerze kluczy (podobnym do SN-i), tak aby w następnej kompilacji kontener kluczy będzie prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="dc59f-119">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="dc59f-120">Należy pamiętać, że plik klucza może zawierać tylko klucz publiczny.</span><span class="sxs-lookup"><span data-stu-id="dc59f-120">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="dc59f-121">Aby uzyskać więcej informacji, zobacz [Tworzenie i używanie zestawów Strong-Named](../../../standard/assembly/create-use-strong-named.md) i [opóźnianie podpisywania zestawu](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="dc59f-121">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="dc59f-122">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dc59f-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="dc59f-123">Otwórz stronę **Właściwości** dla projektu.</span><span class="sxs-lookup"><span data-stu-id="dc59f-123">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="dc59f-124">Kliknij stronę właściwości **podpisywanie** .</span><span class="sxs-lookup"><span data-stu-id="dc59f-124">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="dc59f-125">Zmodyfikuj właściwość **pliku klucza o silnej nazwie** .</span><span class="sxs-lookup"><span data-stu-id="dc59f-125">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="dc59f-126">Można programowo uzyskać dostęp do tej opcji kompilatora przy użyciu <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A> .</span><span class="sxs-lookup"><span data-stu-id="dc59f-126">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc59f-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dc59f-127">See also</span></span>

- [<span data-ttu-id="dc59f-128">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="dc59f-128">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="dc59f-129">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="dc59f-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
