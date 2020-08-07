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
# <a name="-operator-c-reference"></a><span data-ttu-id="54ade-102">:: — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="54ade-102">:: operator (C# reference)</span></span>

<span data-ttu-id="54ade-103">Użyj kwalifikatora aliasu przestrzeni nazw `::` w celu uzyskania dostępu do składowej aliasu przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="54ade-103">Use the namespace alias qualifier `::` to access a member of an aliased namespace.</span></span> <span data-ttu-id="54ade-104">Kwalifikator można użyć `::` tylko między dwoma identyfikatorami.</span><span class="sxs-lookup"><span data-stu-id="54ade-104">You can use the `::` qualifier only between two identifiers.</span></span> <span data-ttu-id="54ade-105">Identyfikator po lewej stronie może być jednym z następujących aliasów:</span><span class="sxs-lookup"><span data-stu-id="54ade-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="54ade-106">Alias przestrzeni nazw utworzony za pomocą [dyrektywy aliasu using](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="54ade-106">A namespace alias created with a [using alias directive](../keywords/using-directive.md):</span></span>

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="54ade-107">[Alias zewnętrzny](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="54ade-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="54ade-108">`global`Alias, który jest aliasem globalnym przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="54ade-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="54ade-109">Globalna przestrzeń nazw jest przestrzenią nazw zawierającą przestrzenie nazw i typy, które nie są zadeklarowane w nazwanym obszarze nazw.</span><span class="sxs-lookup"><span data-stu-id="54ade-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="54ade-110">Gdy jest używany z `::` kwalifikatorem, `global` alias zawsze odwołuje się do globalnej przestrzeni nazw, nawet jeśli istnieje `global` alias przestrzeni nazw zdefiniowany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="54ade-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>

  <span data-ttu-id="54ade-111">Poniższy przykład używa `global` aliasu, aby uzyskać dostęp do <xref:System> przestrzeni nazw .NET, która jest elementem członkowskim globalnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="54ade-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="54ade-112">Bez `global` aliasu zdefiniowana przez użytkownika `System` przestrzeń nazw, która jest członkiem `MyCompany.MyProduct` przestrzeni nazw, zostanie uzyskany dostęp:</span><span class="sxs-lookup"><span data-stu-id="54ade-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

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
  > <span data-ttu-id="54ade-113">`global`Słowo kluczowe jest aliasem globalnym przestrzeni nazw tylko wtedy, gdy jest to identyfikator po lewej stronie `::` kwalifikatora.</span><span class="sxs-lookup"><span data-stu-id="54ade-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="54ade-114">Można również użyć [ `.` tokenu](member-access-operators.md#member-access-expression-) , aby uzyskać dostęp do składowej aliasu przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="54ade-114">You can also use the [`.` token](member-access-operators.md#member-access-expression-) to access a member of an aliased namespace.</span></span> <span data-ttu-id="54ade-115">`.`Token jest jednak również używany do uzyskiwania dostępu do elementu członkowskiego typu.</span><span class="sxs-lookup"><span data-stu-id="54ade-115">However, the `.` token is also used to access a type member.</span></span> <span data-ttu-id="54ade-116">`::`Kwalifikator gwarantuje, że jego identyfikator po lewej stronie zawsze odwołuje się do aliasu przestrzeni nazw, nawet jeśli istnieje typ lub przestrzeń nazw o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="54ade-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="54ade-117">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="54ade-117">C# language specification</span></span>

<span data-ttu-id="54ade-118">Aby uzyskać więcej informacji, zobacz sekcję [kwalifikatory aliasów przestrzeni nazw](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="54ade-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54ade-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="54ade-119">See also</span></span>

- [<span data-ttu-id="54ade-120">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="54ade-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="54ade-121">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="54ade-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="54ade-122">Korzystanie z przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="54ade-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
