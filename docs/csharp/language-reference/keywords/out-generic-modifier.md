---
description: out — słowo kluczowe (modyfikator ogólny) — odwołanie w C#
title: out — słowo kluczowe (modyfikator ogólny) — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 84f3647309c0772f6ae61d3614f8649fe277f153
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142339"
---
# <a name="out-generic-modifier-c-reference"></a>out (modyfikator ogólny) (odwołanie w C#)

W przypadku parametrów typu ogólnego `out` słowo kluczowe Określa, że parametr typu jest współwariantem. Możesz użyć `out` słowa kluczowego w interfejsach ogólnych i delegatach.

Kowariancja umożliwia użycie bardziej pochodnego typu niż określony przez parametr generyczny. Pozwala to na niejawną konwersję klas, które implementują interfejsy współwariantu i niejawną konwersję typów delegatów. Dla typów referencyjnych są obsługiwane Kowariancja i kontrawariancja, ale nie są one obsługiwane w przypadku typów wartości.

Interfejs, który ma parametr typu klasy współdzielonej, umożliwia jej metodom zwrócenie większej liczby typów pochodnych niż te określone przez parametr typu. Na przykład, ponieważ w .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601> , typu T jest współwariantem, można przypisać obiekt `IEnumerable(Of String)` typu do obiektu `IEnumerable(Of Object)` typu bez użycia żadnych specjalnych metod konwersji.

Delegata, do którego można przypisać inny delegat tego samego typu, ale z bardziej pochodnym parametrem typu ogólnego.

Aby uzyskać więcej informacji, zobacz [Kowariancja i kontrawariancja](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="example---covariant-generic-interface"></a>Przykład — interfejs ogólny typu "-Variant"

Poniższy przykład pokazuje, jak zadeklarować, zwiększyć i zaimplementować interfejs ogólny typu "współvariant". Przedstawiono w nim również sposób użycia niejawnej konwersji dla klas, które implementują interfejs współvariant.

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

W interfejsie ogólnym parametr typu może być zadeklarowany jako współwariant, jeśli spełnia następujące warunki:

- Parametr typu jest używany tylko jako typ zwracany metod interfejsu i nie jest używany jako typ argumentów metody.

    > [!NOTE]
    > Istnieje jeden wyjątek dla tej reguły. Jeśli w interfejsie o niezmiennym jest kontrawariantne delegat generyczny jako parametr metody, można użyć typu współwariantu jako parametru typu ogólnego dla tego delegata. Aby uzyskać więcej informacji na temat elementów delegowanych i kontrawariantne ogólnych, zobacz [Wariancja w delegatach](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) i [Używanie wariancji dla delegatów typu Func i akcja](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

- Parametr typu nie jest używany jako ograniczenie ogólne metod interfejsu.

## <a name="example---covariant-generic-delegate"></a>Przykład — delegat generyczny ogólny

Poniższy przykład pokazuje, jak zadeklarować, utworzyć wystąpienie i wywołać delegata ogólnego typu. Pokazuje również, jak niejawnie skonwertować typy delegatów.

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

W delegatze ogólnym typ może być zadeklarowany jako współwariant, jeśli jest używany tylko jako zwracany typ metody i nie jest używany dla argumentów metody.

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Wariancje w interfejsach](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [podczas](in-generic-modifier.md)
- [Modyfikatory](index.md)
