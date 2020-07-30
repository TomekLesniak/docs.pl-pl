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
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>Zalecane Tagi dla komentarzy do dokumentacji (Przewodnik programowania w języku C#)

Kompilator języka C# przetwarza komentarze dokumentacji w kodzie i formatuje je jako XML w pliku, którego nazwa została określona w opcji wiersza polecenia **/doc** . Aby utworzyć ostateczną dokumentację opartą na pliku generowanym przez kompilator, można utworzyć niestandardowe narzędzie lub użyć narzędzia, takiego jak [DocFX](https://dotnet.github.io/docfx/) lub [Sandcastle](https://github.com/EWSoftware/SHFB).

Tagi są przetwarzane na konstrukcjach kodu, takich jak typy i elementy członkowskie typu.

> [!NOTE]
> Komentarzy do dokumentacji nie można zastosować do przestrzeni nazw.  
  
 Kompilator będzie przetwarzać dowolny tag, który jest prawidłowym kodem XML. Poniższe Tagi zapewniają ogólnie używane funkcje w dokumentacji użytkownika.  
  
## <a name="tags"></a>Tagi  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
( \* wskazuje, że kompilator weryfikuje składnię).

Jeśli chcesz, aby w tekście komentarza do dokumentacji pojawiły się nawiasy kątowe, użyj kodowania HTML `<` i, `>` które jest `&lt;` `&gt;` odpowiednio. To kodowanie jest pokazane w poniższym przykładzie.

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [-doc (opcje kompilatora C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Komentarze dokumentacji XML](./index.md)
