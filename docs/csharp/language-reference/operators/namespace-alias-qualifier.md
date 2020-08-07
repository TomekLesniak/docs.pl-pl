---
title: ':: operator — odwołanie w C#'
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
- global
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: f91287ed281a2c6b10bed93cff10b08972a8445e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855130"
---
# <a name="-operator-c-reference"></a>:: — operator (odwołanie w C#)

Użyj kwalifikatora aliasu przestrzeni nazw `::` w celu uzyskania dostępu do składowej aliasu przestrzeni nazw. Kwalifikator można użyć `::` tylko między dwoma identyfikatorami. Identyfikator po lewej stronie może być jednym z następujących aliasów:

- Alias przestrzeni nazw utworzony za pomocą [dyrektywy aliasu using](../keywords/using-directive.md):

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- [Alias zewnętrzny](../keywords/extern-alias.md).
- `global`Alias, który jest aliasem globalnym przestrzeni nazw. Globalna przestrzeń nazw jest przestrzenią nazw zawierającą przestrzenie nazw i typy, które nie są zadeklarowane w nazwanym obszarze nazw. Gdy jest używany z `::` kwalifikatorem, `global` alias zawsze odwołuje się do globalnej przestrzeni nazw, nawet jeśli istnieje `global` alias przestrzeni nazw zdefiniowany przez użytkownika.

  Poniższy przykład używa `global` aliasu, aby uzyskać dostęp do <xref:System> przestrzeni nazw .NET, która jest elementem członkowskim globalnej przestrzeni nazw. Bez `global` aliasu zdefiniowana przez użytkownika `System` przestrzeń nazw, która jest członkiem `MyCompany.MyProduct` przestrzeni nazw, zostanie uzyskany dostęp:

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }

      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```

  > [!NOTE]
  > `global`Słowo kluczowe jest aliasem globalnym przestrzeni nazw tylko wtedy, gdy jest to identyfikator po lewej stronie `::` kwalifikatora.

Można również użyć [ `.` tokenu](member-access-operators.md#member-access-expression-) , aby uzyskać dostęp do składowej aliasu przestrzeni nazw. `.`Token jest jednak również używany do uzyskiwania dostępu do elementu członkowskiego typu. `::`Kwalifikator gwarantuje, że jego identyfikator po lewej stronie zawsze odwołuje się do aliasu przestrzeni nazw, nawet jeśli istnieje typ lub przestrzeń nazw o tej samej nazwie.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [kwalifikatory aliasów przestrzeni nazw](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Korzystanie z przestrzeni nazw](../../programming-guide/namespaces/using-namespaces.md)
