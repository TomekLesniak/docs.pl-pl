---
description: volatile — odwołanie w C#
title: volatile — odwołanie w C#
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: bb89e99e8e28ff1e263817f498619dbfae700a50
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141702"
---
# <a name="volatile-c-reference"></a>volatile (odwołanie w C#)

`volatile`Słowo kluczowe wskazuje, że pole może być modyfikowane przez wiele wątków, które są wykonywane w tym samym czasie. Kompilator, system środowiska uruchomieniowego i nawet sprzęt mogą zmieniać rozmieszczenie odczytów i zapisów w lokalizacjach pamięci ze względu na wydajność. Pola, które są zadeklarowane, `volatile` nie podlegają tym optymalizacji. Dodanie `volatile` modyfikatora gwarantuje, że wszystkie wątki będą obserwować nietrwałe zapisy wykonywane przez każdy inny wątek w kolejności, w której zostały wykonane. Nie istnieje gwarancja pojedynczej kolejności zapisów nietrwałych w postaci zaobserwowanej ze wszystkich wątków wykonania.

`volatile`Słowo kluczowe może być stosowane do pól tego typu:

- Typy odwołań.
- Typy wskaźnika (w niebezpiecznym kontekście). Należy zauważyć, że chociaż wskaźnik może być nietrwały, obiekt, do którego wskazuje element, nie może. Innymi słowy, nie można zadeklarować "wskaźnika do nietrwałego".
- Proste typy, takie jak `sbyte` ,,,,,, `byte` ,, `short` `ushort` `int` `uint` `char` `float` i `bool` .
- `enum`Typ z jednym z następujących typów podstawowych: `byte` ,,, `sbyte` , `short` `ushort` `int` lub `uint` .
- Parametry typu ogólnego znane jako typy referencyjne.
- <xref:System.IntPtr> i <xref:System.UIntPtr> .

Inne typy, w tym `double` i `long` , nie mogą być oznaczone `volatile` ponieważ operacje odczytu i zapisu do pól tych typów nie mogą być niepodzielne. Aby chronić wielowątkowy dostęp do tych typów pól, użyj <xref:System.Threading.Interlocked> elementów członkowskich klasy lub Włącz ochronę dostępu przy użyciu [`lock`](lock-statement.md) instrukcji.

`volatile`Słowo kluczowe może być stosowane tylko do pól obiektu `class` lub `struct` . Nie można zadeklarować zmiennych lokalnych `volatile` .

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak zadeklarować zmienną pola publicznego jako `volatile` .

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

W poniższym przykładzie pokazano, jak można utworzyć wątek pomocniczy lub proces roboczy, który będzie używany do przetwarzania równolegle z elementem wątku głównego. Aby uzyskać więcej informacji na temat wielowątkowości, zobacz [zarządzane wątki](../../../standard/threading/index.md).

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

Po `volatile` dodaniu modyfikatora do deklaracji `_shouldStop` na miejscu, zawsze uzyskasz te same wyniki (podobnie jak w powyższym fragmencie kodu). Jednak bez tego modyfikatora `_shouldStop` elementu członkowskiego zachowanie jest nieprzewidywalne. `DoWork`Metoda może zoptymalizować dostęp do elementu członkowskiego, co spowoduje odczytanie starych danych. Ze względu na charakter programowania wielowątkowego liczba nieodświeżonych odczytów jest nieprzewidywalne. Różne uruchomienia programu będą dawać nieco inne wyniki.

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Specyfikacja języka C#: słowo kluczowe volatile](../../../../_csharplang/spec/classes.md#volatile-fields)
- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory](index.md)
- [lock — Instrukcja](lock-statement.md)
- <xref:System.Threading.Interlocked>
