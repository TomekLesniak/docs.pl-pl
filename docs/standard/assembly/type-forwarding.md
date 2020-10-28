---
title: Przekazywanie dalej typu w środowisku uruchomieniowym języka wspólnego
description: Przekazywanie typu pozwala przenieść typ do innego zestawu platformy .NET bez konieczności ponownego kompilowania aplikacji, które używają oryginalnego zestawu.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: cd166068993fb5d1a5164615de3926a06dda8098
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687669"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="2b270-103">Przekazywanie dalej typu w środowisku uruchomieniowym języka wspólnego</span><span class="sxs-lookup"><span data-stu-id="2b270-103">Type forwarding in the common language runtime</span></span>

<span data-ttu-id="2b270-104">Przekazywanie typu pozwala przenieść typ do innego zestawu bez konieczności ponownego kompilowania aplikacji, które używają oryginalnego zestawu.</span><span class="sxs-lookup"><span data-stu-id="2b270-104">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="2b270-105">Załóżmy na przykład, że aplikacja używa `Example` klasy w zestawie o nazwie *Utility.dll* .</span><span class="sxs-lookup"><span data-stu-id="2b270-105">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll* .</span></span> <span data-ttu-id="2b270-106">Deweloperzy *Utility.dll* mogą zdecydować się na refaktoryzację zestawu, a w procesie może przenieść `Example` klasę do innego zestawu.</span><span class="sxs-lookup"><span data-stu-id="2b270-106">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="2b270-107">Jeśli stara wersja *Utility.dll* jest zastępowana przez nową wersję *Utility.dll* i jej zestawu towarzyszącego, aplikacja, która używa `Example` klasy, zakończy się niepowodzeniem, ponieważ nie może zlokalizować `Example` klasy w nowej wersji *Utility.dll* .</span><span class="sxs-lookup"><span data-stu-id="2b270-107">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll* .</span></span>  
  
 <span data-ttu-id="2b270-108">Deweloperzy *Utility.dll* mogą tego uniknąć przez przekazywanie żądań dla `Example` klasy przy użyciu <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="2b270-108">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="2b270-109">Jeśli atrybut został zastosowany do nowej wersji *Utility.dll* , żądania dotyczące `Example` klasy są przekazywane do zestawu, który zawiera teraz klasę.</span><span class="sxs-lookup"><span data-stu-id="2b270-109">If the attribute has been applied to the new version of *Utility.dll* , requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="2b270-110">Istniejąca aplikacja nadal działa normalnie, bez ponownej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="2b270-110">The existing application continues to function normally, without recompilation.</span></span>

## <a name="forward-a-type"></a><span data-ttu-id="2b270-111">Przekazywanie typu</span><span class="sxs-lookup"><span data-stu-id="2b270-111">Forward a type</span></span>

 <span data-ttu-id="2b270-112">Aby przesłać dalej typ, należy wykonać cztery kroki:</span><span class="sxs-lookup"><span data-stu-id="2b270-112">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="2b270-113">Przenieś kod źródłowy dla typu z oryginalnego zestawu do zestawu docelowego.</span><span class="sxs-lookup"><span data-stu-id="2b270-113">Move the source code for the type from the original assembly to the destination assembly.</span></span>  

2. <span data-ttu-id="2b270-114">W zestawie, w którym używany jest typ, Dodaj <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> dla typu, który został przeniesiony.</span><span class="sxs-lookup"><span data-stu-id="2b270-114">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="2b270-115">Poniższy kod przedstawia atrybut dla typu o nazwie `Example` , który został przeniesiony.</span><span class="sxs-lookup"><span data-stu-id="2b270-115">The following code shows the attribute for a type named `Example` that was moved.</span></span>  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. <span data-ttu-id="2b270-116">Kompiluj zestaw, który zawiera teraz typ.</span><span class="sxs-lookup"><span data-stu-id="2b270-116">Compile the assembly that now contains the type.</span></span>  

4. <span data-ttu-id="2b270-117">Ponownie skompiluj zestaw, w którym znajduje się typ, z odwołaniem do zestawu, który zawiera teraz typ.</span><span class="sxs-lookup"><span data-stu-id="2b270-117">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="2b270-118">Na przykład, Jeśli kompilujesz plik C# z wiersza polecenia, użyj opcji [-Reference (opcje kompilatora C#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) , aby określić zestaw, który zawiera typ.</span><span class="sxs-lookup"><span data-stu-id="2b270-118">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="2b270-119">W języku C++ Użyj dyrektywy [#using](/cpp/preprocessor/hash-using-directive-cpp) w pliku źródłowym, aby określić zestaw, który zawiera typ.</span><span class="sxs-lookup"><span data-stu-id="2b270-119">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b270-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2b270-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="2b270-121">Przekazywanie dalej typu (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="2b270-121">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="2b270-122">#using — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="2b270-122">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
