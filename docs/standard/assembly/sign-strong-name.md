---
title: 'Instrukcje: podpisywanie zestawu za pomocą silnej nazwy'
description: W tym artykule przedstawiono sposób podpisywania zestawu .NET silną nazwą za pomocą karty podpisywanie, konsolidator zestawu, atrybuty zestawu lub opcje kompilatora.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET], signing
- assemblies [.NET], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 5192f7f372b9ef7927930c3599aebc6fca9f1f0f
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687653"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="46e7f-103">Instrukcje: podpisywanie zestawu za pomocą silnej nazwy</span><span class="sxs-lookup"><span data-stu-id="46e7f-103">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="46e7f-104">Chociaż platforma .NET Core obsługuje zestawy o silnych nazwach, a wszystkie zestawy w bibliotece .NET Core są podpisane, większość zestawów innych firm nie potrzebuje silnych nazw.</span><span class="sxs-lookup"><span data-stu-id="46e7f-104">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="46e7f-105">Aby uzyskać więcej informacji, zobacz [Logowanie silnej nazwy](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) w serwisie GitHub.</span><span class="sxs-lookup"><span data-stu-id="46e7f-105">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="46e7f-106">Istnieje kilka metod podpisywania zestawu za pomocą silnej nazwy:</span><span class="sxs-lookup"><span data-stu-id="46e7f-106">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="46e7f-107">Za pomocą karty **podpisywanie** w oknie dialogowym **Właściwości** projektu w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="46e7f-107">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="46e7f-108">Jest to najprostsza i najwygodniejsza metoda podpisywania zestawów za pomocą silnych nazw.</span><span class="sxs-lookup"><span data-stu-id="46e7f-108">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="46e7f-109">Za pomocą [konsolidatora zestawu (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) do łączenia modułu kodu .NET Framework (plik *. module* ) z plikiem klucza.</span><span class="sxs-lookup"><span data-stu-id="46e7f-109">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="46e7f-110">Przy użyciu atrybutów zestawu w celu wstawienia informacji o silnej nazwie do kodu.</span><span class="sxs-lookup"><span data-stu-id="46e7f-110">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="46e7f-111">Możesz użyć albo <xref:System.Reflection.AssemblyKeyFileAttribute> <xref:System.Reflection.AssemblyKeyNameAttribute> atrybutu, w zależności od tego, gdzie znajduje się plik klucza, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="46e7f-111">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="46e7f-112">Przy użyciu opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="46e7f-112">By using compiler options.</span></span>  
  
 <span data-ttu-id="46e7f-113">Aby podpisać zestaw za pomocą silnej nazwy, trzeba mieć parę kluczy kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="46e7f-113">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="46e7f-114">Aby uzyskać więcej informacji na temat tworzenia pary kluczy, zobacz [How to: Create a Public-Private Key para](create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="46e7f-114">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="46e7f-115">Tworzenie i podpisywanie zestawu za pomocą silnej nazwy przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46e7f-115">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="46e7f-116">W **Eksplorator rozwiązań** Otwórz menu skrótów dla projektu, a następnie wybierz **Właściwości** .</span><span class="sxs-lookup"><span data-stu-id="46e7f-116">In **Solution Explorer** , open the shortcut menu for the project, and then choose **Properties** .</span></span>  
  
2. <span data-ttu-id="46e7f-117">Wybierz kartę **podpisywanie** .</span><span class="sxs-lookup"><span data-stu-id="46e7f-117">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="46e7f-118">Zaznacz pole **podpisz zestaw** .</span><span class="sxs-lookup"><span data-stu-id="46e7f-118">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="46e7f-119">W polu **Wybierz plik klucza o silnej nazwie** wybierz **Przeglądaj** , a następnie przejdź do pliku klucza.</span><span class="sxs-lookup"><span data-stu-id="46e7f-119">In the **Choose a strong name key file** box, choose **Browse** , and then navigate to the key file.</span></span> <span data-ttu-id="46e7f-120">Aby utworzyć nowy plik klucza, wybierz pozycję **Nowy** i wprowadź jego nazwę w oknie dialogowym **Tworzenie klucza silnej nazwy** .</span><span class="sxs-lookup"><span data-stu-id="46e7f-120">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46e7f-121">Aby [opóźnić podpisywanie zestawu](delay-sign.md), wybierz plik klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="46e7f-121">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="46e7f-122">Tworzenie i podpisywanie zestawu za pomocą silnej nazwy przy użyciu konsolidatora zestawu</span><span class="sxs-lookup"><span data-stu-id="46e7f-122">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="46e7f-123">W [wiersz polecenia dla deweloperów dla programu Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md)wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="46e7f-123">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="46e7f-124">**Al** **/out:** \<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="46e7f-124">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="46e7f-125">Gdzie:</span><span class="sxs-lookup"><span data-stu-id="46e7f-125">Where:</span></span>  

- <span data-ttu-id="46e7f-126">*AssemblyName* jest nazwą silnie podpisanego zestawu (plik *. dll* lub *. exe* ), który będzie emitowany przez konsolidator zestawu.</span><span class="sxs-lookup"><span data-stu-id="46e7f-126">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="46e7f-127">*ModuleName* jest nazwą modułu kodu .NET Framework (plik *. module* ), który zawiera jeden lub więcej typów.</span><span class="sxs-lookup"><span data-stu-id="46e7f-127">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="46e7f-128">Można utworzyć plik *. module* , kompilując kod za pomocą `/target:module` przełącznika w języku C# lub Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46e7f-128">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="46e7f-129">*filename* jest nazwą kontenera lub pliku, który zawiera parę kluczy.</span><span class="sxs-lookup"><span data-stu-id="46e7f-129">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="46e7f-130">Konsolidator zestawu interpretuje ścieżkę względną w odniesieniu do bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="46e7f-130">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="46e7f-131">Poniższy przykład podpisuje zestaw *MyAssembly.dll* za pomocą silnej nazwy przy użyciu pliku klucza *sgKey. snk* .</span><span class="sxs-lookup"><span data-stu-id="46e7f-131">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk* .</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="46e7f-132">Aby uzyskać więcej informacji na temat tego narzędzia, zobacz [konsolidator zestawu](../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="46e7f-132">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="46e7f-133">Podpisz zestaw silną nazwą przy użyciu atrybutów</span><span class="sxs-lookup"><span data-stu-id="46e7f-133">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="46e7f-134">Dodaj <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> atrybut or <xref:System.Reflection.AssemblyKeyNameAttribute> do pliku kodu źródłowego i określ nazwę pliku lub kontenera, który zawiera parę kluczy do użycia podczas podpisywania zestawu o silnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="46e7f-134">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  

2. <span data-ttu-id="46e7f-135">Skompiluj w normalny sposób plik kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="46e7f-135">Compile the source code file normally.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="46e7f-136">Kompilatory C# i Visual Basic generują ostrzeżenia kompilatora (odpowiednio CS1699 i BC41008), gdy napotkają <xref:System.Reflection.AssemblyKeyFileAttribute> atrybut lub <xref:System.Reflection.AssemblyKeyNameAttribute> w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="46e7f-136">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="46e7f-137">Można zignorować te ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="46e7f-137">You can ignore the warnings.</span></span>  

<span data-ttu-id="46e7f-138">W poniższym przykładzie używany jest <xref:System.Reflection.AssemblyKeyFileAttribute> atrybut z plikiem klucza o nazwie *keyfile. snk* , który znajduje się w katalogu, w którym jest kompilowany zestaw.</span><span class="sxs-lookup"><span data-stu-id="46e7f-138">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk* , which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="46e7f-139">Można również opóźnić podpisywanie zestawu podczas kompilowania pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="46e7f-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="46e7f-140">Aby uzyskać więcej informacji, zobacz [Opóźnij podpisanie zestawu](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="46e7f-140">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="46e7f-141">Podpisywanie zestawu za pomocą silnej nazwy przy użyciu kompilatora</span><span class="sxs-lookup"><span data-stu-id="46e7f-141">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="46e7f-142">Skompiluj plik lub pliki kodu źródłowego przy użyciu `/keyfile` `/delaysign` opcji kompilatora języka C# i Visual Basic lub `/KEYFILE` `/DELAYSIGN` opcji konsolidatora w języku C++.</span><span class="sxs-lookup"><span data-stu-id="46e7f-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="46e7f-143">Po nazwie opcji dodaj średnik, a następnie nazwę pliku klucza.</span><span class="sxs-lookup"><span data-stu-id="46e7f-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="46e7f-144">W przypadku używania kompilatorów wiersza polecenia można skopiować plik klucza do katalogu, który zawiera pliki kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="46e7f-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="46e7f-145">Aby uzyskać informacje dotyczące podpisywania opóźnień, zobacz [Opóźnij podpisanie zestawu](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="46e7f-145">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="46e7f-146">W poniższym przykładzie użyto kompilatora języka C# i podpisuje zestaw *UtilityLibrary.dll* za pomocą silnej nazwy przy użyciu pliku klucza *sgKey. snk* .</span><span class="sxs-lookup"><span data-stu-id="46e7f-146">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk* .</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="46e7f-147">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="46e7f-147">See also</span></span>

- [<span data-ttu-id="46e7f-148">Tworzenie i używanie zestawów o silnej nazwie</span><span class="sxs-lookup"><span data-stu-id="46e7f-148">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="46e7f-149">Instrukcje: Tworzenie pary kluczy publiczny-prywatny</span><span class="sxs-lookup"><span data-stu-id="46e7f-149">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="46e7f-150">Al.exe (Konsolidator zestawu)</span><span class="sxs-lookup"><span data-stu-id="46e7f-150">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="46e7f-151">Podpisywanie zestawu z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="46e7f-151">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="46e7f-152">Zarządzanie podpisywaniem zestawu i manifestu</span><span class="sxs-lookup"><span data-stu-id="46e7f-152">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="46e7f-153">Strona podpisywania, Projektant projektu</span><span class="sxs-lookup"><span data-stu-id="46e7f-153">Signing page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
