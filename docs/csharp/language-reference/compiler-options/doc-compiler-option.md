---
description: -doc (opcje kompilatora C#)
title: -doc (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: b1d7fbbe98aaad16454fdd71c161f2a17a2f4f2e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173259"
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="299cd-103">-doc (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="299cd-103">-doc (C# Compiler Options)</span></span>

<span data-ttu-id="299cd-104">Opcja **-doc** umożliwia umieszczenie komentarzy do dokumentacji w pliku XML.</span><span class="sxs-lookup"><span data-stu-id="299cd-104">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="299cd-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="299cd-105">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="299cd-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="299cd-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="299cd-107">Plik wyjściowy dla XML, który jest wypełniony komentarzami w plikach kodu źródłowego kompilacji.</span><span class="sxs-lookup"><span data-stu-id="299cd-107">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="299cd-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="299cd-108">Remarks</span></span>  

 <span data-ttu-id="299cd-109">W plikach kodu źródłowego Komentarze do dokumentacji, które poprzedzają następujące elementy, mogą być przetwarzane i dodawane do pliku XML:</span><span class="sxs-lookup"><span data-stu-id="299cd-109">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
- <span data-ttu-id="299cd-110">Takie typy zdefiniowane przez użytkownika jako [Klasa](../keywords/class.md), [Delegat](../builtin-types/reference-types.md#the-delegate-type)lub [interfejs](../keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="299cd-110">Such user-defined types as a [class](../keywords/class.md), [delegate](../builtin-types/reference-types.md#the-delegate-type), or [interface](../keywords/interface.md)</span></span>  
  
- <span data-ttu-id="299cd-111">Takie elementy członkowskie jak pole, [zdarzenie](../keywords/event.md), [Właściwość](../../programming-guide/classes-and-structs/using-properties.md)lub metoda</span><span class="sxs-lookup"><span data-stu-id="299cd-111">Such members as a field, [event](../keywords/event.md), [property](../../programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="299cd-112">Plik kodu źródłowego, który zawiera główny, jest wyprowadzany jako pierwszy w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="299cd-112">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="299cd-113">Aby użyć wygenerowanego pliku XML do użycia z funkcją [IntelliSense](/visualstudio/ide/using-intellisense) , pozwól, aby nazwa pliku XML była taka sama jak zestaw, który ma być obsługiwany, a następnie upewnij się, że plik. XML znajduje się w tym samym katalogu, co zestaw.</span><span class="sxs-lookup"><span data-stu-id="299cd-113">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="299cd-114">Z tego względu, gdy zestaw jest przywoływany w projekcie programu Visual Studio, można również znaleźć plik. XML.</span><span class="sxs-lookup"><span data-stu-id="299cd-114">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="299cd-115">Zobacz [dostarczanie komentarzy do kodu](/visualstudio/ide/reference/generate-xml-documentation-comments) i aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="299cd-115">See [Supplying Code Comments](/visualstudio/ide/reference/generate-xml-documentation-comments) and for more information.</span></span>  
  
 <span data-ttu-id="299cd-116">O ile nie zostanie skompilowany [element-target: module](./target-module-compiler-option.md), `file` program będzie zawierać \<assembly> \</assembly> Tagi określające nazwę pliku zawierającego manifest zestawu dla pliku wyjściowego kompilacji.</span><span class="sxs-lookup"><span data-stu-id="299cd-116">Unless you compile with [-target:module](./target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="299cd-117">Opcja-doc dotyczy wszystkich plików wejściowych; lub, jeśli jest ustawiony w ustawieniach projektu, wszystkie pliki w projekcie.</span><span class="sxs-lookup"><span data-stu-id="299cd-117">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="299cd-118">Aby wyłączyć ostrzeżenia związane z komentarzami do dokumentacji dla określonego pliku lub sekcji kodu, użyj [#pragma ostrzeżenie](../preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="299cd-118">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="299cd-119">Zapoznaj się z [polecanymi tagami komentarzy do dokumentacji](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) , aby poznać sposoby generowania dokumentacji z komentarzy w kodzie.</span><span class="sxs-lookup"><span data-stu-id="299cd-119">See [Recommended Tags for Documentation Comments](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="299cd-120">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="299cd-120">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="299cd-121">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="299cd-121">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="299cd-122">Kliknij kartę **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="299cd-122">Click the **Build** tab.</span></span>  
  
3. <span data-ttu-id="299cd-123">Zmodyfikuj właściwość **pliku dokumentacji XML** .</span><span class="sxs-lookup"><span data-stu-id="299cd-123">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="299cd-124">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A> .</span><span class="sxs-lookup"><span data-stu-id="299cd-124">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299cd-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="299cd-125">See also</span></span>

- [<span data-ttu-id="299cd-126">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="299cd-126">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="299cd-127">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="299cd-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
