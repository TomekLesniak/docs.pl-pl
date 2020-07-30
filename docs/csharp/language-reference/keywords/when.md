---
title: gdy kontekstowe słowo kluczowe — odwołanie w C#
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 2b041ca3a821f45dd63ce3f6bee7a920eb495651
ms.sourcegitcommit: 32f0d6f4c01ddc6ca78767c3a30e3305f8cd032c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2020
ms.locfileid: "87426998"
---
# <a name="when-c-reference"></a>When (odwołanie w C#)

Możesz użyć `when` kontekstowego słowa kluczowego, aby określić warunek filtru w następujących kontekstach:

- W `catch` instrukcji bloku [try/catch](try-catch.md) lub [try/catch/finally](try-catch-finally.md) .
- W `case` etykiecie instrukcji [Switch](switch.md) .
- W [ `switch` wyrażeniu](../operators/switch-expression.md).

## <a name="when-in-a-catch-statement"></a>`when`w `catch` instrukcji

Począwszy od języka C# 6, `when` można użyć w `catch` instrukcji, aby określić warunek, który musi mieć wartość true dla programu obsługi określonego wyjątku do wykonania. Jego składnia to:

```csharp
catch (ExceptionType [e]) when (expr)
```

gdzie *Expr* jest wyrażeniem, którego wynikiem jest wartość logiczna. Jeśli zwróci `true` , program obsługi wyjątków jest wykonywany; Jeśli nie jest `false` .

Poniższy przykład używa `when` słowa kluczowego, aby warunkowo wykonywać procedury obsługi w <xref:System.Net.Http.HttpRequestException> zależności od tekstu komunikatu o wyjątku.

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a>`when`w `switch` instrukcji

Począwszy od języka C# 7,0, `case` etykiety nie muszą być wzajemnie wykluczane, a kolejność, w jakiej `case` etykiety pojawiają się w `switch` instrukcji, może ustalić, który blok przełącznika jest wykonywany. Za pomocą `when` słowa kluczowego można określić warunek filtru, który powoduje, że skojarzona z nim etykieta Case ma wartość true tylko wtedy, gdy warunek filtru ma również wartość true. Jego składnia to:

```csharp
case (expr) when (when-condition):
```

gdzie *Expr* jest wzorcem stałej lub wzorcem typu, który jest porównywany z wyrażeniem Match, a *warunek when* jest dowolnym wyrażeniem logicznym.

Poniższy przykład używa `when` słowa kluczowego do testowania dla `Shape` obiektów, które mają powierzchnię zero, a także do testowania dla różnych `Shape` obiektów, które mają obszar większy niż zero.

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a>Zobacz też

- [switch, instrukcja](switch.md)
- [Instrukcja try/catch](try-catch.md)
- [Instrukcja try/catch/finally](try-catch-finally.md)
