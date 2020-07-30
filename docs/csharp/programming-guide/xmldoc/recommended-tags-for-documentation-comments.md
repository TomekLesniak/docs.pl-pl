---
title: Zalecane Tagi dla komentarzy do dokumentacji — Przewodnik programowania w języku C#
description: Dowiedz się więcej o zalecanych tagach dla komentarzy do dokumentacji. Zapoznaj się z listą zalecanych tagów i Wyświetl dodatkowe dostępne zasoby.
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 65bca6f979c5ffd91507b571a4f049377315192d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381518"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="73054-104">Zalecane Tagi dla komentarzy do dokumentacji (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="73054-104">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="73054-105">Kompilator języka C# przetwarza komentarze dokumentacji w kodzie i formatuje je jako XML w pliku, którego nazwa została określona w opcji wiersza polecenia **/doc** .</span><span class="sxs-lookup"><span data-stu-id="73054-105">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="73054-106">Aby utworzyć ostateczną dokumentację opartą na pliku generowanym przez kompilator, można utworzyć niestandardowe narzędzie lub użyć narzędzia, takiego jak [DocFX](https://dotnet.github.io/docfx/) lub [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="73054-106">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="73054-107">Tagi są przetwarzane na konstrukcjach kodu, takich jak typy i elementy członkowskie typu.</span><span class="sxs-lookup"><span data-stu-id="73054-107">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="73054-108">Komentarzy do dokumentacji nie można zastosować do przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="73054-108">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="73054-109">Kompilator będzie przetwarzać dowolny tag, który jest prawidłowym kodem XML.</span><span class="sxs-lookup"><span data-stu-id="73054-109">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="73054-110">Poniższe Tagi zapewniają ogólnie używane funkcje w dokumentacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="73054-110">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="73054-111">Tagi</span><span class="sxs-lookup"><span data-stu-id="73054-111">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
<span data-ttu-id="73054-112">( \* wskazuje, że kompilator weryfikuje składnię).</span><span class="sxs-lookup"><span data-stu-id="73054-112">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="73054-113">Jeśli chcesz, aby w tekście komentarza do dokumentacji pojawiły się nawiasy kątowe, użyj kodowania HTML `<` i, `>` które jest `&lt;` `&gt;` odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="73054-113">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="73054-114">To kodowanie jest pokazane w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="73054-114">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="73054-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="73054-115">See also</span></span>

- [<span data-ttu-id="73054-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="73054-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="73054-117">-doc (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="73054-117">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="73054-118">Komentarze dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="73054-118">XML documentation comments</span></span>](./index.md)
