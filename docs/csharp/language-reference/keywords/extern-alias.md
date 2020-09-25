---
description: alias zewnętrzny — odwołanie w C#
title: alias zewnętrzny — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 5ecafa5a989bc183d7f52ac3d4b4d50a81b36014
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203348"
---
# <a name="extern-alias-c-reference"></a>extern alias (odwołanie w C#)

Może zajść konieczność odwołująca się do dwóch wersji zestawów, które mają te same nazwy typów w pełni kwalifikowana. Na przykład może być konieczne użycie co najmniej dwóch wersji zestawu w tej samej aplikacji. Korzystając z zewnętrznego aliasu zestawu, przestrzenie nazw z każdego zestawu mogą być opakowane w przestrzenie nazw poziomu głównego o nazwie alias, co umożliwia ich użycie w tym samym pliku.  
  
> [!NOTE]
> Słowo kluczowe [extern](./extern.md) jest również używane jako modyfikator metody, deklarując metodę zapisaną w kodzie niezarządzanym.  
  
 Aby odwoływać się do dwóch zestawów z tymi samymi w pełni kwalifikowanymi nazwami typu, alias musi być określony w wierszu polecenia w następujący sposób:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Spowoduje to utworzenie aliasów zewnętrznych `GridV1` i `GridV2` . Aby użyć tych aliasów z poziomu programu, odwołując się do nich za pomocą `extern` słowa kluczowego. Na przykład:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Każda deklaracja aliasu zewnętrznego wprowadza dodatkową przestrzeń nazw na poziomie głównym, która jest równoległa (ale nie znajduje się w obrębie) globalnej przestrzeni nazw. Z tego względu typy z każdego zestawu mogą być określane bez niejednoznaczności przy użyciu ich w pełni kwalifikowanej nazwy, w której znajduje się odpowiedni alias przestrzeni nazw.  
  
 W poprzednim przykładzie `GridV1::Grid` jest to formant siatki z, który będzie `grid.dll` `GridV2::Grid` formantem siatki z `grid20.dll` .  
  
## <a name="using-visual-studio"></a>Korzystanie z programu Visual Studio

Jeśli używasz programu Visual Studio, aliasy mogą być udostępniane w podobny sposób.

Dodaj odwołanie do *grid.dll* i *grid20.dll* do projektu w programie Visual Studio. Otwórz kartę właściwości i Zmień aliasy z globalny na GridV1 i GridV2.

Użyj tych aliasów w taki sam sposób, jak powyżej

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

Teraz można utworzyć alias dla przestrzeni nazw lub typu za *pomocą dyrektywy aliasu*. Aby uzyskać więcej informacji, zobacz [Używanie dyrektywy](using-directive.md).

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a>Specyfikacja języka C#  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [:: Operator](../operators/namespace-alias-qualifier.md)
- [-Reference (opcje kompilatora C#)](../compiler-options/reference-compiler-option.md)
