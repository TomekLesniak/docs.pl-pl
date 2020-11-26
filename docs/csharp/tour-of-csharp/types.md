---
title: 'Definiowanie typów i ich członków — Przewodnik po języku C #'
description: Bloki konstrukcyjne programów są typami. Dowiedz się, jak tworzyć klasy, struktury, interfejsy i inne w języku C#.
ms.date: 08/06/2020
ms.openlocfilehash: efd353fe8c1e6a57952bcb2586a05ad38ecd52b9
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "88559118"
---
# <a name="types-and-members"></a>Typy i elementy członkowskie

## <a name="classes-and-objects"></a>Klasy i obiekty

*Klasy* są najbardziej podstawą typów języka C#. Klasa jest strukturą danych, która łączy stan (pola) i akcje (metody i inne elementy członkowskie funkcji) w jednej jednostce. Klasa zawiera definicję dla *wystąpień* klasy, znane także jako *obiekty*. Klasy obsługują *dziedziczenie* i *polimorfizm*, natomiast mechanizmy, w których *klasy pochodne* mogą poszerzać i specjalizację *klas bazowych*.

Nowe klasy są tworzone za pomocą deklaracji klasy. Deklaracja klasy zaczyna się od nagłówka. Nagłówek określa:

- Atrybuty i Modyfikatory klasy
- Nazwa klasy
- Klasa bazowa (w przypadku dziedziczenia z [klasy bazowej](#base-classes))
- Interfejsy implementowane przez klasę.

Po tym nagłówku następuje treść klasy, która składa się z listy deklaracji elementów członkowskich, które są zapisywane między ogranicznikami `{` i `}` .

Poniższy kod przedstawia deklarację prostej klasy o nazwie `Point` :

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointClass":::

Wystąpienia klas są tworzone przy użyciu `new` operatora, który przydziela pamięć dla nowego wystąpienia, wywołuje konstruktora w celu zainicjowania wystąpienia i zwraca odwołanie do wystąpienia. Poniższe instrukcje tworzą dwa `Point` obiekty i przechowują odwołania do tych obiektów w dwóch zmiennych:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePoints":::

Pamięć zajęta przez obiekt jest automatycznie odzyskiwana, gdy obiekt nie jest już dostępny. Nie jest to konieczne ani możliwe, aby jawnie cofnąć alokację obiektów w języku C#.

### <a name="type-parameters"></a>Parametry typu

Klasy ogólne definiują [ * **parametry typu** _](../programming-guide/generics/index.md). Parametry typu są lista nazw parametrów typu ujętych w nawiasy ostre. Parametry typu są zgodne z nazwą klasy. Parametry typu mogą być następnie używane w treści deklaracji klasy do definiowania elementów członkowskich klasy. W poniższym przykładzie parametry typu `Pair` są `TFirst` i `TSecond` :

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DefinePairClass":::

Typ klasy zadeklarowanej do wykonania parametrów typu jest nazywany typem klasy _generic *. Typy struktur, interfejsów i delegatów mogą być również rodzajowe.
Gdy używana jest Klasa generyczna, należy podać argumenty typu dla każdego z parametrów typu:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePairObject":::

Typ ogólny z podanymi argumentami typu, jak `Pair<int,string>` powyżej, jest nazywany *typem skonstruowanym*.

### <a name="base-classes"></a>Klas podstawowych

Deklaracja klasy może określać klasę bazową. Postępuj według nazwy klasy i parametrów typu z dwukropkiem i nazwą klasy bazowej. Pominięcie specyfikacji klasy bazowej jest taka sama jak pochodna typu `object` . W poniższym przykładzie klasą bazową `Point3D` jest `Point` . Z pierwszego przykładu klasą bazową `Point` jest `object` :

:::code language="csharp" source="./snippets/shared/Types.cs" ID="Create3DPoint":::

Klasa dziedziczy elementy członkowskie swojej klasy bazowej. Dziedziczenie oznacza, że Klasa niejawnie zawiera prawie wszystkich członków swojej klasy podstawowej. Klasa nie dziedziczy wystąpienia i konstruktorów statycznych i finalizatora. Klasa pochodna może dodawać nowych członków do tych elementów, które dziedziczy, ale nie może usunąć definicji dziedziczonego elementu członkowskiego. W poprzednim przykładzie `Point3D` dziedziczy `X` i `Y` składowe z `Point` , a każde `Point3D` wystąpienie zawiera trzy właściwości, `X` , `Y` , i `Z` .

Niejawna konwersja istnieje z typu klasy do dowolnego z jego typów klas podstawowych. Zmienna typu klasy może odwoływać się do wystąpienia tej klasy lub wystąpienia dowolnej klasy pochodnej. Na przykład uwzględniając poprzednie deklaracje klas, zmienna typu `Point` może odwoływać się do `Point` lub `Point3D` :

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplicitCastToBase":::

## <a name="structs"></a>Struktury

Klasy definiują typy obsługujące dziedziczenie i polimorfizm. Umożliwiają one tworzenie zaawansowanych zachowań opartych na hierarchiach klas pochodnych. Z kolei typy [ * **struct** _](../language-reference/builtin-types/struct.md) to prostsze typy, których głównym celem jest przechowywanie wartości danych. Struktury nie mogą deklarować typu podstawowego; niejawnie pochodzą od <xref:System.ValueType?displayProperty=nameWithType> . Nie można wyprowadzić innych `struct` typów z `struct` typu. Są one niejawnie zapieczętowane.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointStruct":::

## <a name="interfaces"></a>Interfejsy

[_*_Interfejs_*_](../programming-guide/interfaces/index.md) definiuje kontrakt, który może być zaimplementowany przez klasy i struktury. Interfejs może zawierać metody, właściwości, zdarzenia i indeksatory. Interfejs zazwyczaj nie dostarcza implementacji elementów członkowskich, które definiuje — tylko określa elementy członkowskie, które muszą być dostarczone przez klasy lub struktury, które implementują interfejs.

Interfejsy mogą wykorzystywać _*_wielokrotne dziedziczenie_*_. W poniższym przykładzie interfejs `IComboBox` dziedziczy z obu `ITextBox` i `IListBox` .

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FirstInterfaces":::

Klasy i struktury mogą implementować wiele interfejsów. W poniższym przykładzie Klasa `EditBox` implementuje zarówno `IControl` , jak i `IDataBound` .

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplementInterfaces":::

Gdy Klasa lub struktura implementuje określony interfejs, wystąpienia tej klasy lub struktury mogą być niejawnie konwertowane na typ tego interfejsu. Na przykład

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UseInterfaces":::

## <a name="enums"></a>Wyliczenia

Typ [_*_wyliczeniowy_*_](../language-reference/builtin-types/enum.md) definiuje zestaw wartości stałych. Poniżej `enum` deklarują stałe, które definiują różne warzywa główne:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="EnumDeclaration":::

Można również zdefiniować element, `enum` który będzie używany w kombinacji jako flagi. Poniższa deklaracja deklaruje zestaw flag dla czterech sezonów. Można zastosować dowolną kombinację sezonów, w tym `All` wartość obejmującą wszystkie pory roku:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FlagsEnumDeclaration":::

W poniższym przykładzie przedstawiono deklaracje obu powyższych typów wyliczeniowych:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UsingEnums":::

## <a name="nullable-types"></a>Typy dopuszczające wartości null

Zmienne dowolnego typu mogą być deklarowane jako _*_niedopuszczające wartości null_*_ lub _*_dopuszczające wartości null_*_. Zmienna dopuszczający wartości null może zawierać dodatkową `null` wartość wskazującą brak wartości. Typy wartości null (struktury lub wyliczenia) są reprezentowane przez <xref:System.Nullable%601?displayProperty=nameWithType> . Typy referencyjne niedopuszczające wartości null i dopuszczające wartość null są reprezentowane przez odpowiedni typ referencyjny. Rozróżnienie jest reprezentowane przez metadane odczytywane przez kompilator i niektóre biblioteki. Kompilator zawiera ostrzeżenia, gdy odwołania do wartości null są wyłączane bez uprzedniego sprawdzenia ich wartości `null` . Kompilator zawiera również ostrzeżenia, gdy do odwołań nie dopuszczających wartości null są przypisywane wartości, które mogą być `null` . Poniższy przykład deklaruje _*_wartość null int_*_, inicjując ją do `null` . Następnie ustawia wartość na `5` . Pokazuje to samo pojęcie z _*_niezerowym ciągiem_*_. Aby uzyskać więcej informacji, zobacz [typy wartości null](../language-reference/builtin-types/nullable-value-types.md) i [typy referencyjne dopuszczające wartość null](../nullable-references.md).

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareNullable":::

## <a name="tuples"></a>Krotki

Język C# [obsługuje *_krotki_* * _](../language-reference/builtin-types/value-tuples.md), które zapewnia zwięzłą składnię do grupowania wielu elementów danych w lekkiej strukturze danych. Tworzysz wystąpienie krotki przez zadeklarowanie typów i nazw członków między `(` i `)` , jak pokazano w następującym przykładzie:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareTuples":::

Krotki zapewniają alternatywę dla struktury danych z wieloma elementami członkowskimi, bez używania bloków konstrukcyjnych opisanych w następnym artykule.

>[!div class="step-by-step"]
>[Poprzedni](index.md) 
> [Dalej](program-building-blocks.md)
