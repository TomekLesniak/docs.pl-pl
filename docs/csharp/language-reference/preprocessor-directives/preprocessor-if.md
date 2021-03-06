---
description: '#Jeśli dyrektywa preprocesora — odwołanie w C#'
title: '#Jeśli dyrektywa preprocesora — odwołanie w C#'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: dc3e235db49279691203a0db4d124239fb972c69
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065240"
---
# <a name="if-c-reference"></a>#if (odwołanie w C#)

Gdy kompilator języka C# napotyka `#if` dyrektywę, a ostatecznie według dyrektywy [#endif](preprocessor-endif.md) , kompiluje kod między dyrektywami tylko wtedy, gdy określony symbol jest zdefiniowany. W przeciwieństwie do C i C++, nie można przypisać wartości liczbowej do symbolu. `#if`Instrukcja w języku C# jest wartością logiczną i tylko testuje, czy symbol został zdefiniowany. Na przykład:

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

Można użyć operatorów [==](../operators/equality-operators.md#equality-operator-) (równość) i [! =](../operators/equality-operators.md#inequality-operator-) (nierówność) tylko do testowania wartości [bool](../builtin-types/bool.md) `true` lub `false` . `true` oznacza, że symbol jest zdefiniowany. Instrukcja `#if DEBUG` ma takie samo znaczenie jak `#if (DEBUG == true)` . Można użyć [&&  (i)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;  (lub)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-)i [! (nie)](../operators/boolean-logical-operators.md#logical-negation-operator-) Operatory umożliwiające ocenę, czy zdefiniowano wiele symboli. Można również grupować symbole i operatory za pomocą nawiasów.

## <a name="remarks"></a>Uwagi

`#if`wraz z [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md)i [#undef](preprocessor-undef.md) umożliwiają uwzględnienie lub wykluczenie kodu na podstawie istnienia jednego lub kilku symboli. Może to być przydatne podczas kompilowania kodu dla kompilacji debugowania lub kompilowania dla określonej konfiguracji.

Dyrektywa warunkowa rozpoczynająca się od `#if` dyrektywy musi być jawnie zakończona `#endif` dyrektywą.

`#define` umożliwia zdefiniowanie symbolu. Używając symbolu jako wyrażenia przesłanego do `#if` dyrektywy, wyrażenie daje w wyniku `true` .

Można również zdefiniować symbol z opcją [-define](../compiler-options/define-compiler-option.md) kompilatora. Możesz oddefiniować symbol z [#undef](preprocessor-undef.md).

Symbol zdefiniowany za pomocą `-define` lub with `#define` nie powoduje konfliktu ze zmienną o tej samej nazwie. Oznacza to, że nazwa zmiennej nie powinna być przenoszona do dyrektywy preprocesora, a symbol może być oceniany tylko przez dyrektywę preprocesora.

Zakres symbolu utworzonego za pomocą `#define` to plik, w którym został zdefiniowany.

System kompilacji jest również świadomy wstępnie zdefiniowanych symboli preprocesora reprezentujących różne [Platformy docelowe](../../../standard/frameworks.md) w projektach w stylu zestawu SDK. Są one przydatne podczas tworzenia aplikacji, które mogą być ukierunkowane na więcej niż jedną wersję platformy .NET.

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> W przypadku tradycyjnych projektów typu non-SDK należy ręcznie skonfigurować symbole kompilacji warunkowej dla różnych platform docelowych w programie Visual Studio za pośrednictwem stron właściwości projektu.

Inne wstępnie zdefiniowane symbole obejmują stałe debugowania i śledzenia. Można zastąpić wartości ustawione dla projektu przy użyciu `#define` . Symbol debugowania, na przykład, jest automatycznie ustawiany w zależności od właściwości konfiguracji kompilacji ("Debugowanie" lub "wersja").

## <a name="examples"></a>Przykłady

W poniższym przykładzie pokazano, jak zdefiniować symbol elementu WebTest dla pliku, a następnie przetestować wartości symboli TEST i DEBUG. Dane wyjściowe tego przykładu zależą od tego, czy projekt został skompilowany w trybie konfiguracji debugowania czy wydania.

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

Poniższy przykład pokazuje, jak przeprowadzić test dla różnych platform docelowych, aby można było używać nowszych interfejsów API, gdy jest to możliwe:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a>Zobacz także

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](index.md)
- [Instrukcje: Kompilowanie warunkowe ze śledzeniem i debugowaniem](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
