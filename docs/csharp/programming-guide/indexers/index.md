---
title: Indeksatory — Przewodnik programowania w języku C#
description: Indeksatory w języku C# zezwalają na indeksowanie wystąpień klasy lub struktury, takich jak tablice. Można ustawić lub pobrać wartość indeksowaną bez określenia typu lub elementu członkowskiego wystąpienia.
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: ea95eef7bb9ba232e4d59e3f833b82e98398fc33
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495307"
---
# <a name="indexers-c-programming-guide"></a>Indeksatory (Przewodnik programowania w języku C#)

Indeksatory umożliwiają indeksowanie wystąpień klasy lub struktury tak samo jak w przypadku tablic. Indeksowaną wartość można ustawić lub pobrać bez jawnego określenia typu lub elementu członkowskiego wystąpienia. Indeksatory przypominają [Właściwości](../classes-and-structs/properties.md) , z tą różnicą, że ich metody dostępu pobierają parametry.  

 W poniższym przykładzie zdefiniowano klasę generyczną z prostymi metodami dostępu [Get](../../language-reference/keywords/get.md) i [Set](../../language-reference/keywords/set.md) do przypisywania i pobierania wartości. `Program`Klasa tworzy wystąpienie tej klasy do przechowywania ciągów.  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> Aby uzyskać więcej przykładów, zobacz sekcję [pokrewne](./index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Definicje treści wyrażenia  

Metoda dostępu "Get" lub "Set" może składać się z pojedynczej instrukcji, która zwraca lub ustawia wartość. Składowe w postaci wyrażeń zawierają uproszczoną składnię do obsługi tego scenariusza. Począwszy od języka C# 6, indeksator tylko do odczytu może być implementowany jako składowa z wyrażeniem, jak pokazano w poniższym przykładzie.

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Należy zauważyć, że `=>` wprowadza treść wyrażenia, a `get` słowo kluczowe nie jest używane.

Począwszy od języka C# 7,0, zarówno metoda dostępu get, jak i set może być zaimplementowana jako składowe z wyrażeniami. W takim przypadku `get` `set` należy użyć słów kluczowych i. Przykład:

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Omówienie indeksatorów  
  
- Indeksatory umożliwiają indeksowanie obiektów w podobny sposób do tablic.  
  
- `get`Metoda dostępu zwraca wartość. `set`Metoda dostępu przypisuje wartość.  
  
- [To](../../language-reference/keywords/this.md) słowo kluczowe jest używane do definiowania indeksatora.  
  
- Słowo kluczowe [Value](../../language-reference/keywords/value.md) służy do definiowania wartości przypisywanej przez `set` metodę dostępu.  
  
- Indeksatory nie muszą być indeksowane przez wartość całkowitą; Istnieje możliwość zdefiniowania określonego mechanizmu wyszukiwania.  
  
- Indeksatory mogą być przeciążone.  
  
- Indeksatory mogą mieć więcej niż jeden parametr formalny, na przykład podczas uzyskiwania dostępu do tablicy dwuwymiarowej.  
  
## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> Sekcje pokrewne  
  
- [Używanie indeksatorów](./using-indexers.md)  
  
- [Indeksatory w interfejsach](./indexers-in-interfaces.md)  
  
- [Porównanie właściwości i indeksatorów](./comparison-between-properties-and-indexers.md)  
  
- [Ograniczanie dostępności metody dostępu](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [indeksatory](~/_csharplang/spec/classes.md#indexers) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.
  
## <a name="see-also"></a>Zobacz także

- [Przewodnik programowania w języku C#](../index.md)
- [Właściwości](../classes-and-structs/properties.md)
