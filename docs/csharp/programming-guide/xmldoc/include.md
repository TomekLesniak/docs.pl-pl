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
# <a name="include-c-programming-guide"></a>\<include> (Przewodnik programowania w języku C#)

## <a name="syntax"></a>Składnia

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a>Parametry

- `filename`

  Nazwa pliku XML zawierającego dokumentację. Nazwa pliku może być kwalifikowana ze ścieżką względną do pliku kodu źródłowego. Należy ująć `filename` w znaki pojedynczego cudzysłowu (' ').

- `tagpath`

  Ścieżka tagów `filename` , które prowadzą do znacznika `name` . Ujmij ścieżkę w znaki pojedynczego cudzysłowu (' ').

- `name`

  Specyfikator nazwy w tagu, który poprzedza Komentarze; `name` ma `id` .

- `id`

  Identyfikator tagu, który poprzedza Komentarze. Ujmij identyfikator w znaki podwójnego cudzysłowu ("").

## <a name="remarks"></a>Uwagi

`<include>`Tag umożliwia odwoływanie się do komentarzy w innym pliku, które opisują typy i elementy członkowskie w kodzie źródłowym. Jest to alternatywa dla umieszczania komentarzy do dokumentacji bezpośrednio w pliku kodu źródłowego. Umieszczając dokumentację w osobnym pliku, można zastosować kontrolę źródła do dokumentacji niezależnie od kodu źródłowego. Jedna osoba może mieć wyewidencjonowany plik kodu źródłowego, a ktoś inny może mieć wyewidencjonowany plik dokumentacji.

`<include>`Tag używa SKŁADNI XML XPath. Zapoznaj się z dokumentacją XPath, aby dostosowywać swoje `<include>` użycie.

## <a name="example"></a>Przykład

Jest to przykład wieloplikowy. Poniżej znajduje się pierwszy plik, który używa `<include>` .

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

Drugi plik, *xml_include_tag.doc*, zawiera następujące komentarze dokumentacji.

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

## <a name="program-output"></a>Dane wyjściowe programu

Następujące dane wyjściowe są generowane, gdy kompilujesz klasy test i TEST2 z następującym wierszem polecenia: `-doc:DocFileName.xml.` w programie Visual Studio należy określić opcję komentarzy w dokumencie XML w okienku kompilacja projektanta projektu. Gdy kompilator języka C# widzi `<include>` tag, wyszukuje komentarze dokumentacji w *xml_include_tag.doc* zamiast bieżącego pliku źródłowego. Następnie kompilator generuje *DocFileName.xml*i jest to plik, który jest używany przez narzędzia dokumentacji, takie jak [Sandcastle](https://github.com/EWSoftware/SHFB) , aby utworzyć ostateczną dokumentację.  
  
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
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zalecane Tagi dla komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)
