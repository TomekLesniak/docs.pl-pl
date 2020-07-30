---
title: Przestrzenie nazw — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat przestrzeni nazw w programowaniu języka C#. Zobacz Omówienie właściwości przestrzeni nazw i Wyświetl dodatkowe zasoby.
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: fca2c641520bd9cd19a48bff2119a6f09c3713ea
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382103"
---
# <a name="namespaces-c-programming-guide"></a>Przestrzenie nazw (Przewodnik programowania w języku C#)

Przestrzenie nazw są intensywnie używane w programowaniu języka C# na dwa sposoby. Najpierw platforma .NET używa przestrzeni nazw do organizowania jej wielu klas w następujący sposób:  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<xref:System>jest przestrzenią nazw i <xref:System.Console> jest klasą w tej przestrzeni nazw. `using`Można użyć słowa kluczowego, tak aby pełna nazwa nie była wymagana, jak w poniższym przykładzie:

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]

Aby uzyskać więcej informacji, zobacz [dyrektywa using](../../language-reference/keywords/using-directive.md).

Po drugie, zadeklarowanie własnych przestrzeni nazw może pomóc w kontroli zakresu nazw klas i metod w większych projektach programistycznych. Użyj słowa kluczowego [Namespace](../../language-reference/keywords/namespace.md) , aby zadeklarować przestrzeń nazw, jak w poniższym przykładzie:

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

Nazwa przestrzeni nazw musi być prawidłową [nazwą identyfikatora](../inside-a-program/identifier-names.md)języka C#.

## <a name="namespaces-overview"></a>Przegląd przestrzeni nazw

Przestrzenie nazw mają następujące właściwości:

- Organizują one duże projekty kodu.
- Są one rozdzielane za pomocą `.` operatora.
- `using`Dyrektywa eliminuje konieczność określenia nazwy przestrzeni nazw dla każdej klasy.
- `global`Przestrzeń nazw jest przestrzenią nazw "root": `global::System` zawsze odwołuje się do <xref:System> przestrzeni nazw platformy .NET.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [przestrzenie nazw](~/_csharplang/spec/namespaces.md) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Używanie przestrzeni nazw](using-namespaces.md)
- [Korzystanie z przestrzeni nazw typu My](how-to-use-the-my-namespace.md)
- [Nazwy identyfikatorów](../inside-a-program/identifier-names.md)
- [using — Dyrektywa](../../language-reference/keywords/using-directive.md)
- [:: Operator](../../language-reference/operators/namespace-alias-qualifier.md)
