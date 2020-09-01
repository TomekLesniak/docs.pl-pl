---
description: Odwołanie do języka C#
title: Odwołanie do języka C#
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: 7d78b28479ed6128321207073dc94976710f10b6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138907"
---
# <a name="-c-reference"></a>@ (Odwołanie w C#)

`@`Znak specjalny służy jako identyfikator Verbatim. Może być używana w następujący sposób:

1. Aby włączyć używanie słów kluczowych języka C# jako identyfikatorów. `@`Znak prefiksu elementu kodu, który kompilator ma interpretować jako identyfikator, a nie słowo kluczowe języka C#. Poniższy przykład używa `@` znaku do definiowania identyfikatora o nazwie `for` , który używa w `for` pętli.

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Aby wskazać, że literał ciągu ma być interpretowany Verbatim. `@`Znak w tym wystąpieniu definiuje *literał ciągu Verbatim*. Proste sekwencje ucieczki (takie jak `"\\"` dla ukośnika odwrotnego), szesnastkowe sekwencje ucieczki ( `"\x0041"` na przykład dla Wielkiej litery a) i sekwencje znaków Unicode ( `"\u0041"` na przykład dla Wielkiej litery a) są interpretowane dosłownie. Tylko sekwencja ucieczki oferty ( `""` ) nie jest interpretowana dosłownie; tworzy jeden podwójny cudzysłów. Ponadto w przypadku Verbatim [interpolowanego](interpolated.md) nawiasu klamrowego sekwencje ucieczki ( `{{` i `}}` ) nie są interpretowane dosłownie; tworzą one pojedyncze nawiasy klamrowe. W poniższym przykładzie zdefiniowano dwie identyczne ścieżki plików, jeden przy użyciu zwykłego literału ciągu, a drugi przy użyciu literału ciągu Verbatim. Jest to jeden z najczęściej używanych Verbatim literałów ciągów.

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   Poniższy przykład ilustruje efekt definiowania zwykłego literału ciągu i literału ciągu Verbatim, który zawiera identyczne sekwencje znaków.

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Aby umożliwić kompilatorowi rozróżnienie atrybutów w przypadkach konfliktu nazw. Atrybut jest klasą, która pochodzi od <xref:System.Attribute> . Nazwa typu zwykle zawiera **atrybut**sufiksu, chociaż kompilator nie wymusza tej Konwencji. Atrybut może następnie być przywoływany w kodzie według jego pełnej nazwy typu (na przykład `[InfoAttribute]` lub jego skróconej nazwy (na przykład `[Info]` ). Jednak konflikt nazewnictwa występuje, jeśli dwa skrócone nazwy typów atrybutów są identyczne, a jedna nazwa typu zawiera sufiks **atrybutu** , ale drugi nie. Na przykład następujący kod nie zostanie skompilowany, ponieważ kompilator nie może określić, czy `Info` atrybut lub `InfoAttribute` jest stosowany do `Example` klasy. Aby uzyskać więcej informacji, zobacz [CS1614](../compiler-messages/cs1614.md) .

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Znaki specjalne w języku C#](./index.md)
