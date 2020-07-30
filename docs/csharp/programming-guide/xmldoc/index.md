---
title: Komentarze dokumentacji XML — Przewodnik programowania w języku C#
description: Dowiedz się więcej o komentarzach dokumentacji XML. Można utworzyć dokumentację dla kodu, dołączając elementy XML w specjalnych polach komentarzy.
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
ms.openlocfilehash: fbdeb53331d9fc63d24a3322ea13863d7c0a3630
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381882"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Komentarze dokumentacji XML (Przewodnik programowania w języku C#)

W języku C# można utworzyć dokumentację dla kodu, dołączając elementy XML w specjalnych polach komentarzy (oznaczone przez potrójne ukośniki) w kodzie źródłowym bezpośrednio przed blokiem kodu, do którego odwołuje się komentarz, na przykład.

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

Podczas kompilowania przy użyciu opcji [-doc](../../language-reference/compiler-options/doc-compiler-option.md) kompilator przeszuka wszystkie tagi XML w kodzie źródłowym i utworzy plik dokumentacji XML. Aby utworzyć ostateczną dokumentację opartą na pliku generowanym przez kompilator, można utworzyć niestandardowe narzędzie lub użyć narzędzia, takiego jak [DocFX](https://dotnet.github.io/docfx/) lub [Sandcastle](https://github.com/EWSoftware/SHFB).

Aby odwołać się do elementów XML (na przykład funkcja przetwarza konkretne elementy XML, które chcesz opisać w komentarzu dokumentacji XML), można użyć standardowego mechanizmu quota ( `<` i `>` ).  Aby odwołać się do identyfikatorów ogólnych w elementach Reference Code ( `cref` ), można użyć znaków ucieczki (na przykład `cref="List&lt;T&gt;"` ) lub nawiasów klamrowych ( `cref="List{T}"` ).  Jest to szczególny przypadek, w którym kompilator analizuje nawiasy klamrowe jako nawiasy kątowe, dzięki czemu komentarz dokumentacji jest wygodniejszy dla autora, gdy ten odwołuje się do identyfikatorów ogólnych.

> [!NOTE]
> Komentarze dokumentacji XML nie są metadanymi; nie są one uwzględniane w kompilowanym zestawie i dlatego są niedostępne za pośrednictwem mechanizmu odbicia.

## <a name="in-this-section"></a>W tej sekcji

- [Zalecane tagi przeznaczone do komentarzy dokumentacji](./recommended-tags-for-documentation-comments.md)

- [Przetwarzanie pliku XML](./processing-the-xml-file.md)

- [Ograniczniki tagów dokumentacji](./delimiters-for-documentation-tags.md)

- [Używanie funkcji dokumentacji XML](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a>Sekcje pokrewne

Aby uzyskać więcej informacji, zobacz:

- [-doc (Przetwarzaj komentarze dokumentacji)](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
