---
title: 'Instrukcje: odwoływanie się do zestawu o silnej nazwie'
description: W tym artykule pokazano, jak odwoływać się do typów lub zasobów w przypadku zestawu o silnej nazwie .NET, w czasie kompilacji lub w środowisku uruchomieniowym.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 478f786995cfc4b57f0b18b2159775db104e9cfb
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687696"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="e6352-103">Instrukcje: odwoływanie się do zestawu o silnej nazwie</span><span class="sxs-lookup"><span data-stu-id="e6352-103">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="e6352-104">Proces odwoływania się do typów lub zasobów w zestawie o silnej nazwie jest zwykle niewidoczny.</span><span class="sxs-lookup"><span data-stu-id="e6352-104">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="e6352-105">Odwołanie można wykonać w czasie kompilacji (wczesne wiązanie) lub w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="e6352-105">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="e6352-106">Odwołanie w czasie kompilacji odbywa się po wskazaniu kompilatora, który zestaw ma zostać skompilowany jawnie odwołuje się do innego zestawu.</span><span class="sxs-lookup"><span data-stu-id="e6352-106">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="e6352-107">W przypadku korzystania z odwołania w czasie kompilacji kompilator automatycznie pobiera klucz publiczny do określonego zestawu o silnej nazwie i umieszcza go w odwołaniu do zestawu, który jest kompilowany.</span><span class="sxs-lookup"><span data-stu-id="e6352-107">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6352-108">Zestaw o silnej nazwie może używać tylko typów z innych zestawów o silnych nazwach.</span><span class="sxs-lookup"><span data-stu-id="e6352-108">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="e6352-109">W przeciwnym razie zabezpieczenia zestawu o silnej nazwie byłyby naruszone.</span><span class="sxs-lookup"><span data-stu-id="e6352-109">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="e6352-110">Utwórz odwołanie w czasie kompilacji do zestawu o silnej nazwie</span><span class="sxs-lookup"><span data-stu-id="e6352-110">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="e6352-111">W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="e6352-111">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="e6352-112">\<*compiler command*>**/Reference:**\<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="e6352-112">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="e6352-113">W tym poleceniu *kompilator* jest poleceniem kompilatora dla używanego języka, a *Nazwa zestawu* to nazwa zestawu o silnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="e6352-113">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="e6352-114">Można również użyć innych opcji kompilatora, takich jak opcja **/t: Library** do tworzenia zestawu biblioteki.</span><span class="sxs-lookup"><span data-stu-id="e6352-114">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="e6352-115">Poniższy przykład tworzy zestaw o nazwie *myAssembly.dll* , który odwołuje się do zestawu o silnej nazwie, o nazwie *myLibAssembly.dll* z modułu kodu o nazwie *myAssembly.cs* .</span><span class="sxs-lookup"><span data-stu-id="e6352-115">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs* .</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="e6352-116">Utwórz odwołanie w czasie wykonywania do zestawu o silnej nazwie</span><span class="sxs-lookup"><span data-stu-id="e6352-116">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="e6352-117">Podczas wykonywania odwołania do zestawu o silnej nazwie, na przykład przy użyciu <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> metody lub, należy użyć nazwy wyświetlanej zestawu o silnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="e6352-117">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="e6352-118">Składnia nazwy wyświetlanej jest następująca:</span><span class="sxs-lookup"><span data-stu-id="e6352-118">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="e6352-119">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span><span class="sxs-lookup"><span data-stu-id="e6352-119">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="e6352-120">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="e6352-120">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="e6352-121">W tym przykładzie `PublicKeyToken` jest to szesnastkowa postać tokenu klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="e6352-121">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="e6352-122">Jeśli nie ma żadnej wartości kulturowej, użyj `Culture=neutral` .</span><span class="sxs-lookup"><span data-stu-id="e6352-122">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="e6352-123">Poniższy przykład kodu pokazuje, jak używać tych informacji przy użyciu <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="e6352-123">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

<span data-ttu-id="e6352-124">Można wydrukować format szesnastkowy klucza publicznego i tokenu klucza publicznego dla określonego zestawu za pomocą następującego polecenia [silnej nazwy (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) :</span><span class="sxs-lookup"><span data-stu-id="e6352-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="e6352-125">**SN-TP \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="e6352-125">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="e6352-126">Jeśli masz plik klucza publicznego, możesz użyć poniższego polecenia (należy zwrócić uwagę na różnice w przypadku opcji wiersza polecenia):</span><span class="sxs-lookup"><span data-stu-id="e6352-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="e6352-127">**SN-TP \<** *public key file* **>**</span><span class="sxs-lookup"><span data-stu-id="e6352-127">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="e6352-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e6352-128">See also</span></span>

- [<span data-ttu-id="e6352-129">Tworzenie i używanie zestawów o silnej nazwie</span><span class="sxs-lookup"><span data-stu-id="e6352-129">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
