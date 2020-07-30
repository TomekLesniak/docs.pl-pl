---
title: Elementy członkowskie w postaci wyrażeń — Przewodnik programowania w języku C#
description: Dowiedz się więcej o elementach składowych wyrażeń. Zobacz przykłady kodu, które używają definicji treści wyrażenia dla właściwości, konstruktorów, finalizatorów i innych.
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: e68e96e4aa3ff6a64590459a7197da1833e1a275
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381661"
---
# <a name="expression-bodied-members-c-programming-guide"></a>Elementy członkowskie z wyrażeniami (Przewodnik programowania w języku C#)

Definicje treści wyrażenia pozwalają zapewnić implementację elementu członkowskiego w bardzo zwięzłej, czytelnej postaci. Można użyć definicji treści wyrażenia za każdym razem, gdy logika dowolnego obsługiwanego elementu członkowskiego, takiego jak metoda lub właściwość, składa się z jednego wyrażenia. Definicja treści wyrażenia ma następującą składnię ogólną:

```csharp
member => expression;
```

*wyrażenie* WHERE jest prawidłowym wyrażeniem.

Obsługa definicji treści wyrażenia została wprowadzona dla metod i właściwości tylko do odczytu w języku C# 6 i została rozwinięta w języku C# 7,0. Definicje treści wyrażenia mogą być używane z elementami członkowskimi typu wymienionymi w poniższej tabeli:

|Członek  |Obsługiwane przez... |
|---------|---------|
|[Metoda](#methods)  |C# 6 |
|[Właściwość tylko do odczytu](#read-only-properties)   |C# 6  |
|[Właściwość](#properties)  |C# 7.0 |
|[Konstruktor](#constructors)   |C# 7.0 |
|[Finalizator](#finalizers)     |C# 7.0 |
|[Indeksator](#indexers)       |C# 7.0 |

## <a name="methods"></a>Metody

Metoda zabudowana wyrażenia składa się z pojedynczego wyrażenia, które zwraca wartość, której typ pasuje do typu zwracanego metody lub dla metod zwracających `void` , które wykonują pewne operacje. Na przykład typy, które zastępują <xref:System.Object.ToString%2A> metodę, zazwyczaj obejmują pojedyncze wyrażenie, które zwraca reprezentację ciągu bieżącego obiektu.

W poniższym przykładzie zdefiniowano `Person` klasę, która zastępuje <xref:System.Object.ToString%2A> metodę z definicją treści wyrażenia. Definiuje także `DisplayName` metodę, która wyświetla nazwę konsoli programu. Należy zauważyć, że `return` słowo kluczowe nie jest używane w `ToString` definicji treści wyrażenia.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Aby uzyskać więcej informacji, zobacz [metody (Przewodnik programowania w języku C#)](../classes-and-structs/methods.md).

## <a name="read-only-properties"></a>Właściwości tylko do odczytu

Począwszy od języka C# 6, można użyć definicji treści wyrażenia, aby zaimplementować właściwość tylko do odczytu. W tym celu należy użyć następującej składni:

```csharp
PropertyType PropertyName => expression;
```

W poniższym przykładzie zdefiniowano `Location` klasę, której właściwość tylko do odczytu `Name` jest zaimplementowana jako definicja treści wyrażenia, która zwraca wartość `locationName` pola prywatnego:

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Aby uzyskać więcej informacji na temat właściwości, zobacz [właściwości (Przewodnik programowania w języku C#)](../classes-and-structs/properties.md).

## <a name="properties"></a>Właściwości

Począwszy od języka C# 7,0, można użyć definicji treści wyrażenia do implementowania właściwości `get` i `set` metod dostępu. Poniższy przykład ilustruje, jak to zrobić:

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

Aby uzyskać więcej informacji na temat właściwości, zobacz [właściwości (Przewodnik programowania w języku C#)](../classes-and-structs/properties.md).

## <a name="constructors"></a>Konstruktory

Definicja treści wyrażenia dla konstruktora zwykle składa się z pojedynczego wyrażenia przypisania lub wywołania metody, które obsługuje argumenty konstruktora lub inicjuje stan wystąpienia.

W poniższym przykładzie zdefiniowano `Location` klasę, której Konstruktor ma jeden parametr ciągu o nazwie *name*. Definicja treści wyrażenia przypisuje argument do `Name` właściwości.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Aby uzyskać więcej informacji, zobacz [konstruktory (Przewodnik programowania w języku C#)](../classes-and-structs/constructors.md).

## <a name="finalizers"></a>Finalizatory

Definicja treści wyrażenia dla finalizatora zwykle zawiera instrukcje czyszczenia, takie jak instrukcje zwalniania niezarządzanych zasobów.

W poniższym przykładzie zdefiniowano finalizator, który używa definicji treści wyrażenia, aby wskazać, że finalizator został wywołany.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

Aby uzyskać więcej informacji, zobacz [finalizatory (Przewodnik programowania w języku C#)](../classes-and-structs/destructors.md).

## <a name="indexers"></a>Indexers (Indeksatory)

Podobnie jak w przypadku właściwości, indeksator i Akcesory `get` `set` składają się z definicji treści wyrażenia, jeśli `get` metoda dostępu składa się z jednego wyrażenia, które zwraca wartość lub `set` metoda dostępu wykonuje proste przypisanie.

W poniższym przykładzie zdefiniowano klasę o nazwie `Sports` , która zawiera <xref:System.String> tablicę wewnętrzną, która zawiera nazwy wielu sportowych. Zarówno indeksator `get` , jak i metody `set` dostępu są zaimplementowane jako definicje treści wyrażenia.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

Aby uzyskać więcej informacji, zobacz [indeksatory (Przewodnik programowania w języku C#)](../indexers/index.md).
