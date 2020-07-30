---
title: <summary> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <summary> Tag, który jest używany do opisywania typu lub elementu członkowskiego typu. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: f9243e598aaf0c12dd48b48045f461b4b307c18f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380608"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="7ea36-105">\<summary>(Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="7ea36-105">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7ea36-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="7ea36-106">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="7ea36-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="7ea36-107">Parameters</span></span>

- `description`

  <span data-ttu-id="7ea36-108">Podsumowanie obiektu.</span><span class="sxs-lookup"><span data-stu-id="7ea36-108">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ea36-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7ea36-109">Remarks</span></span>

<span data-ttu-id="7ea36-110">`<summary>`Tag powinien służyć do opisywania typu lub elementu członkowskiego typu.</span><span class="sxs-lookup"><span data-stu-id="7ea36-110">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="7ea36-111">Służy [\<remarks>](./remarks.md) do dodawania dodatkowych informacji do opisu typu.</span><span class="sxs-lookup"><span data-stu-id="7ea36-111">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="7ea36-112">Użyj [atrybutu cref](./cref-attribute.md) , aby włączyć narzędzia do dokumentacji, takie jak [DocFX](https://dotnet.github.io/docfx/) i [Sandcastle](https://github.com/EWSoftware/SHFB) , aby utworzyć wewnętrzne hiperłącza do stron dokumentacji dla elementów kodu.</span><span class="sxs-lookup"><span data-stu-id="7ea36-112">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="7ea36-113">Tekst `<summary>` znacznika jest jedynym źródłem informacji o typie w technologii IntelliSense i jest również wyświetlany w oknie Przeglądarka obiektów.</span><span class="sxs-lookup"><span data-stu-id="7ea36-113">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="7ea36-114">Kompiluj z [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="7ea36-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="7ea36-115">Aby utworzyć ostateczną dokumentację opartą na pliku generowanym przez kompilator, można utworzyć niestandardowe narzędzie lub użyć narzędzia, takiego jak [DocFX](https://dotnet.github.io/docfx/) lub [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="7ea36-115">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="7ea36-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="7ea36-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="7ea36-117">W poprzednim przykładzie jest tworzony następujący plik XML.</span><span class="sxs-lookup"><span data-stu-id="7ea36-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            </summary>
            <seealso cref="M:TestClass.Main"/>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="7ea36-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="7ea36-118">Example</span></span>

<span data-ttu-id="7ea36-119">Poniższy przykład pokazuje, jak utworzyć `cref` odwołanie do typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="7ea36-119">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="7ea36-120">W poprzednim przykładzie jest tworzony następujący plik XML.</span><span class="sxs-lookup"><span data-stu-id="7ea36-120">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="7ea36-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7ea36-121">See also</span></span>

- [<span data-ttu-id="7ea36-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="7ea36-122">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7ea36-123">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="7ea36-123">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
