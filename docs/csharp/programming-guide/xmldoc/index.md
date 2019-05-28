---
title: Komentarze dokumentacji XML — C# przewodnik programowania
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: 85d75d6420404f278c4a8b16eb9bf30aff958f7c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645769"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="cd035-102">Komentarze dokumentacji XML (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="cd035-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="cd035-103">W języku Visual C# można tworzyć dokumentację kodu, umieszczając elementy XML w specjalnych polach komentarzy (wskazywanych przez potrójne ukośniki) w kodzie źródłowym bezpośrednio przed blokiem kodu, do którego odwołują się komentarze, na przykład:</span><span class="sxs-lookup"><span data-stu-id="cd035-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="cd035-104">Podczas kompilacji z [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) opcja, kompilator będzie wyszukiwał wszystkie tagi XML w źródle programowanie i tworzenie pliku dokumentacji XML.</span><span class="sxs-lookup"><span data-stu-id="cd035-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="cd035-105">Aby utworzyć dokumentację na podstawie pliku generowanych przez kompilator, możesz utworzyć niestandardowego narzędzia lub użyj narzędzia takiego jak [DocFX](https://dotnet.github.io/docfx/) lub [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="cd035-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="cd035-106">Aby odwołać się do elementów XML (na przykład Twoja funkcja przetwarza określone elementy XML, które użytkownik chce opisać w komentarzu dokumentacji XML), można użyć standardowego mechanizmu cytowania (`<` i `>`).</span><span class="sxs-lookup"><span data-stu-id="cd035-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="cd035-107">Aby odwołać się do identyfikatorów ogólnych w odwołaniu do kodu (`cref`) elementy, można użyć znaków ucieczki (na przykład `cref="List&lt;T&gt;"`) lub nawiasów klamrowych (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="cd035-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="cd035-108">Jest to szczególny przypadek, w którym kompilator analizuje nawiasy klamrowe jako nawiasy kątowe, dzięki czemu komentarz dokumentacji jest wygodniejszy dla autora, gdy ten odwołuje się do identyfikatorów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="cd035-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd035-109">Komentarze dokumentacji XML nie są metadanymi; nie są one uwzględniane w kompilowanym zestawie i dlatego są niedostępne za pośrednictwem mechanizmu odbicia.</span><span class="sxs-lookup"><span data-stu-id="cd035-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd035-110">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="cd035-110">In This Section</span></span>  
  
- [<span data-ttu-id="cd035-111">Zalecane tagi przeznaczone do komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="cd035-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
- [<span data-ttu-id="cd035-112">Przetwarzanie pliku XML</span><span class="sxs-lookup"><span data-stu-id="cd035-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
- [<span data-ttu-id="cd035-113">Ograniczniki tagów dokumentacji</span><span class="sxs-lookup"><span data-stu-id="cd035-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
- [<span data-ttu-id="cd035-114">Instrukcje: Użycie funkcji dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="cd035-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="cd035-115">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="cd035-115">Related Sections</span></span>  
 <span data-ttu-id="cd035-116">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="cd035-116">For more information, see:</span></span>  
  
- [<span data-ttu-id="cd035-117">/ doc (Przetwarzaj komentarze dokumentacji)</span><span class="sxs-lookup"><span data-stu-id="cd035-117">/doc (Process Documentation Comments)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="cd035-118">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="cd035-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd035-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cd035-119">See also</span></span>

- [<span data-ttu-id="cd035-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="cd035-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)