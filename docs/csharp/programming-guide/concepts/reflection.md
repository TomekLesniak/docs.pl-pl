---
title: Odbicie (C#)
description: Odbicie zawiera obiekty, które opisują zestawy, moduły i typy w języku C#. Jeśli kod zawiera atrybuty, odbicie umożliwia uzyskanie dostępu do nich.
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4d4f4c082dd2d58e212bae53524e5dd4fd06fb75
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302805"
---
# <a name="reflection-c"></a>Odbicie (C#)

Odbicie zawiera obiekty (typu <xref:System.Type> ) opisujące zestawy, moduły i typy. Możesz użyć odbicia, aby dynamicznie utworzyć wystąpienie typu, powiązać typ z istniejącym obiektem lub uzyskać typ z istniejącego obiektu i wywołać jego metody lub uzyskać dostęp do jego pól i właściwości. Jeśli używasz atrybutów w kodzie, odbicie umożliwia uzyskanie dostępu do nich. Aby uzyskać więcej informacji, zobacz [atrybuty](../../../standard/attributes/index.md).

Oto prosty przykład odbicia przy użyciu <xref:System.Object.GetType> metody dziedziczonej przez wszystkie typy z `Object` klasy podstawowej — w celu uzyskania typu zmiennej:

> [!NOTE]
> Upewnij się, że dodano `using System;` i `using System.Reflection;` w górnej części pliku *CS* .

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

Wynik: `System.Int32` .

Poniższy przykład używa odbicia w celu uzyskania pełnej nazwy załadowanego zestawu.

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

Wynik: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e` .

> [!NOTE]
> Słowa kluczowe języka C# `protected` i nie `internal` mają znaczenia w Il i nie są używane w interfejsach API odbicia. Odpowiednie warunki w IL są *rodziną* i *zestawem*. Aby zidentyfikować `internal` metodę przy użyciu odbicia, należy użyć <xref:System.Reflection.MethodBase.IsAssembly%2A> właściwości. Aby zidentyfikować `protected internal` metodę, użyj <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> .

## <a name="reflection-overview"></a>Przegląd odbicia

Odbicie jest przydatne w następujących sytuacjach:

- Gdy musisz uzyskać dostęp do atrybutów w metadanych programu. Aby uzyskać więcej informacji, zobacz artykuł [pobieranie informacji przechowywanych w atrybutach](../../../standard/attributes/retrieving-information-stored-in-attributes.md).
- Do badania i tworzenia wystąpień typów w zestawie.
- Do kompilowania nowych typów w czasie wykonywania. Użyj klas w <xref:System.Reflection.Emit> .
- Do wykonywania późnego wiązania, uzyskiwanie dostępu do metod w typach utworzonych w czasie wykonywania. Zobacz temat [dynamiczne ładowanie i używanie typów](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).

## <a name="related-sections"></a>Sekcje pokrewne

Więcej informacji:

- [Odbicie](../../../framework/reflection-and-codedom/reflection.md)
- [Wyświetlanie informacji o typie](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [Odbicie i typy ogólne](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [Pobieranie informacji przechowywanych w atrybutach](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Zestawy w środowisku .NET](../../../standard/assembly/index.md)
