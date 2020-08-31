---
title: <include> — Przewodnik programowania w języku C#
description: Dowiedz się więcej o kodzie XML <include> seryjn. Ten tag umożliwia odwoływanie się do komentarzy w innym pliku, które opisują typy i elementy członkowskie w kodzie źródłowym.
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: d2de8fea17850685668766bc4ec6e64b1be77cce
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053194"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="53f1d-105">\<include> (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="53f1d-105">\<include> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="53f1d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="53f1d-106">Syntax</span></span>

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a><span data-ttu-id="53f1d-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="53f1d-107">Parameters</span></span>

- `filename`

  <span data-ttu-id="53f1d-108">Nazwa pliku XML zawierającego dokumentację.</span><span class="sxs-lookup"><span data-stu-id="53f1d-108">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="53f1d-109">Nazwa pliku może być kwalifikowana ze ścieżką względną do pliku kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="53f1d-109">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="53f1d-110">Należy ująć `filename` w znaki pojedynczego cudzysłowu (' ').</span><span class="sxs-lookup"><span data-stu-id="53f1d-110">Enclose `filename` in single quotation marks (' ').</span></span>

- `tagpath`

  <span data-ttu-id="53f1d-111">Ścieżka tagów `filename` , które prowadzą do znacznika `name` .</span><span class="sxs-lookup"><span data-stu-id="53f1d-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="53f1d-112">Ujmij ścieżkę w znaki pojedynczego cudzysłowu (' ').</span><span class="sxs-lookup"><span data-stu-id="53f1d-112">Enclose the path in single quotation marks (' ').</span></span>

- `name`

  <span data-ttu-id="53f1d-113">Specyfikator nazwy w tagu, który poprzedza Komentarze; `name` ma `id` .</span><span class="sxs-lookup"><span data-stu-id="53f1d-113">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>

- `id`

  <span data-ttu-id="53f1d-114">Identyfikator tagu, który poprzedza Komentarze.</span><span class="sxs-lookup"><span data-stu-id="53f1d-114">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="53f1d-115">Ujmij identyfikator w znaki podwójnego cudzysłowu ("").</span><span class="sxs-lookup"><span data-stu-id="53f1d-115">Enclose the ID in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="53f1d-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="53f1d-116">Remarks</span></span>

<span data-ttu-id="53f1d-117">`<include>`Tag umożliwia odwoływanie się do komentarzy w innym pliku, które opisują typy i elementy członkowskie w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="53f1d-117">The `<include>` tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="53f1d-118">Jest to alternatywa dla umieszczania komentarzy do dokumentacji bezpośrednio w pliku kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="53f1d-118">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="53f1d-119">Umieszczając dokumentację w osobnym pliku, można zastosować kontrolę źródła do dokumentacji niezależnie od kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="53f1d-119">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="53f1d-120">Jedna osoba może mieć wyewidencjonowany plik kodu źródłowego, a ktoś inny może mieć wyewidencjonowany plik dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="53f1d-120">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>

<span data-ttu-id="53f1d-121">`<include>`Tag używa SKŁADNI XML XPath.</span><span class="sxs-lookup"><span data-stu-id="53f1d-121">The `<include>` tag uses the XML XPath syntax.</span></span> <span data-ttu-id="53f1d-122">Zapoznaj się z dokumentacją XPath, aby dostosowywać swoje `<include>` użycie.</span><span class="sxs-lookup"><span data-stu-id="53f1d-122">Refer to XPath documentation for ways to customize your `<include>` use.</span></span>

## <a name="example"></a><span data-ttu-id="53f1d-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="53f1d-123">Example</span></span>

<span data-ttu-id="53f1d-124">Jest to przykład wieloplikowy.</span><span class="sxs-lookup"><span data-stu-id="53f1d-124">This is a multifile example.</span></span> <span data-ttu-id="53f1d-125">Poniżej znajduje się pierwszy plik, który używa `<include>` .</span><span class="sxs-lookup"><span data-stu-id="53f1d-125">The following is the first file, which uses `<include>`.</span></span>

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

<span data-ttu-id="53f1d-126">Drugi plik, *xml_include_tag.doc*, zawiera następujące komentarze dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="53f1d-126">The second file, *xml_include_tag.doc*, contains the following documentation comments.</span></span>

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a><span data-ttu-id="53f1d-127">Dane wyjściowe programu</span><span class="sxs-lookup"><span data-stu-id="53f1d-127">Program output</span></span>

<span data-ttu-id="53f1d-128">Następujące dane wyjściowe są generowane, gdy kompilujesz klasy test i TEST2 z następującym wierszem polecenia: `-doc:DocFileName.xml.` w programie Visual Studio należy określić opcję komentarzy w dokumencie XML w okienku kompilacja projektanta projektu.</span><span class="sxs-lookup"><span data-stu-id="53f1d-128">The following output is generated when you compile the Test and Test2 classes with the following command line: `-doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="53f1d-129">Gdy kompilator języka C# widzi `<include>` tag, wyszukuje komentarze dokumentacji w *xml_include_tag.doc* zamiast bieżącego pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="53f1d-129">When the C# compiler sees the `<include>` tag, it searches for documentation comments in *xml_include_tag.doc* instead of the current source file.</span></span> <span data-ttu-id="53f1d-130">Następnie kompilator generuje *DocFileName.xml*i jest to plik, który jest używany przez narzędzia dokumentacji, takie jak [Sandcastle](https://github.com/EWSoftware/SHFB) , aby utworzyć ostateczną dokumentację.</span><span class="sxs-lookup"><span data-stu-id="53f1d-130">The compiler then generates *DocFileName.xml*, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a><span data-ttu-id="53f1d-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="53f1d-131">See also</span></span>

- [<span data-ttu-id="53f1d-132">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="53f1d-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="53f1d-133">Zalecane Tagi dla komentarzy dokumentacji</span><span class="sxs-lookup"><span data-stu-id="53f1d-133">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
