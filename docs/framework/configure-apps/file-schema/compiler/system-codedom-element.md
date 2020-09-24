---
title: <system.codedom>, element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 6c35e24696be040788a0c44cbb100ebb35d37157
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149572"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="025e0-102">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="025e0-102">\<system.codedom> Element</span></span>

<span data-ttu-id="025e0-103">Określa ustawienia konfiguracji kompilatora dla dostępnych dostawców języka.</span><span class="sxs-lookup"><span data-stu-id="025e0-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="025e0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="025e0-104">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="025e0-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="025e0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="025e0-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="025e0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="025e0-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="025e0-107">Attributes</span></span>  

 <span data-ttu-id="025e0-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="025e0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="025e0-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="025e0-109">Child Elements</span></span>  
  
|<span data-ttu-id="025e0-110">Element</span><span class="sxs-lookup"><span data-stu-id="025e0-110">Element</span></span>|<span data-ttu-id="025e0-111">Opis</span><span class="sxs-lookup"><span data-stu-id="025e0-111">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="025e0-112">Kontener dla elementów konfiguracji kompilatora; zawiera zero lub więcej [\<compiler>](compiler-element.md) elementów.</span><span class="sxs-lookup"><span data-stu-id="025e0-112">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="025e0-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="025e0-113">Parent Elements</span></span>  
  
|<span data-ttu-id="025e0-114">Element</span><span class="sxs-lookup"><span data-stu-id="025e0-114">Element</span></span>|<span data-ttu-id="025e0-115">Opis</span><span class="sxs-lookup"><span data-stu-id="025e0-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="025e0-116">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="025e0-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="025e0-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="025e0-117">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="025e0-118">.NET Framework wersja 2,0</span><span class="sxs-lookup"><span data-stu-id="025e0-118">.NET Framework Version 2.0</span></span>  

 <span data-ttu-id="025e0-119">[\<system.codedom>](system-codedom-element.md)Element zawiera ustawienia konfiguracji kompilatora dla dostawców języka zainstalowanych na komputerze oprócz domyślnych dostawców zainstalowanych z .NET Framework, takich jak <xref:Microsoft.CSharp.CSharpCodeProvider> i <xref:Microsoft.VisualBasic.VBCodeProvider> .</span><span class="sxs-lookup"><span data-stu-id="025e0-119">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="025e0-120">[\<compilers>](compilers-element.md)Element zawiera zero lub więcej [\<compiler>](compiler-element.md) elementów.</span><span class="sxs-lookup"><span data-stu-id="025e0-120">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="025e0-121">Każdy [\<compiler>](compiler-element.md) element określa atrybuty konfiguracji kompilatora dla określonego dostawcy języka.</span><span class="sxs-lookup"><span data-stu-id="025e0-121">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="025e0-122">Deweloperzy i dostawcy kompilatora mogą dodać ustawienia konfiguracji do pliku konfiguracji komputera (Machine.config), aby uzyskać nową <xref:System.CodeDom.Compiler.CodeDomProvider> implementację.</span><span class="sxs-lookup"><span data-stu-id="025e0-122">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="025e0-123">Użyj <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metody, aby programowo wyliczyć zarówno domyślnych dostawców języka, jak i dostawców języka identyfikowanych przez ustawienia konfiguracji kompilatora na komputerze.</span><span class="sxs-lookup"><span data-stu-id="025e0-123">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="025e0-124">W .NET Framework wersje 1,0 i 1,1 dostawcy języka domyślnego dostarczone przez .NET Framework są identyfikowane w [\<compilers>](compilers-element.md) elemencie.</span><span class="sxs-lookup"><span data-stu-id="025e0-124">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="025e0-125">W .NET Framework w wersji 2,0 dostawcy języka domyślnego nie są identyfikowane w [\<compilers>](compilers-element.md) elemencie, ale można je wyliczyć przy użyciu <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="025e0-125">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="025e0-126">.NET Framework wersje 1,0 i 1,1</span><span class="sxs-lookup"><span data-stu-id="025e0-126">.NET Framework Versions 1.0 and 1.1</span></span>  

 <span data-ttu-id="025e0-127">[\<system.codedom>](system-codedom-element.md)Element zawiera ustawienia konfiguracji kompilatora dla dostawców języka na komputerze.</span><span class="sxs-lookup"><span data-stu-id="025e0-127">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="025e0-128">[\<compilers>](compilers-element.md)Element zawiera zero lub więcej [\<compiler>](compiler-element.md) elementów.</span><span class="sxs-lookup"><span data-stu-id="025e0-128">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="025e0-129">Każdy [\<compiler>](compiler-element.md) element określa atrybuty konfiguracji kompilatora dla określonego dostawcy języka.</span><span class="sxs-lookup"><span data-stu-id="025e0-129">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="025e0-130">.NET Framework definiuje początkowe ustawienia kompilatora w pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="025e0-130">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="025e0-131">Deweloperzy i dostawcy kompilatora mogą dodać ustawienia konfiguracji dla nowej <xref:System.CodeDom.Compiler.CodeDomProvider> implementacji.</span><span class="sxs-lookup"><span data-stu-id="025e0-131">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="025e0-132">Użyj <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metody, aby programowo wyliczyć dostawcę języka i ustawienia konfiguracji kompilatora na komputerze.</span><span class="sxs-lookup"><span data-stu-id="025e0-132">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="025e0-133">Plik konfiguracji</span><span class="sxs-lookup"><span data-stu-id="025e0-133">Configuration File</span></span>  

 <span data-ttu-id="025e0-134">Ten element może być używany w pliku konfiguracji komputera i w pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="025e0-134">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="025e0-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="025e0-135">Example</span></span>  

 <span data-ttu-id="025e0-136">Poniższy przykład ilustruje typową konfigurację kompilatora.</span><span class="sxs-lookup"><span data-stu-id="025e0-136">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="025e0-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="025e0-137">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="025e0-138">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="025e0-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="025e0-139">Schemat ustawień kompilatora i dostawcy języka</span><span class="sxs-lookup"><span data-stu-id="025e0-139">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="025e0-140">\<compiler> Postaci</span><span class="sxs-lookup"><span data-stu-id="025e0-140">\<compiler> Element</span></span>](compiler-element.md)
