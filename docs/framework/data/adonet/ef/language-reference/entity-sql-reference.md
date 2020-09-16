---
title: Informacje Entity SQL
ms.date: 03/30/2017
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
ms.openlocfilehash: 987aa5c05b88d684e050721077d704b29e546aab
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542127"
---
# <a name="entity-sql-reference"></a>Informacje Entity SQL

Ta sekcja zawiera Entity SQL artykułów referencyjnych. Ten artykuł podsumowuje i grupuje operatory Entity SQL według kategorii.

## <a name="arithmetic-operators"></a>Operatory arytmetyczne

Operatory arytmetyczne wykonują operacje matematyczne na dwóch wyrażeniach z co najmniej jednym typem danych liczbowych. W poniższej tabeli wymieniono operatory arytmetyczne Entity SQL:

|Operator|Zastosowanie|
|--------------|---------|
|[+ (Dodaj)](add.md)|Dodatkowo.|
|[/ (Dzielenie)](divide-entity-sql.md)|Przegrod.|
|[% (Modulo)](modulo-entity-sql.md)|Zwraca resztę z dzielenia.|
|[* (Mnożenie)](multiply-entity-sql.md)|Mnożenia.|
|[- (Ujemne)](negative-entity-sql.md)|Negacji.|
|[- (Odejmowanie)](subtract-entity-sql.md)|Odejmowania.|

## <a name="canonical-functions"></a>Funkcje kanoniczne

Funkcje kanoniczne są obsługiwane przez wszystkich dostawców danych i mogą być używane przez wszystkie technologie zapytań. W poniższej tabeli wymieniono funkcje kanoniczne:

|Funkcja|Typ|
|--------------|----------|
|[Agreguj Entity SQL funkcje kanoniczne](aggregate-canonical-functions.md)|Omawia funkcje agregujące Entity SQL w postaci kanonicznej.|
|[Funkcje matematyczne Canonical](math-canonical-functions.md)|Omawia Entity SQL funkcje kanoniczne matematyczne.|
|[Funkcje ciągów Canonical](string-canonical-functions.md)|Omawia ciąg Entity SQL funkcje kanoniczne.|
|[Funkcji daty i godziny Canonical](date-and-time-canonical-functions.md)|Omawia datę i godzinę Entity SQL funkcje kanoniczne.|
|[Funkcje bitowe Canonical](bitwise-canonical-functions.md)|Omawia bitowe Entity SQL funkcje kanoniczne.|
|[Inne funkcje Canonical](other-canonical-functions.md)|Omawia funkcje niesklasyfikowane jako bitowe, daty/godziny, String, Math lub Aggregate.|

## <a name="comparison-operators"></a>Operatory porównania

Operatory porównania są zdefiniowane dla następujących typów:,,,,,,,,,, `Byte` `Int16` `Int32` `Int64` `Double` `Single` `Decimal` `String` `DateTime` `Date` `Time` , `DateTimeOffset` . Niejawna Promocja typu występuje dla operandów przed zastosowaniem operatora porównania. Operatory porównania zawsze zwracają wartości logiczne. Gdy co najmniej jeden z operandów ma wartość `null` , wynik jest `null` .

Równość i nierówność są zdefiniowane dla dowolnego typu obiektu, który ma tożsamość, taką jak `Boolean` Typ. Obiekty inne niż pierwotne z tożsamością są uważane za równe, jeśli korzystają z tej samej tożsamości. W poniższej tabeli wymieniono Entity SQL operatory porównania:

|Operator|Opis|
|--------------|-----------------|
|[= (Równa się)](equals-entity-sql.md)|Porównuje równość dwóch wyrażeń.|
|[> (Większe niż)](greater-than-entity-sql.md)|Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość większą niż prawo wyrażenie.|
|[>= (Większe niż lub równe)](greater-than-or-equal-to-entity-sql.md)|Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość większą lub równą prawemu wyrażeniu.|
|[\[nie ma \] wartości null](isnull-entity-sql.md)|Określa, czy wyrażenie zapytania ma wartość null.|
|[< (Mniejsze niż)](less-than-entity-sql.md)|Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość mniejszą niż prawo wyrażenie.|
|[<= (Mniejsze niż lub równe)](less-than-or-equal-to-entity-sql.md)|Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość mniejszą lub równą prawemu wyrażeniu.|
|[\[NIE \] pomiędzy](between-entity-sql.md)|Określa, czy wynikiem wyrażenia jest wartość w określonym zakresie.|
|[\!= (Nie równa się)](not-equal-to-entity-sql.md)|Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie nie jest równe wyrażeniu z prawej strony.|
|[\[NIE \] przypomina](like-entity-sql.md)|Określa, czy określony ciąg znaków jest zgodny z określonym wzorcem.|

## <a name="logical-and-case-expression-operators"></a>Operatory wyrażenia logicznego i Case

Test operatorów logicznych dla prawdy warunku. Wyrażenie CASE oblicza zestaw wyrażeń logicznych, aby określić wynik. W poniższej tabeli wymieniono operatory logiczne i wyrażenia CASE:

|Operator|Opis|
|--------------|-----------------|
|[&&  (koniunkcja logiczna i)](and-entity-sql.md)|Koniunkcja logiczna i.|
|[\! (Logiczne NOT)](not-entity-sql.md)|NIE ma logicznego.|
|[&#124;&#124;  (logiczne lub)](or-entity-sql.md)|Logiczne OR.|
|[SPRAW](case-entity-sql.md)|Oblicza zestaw wyrażeń logicznych, aby określić wynik.|
|[NASTĘPNIE](then-entity-sql.md)|Wynik klauzuli [when](/previous-versions/dotnet/netframework-4.0/bb387119(v=vs.100)) , gdy wartość jest równa true.|

## <a name="query-operators"></a>Operatory zapytań

Operatory zapytań są używane do definiowania wyrażeń zapytania, które zwracają dane jednostki. W poniższej tabeli wymieniono operatory zapytań:

|Operator|Zastosowanie|
|--------------|---------|
|[FROM](from-entity-sql.md)|Określa kolekcję, która jest używana w instrukcjach [SELECT](select-entity-sql.md) .|
|[GROUP BY](group-by-entity-sql.md)|Określa grupy, w których obiekty zwracane przez zapytanie ([SELECT](select-entity-sql.md)) mają zostać umieszczone.|
|[GroupPartition](grouppartition-entity-sql.md)|Zwraca kolekcję wartości argumentów, które są rzutowane na partycję grupy, z którą jest powiązana agregacja.|
|[HAVING](having-entity-sql.md)|Określa warunek wyszukiwania dla grupy lub agregacji.|
|[GRANICE](limit-entity-sql.md)|Używany z klauzulą [order by](order-by-entity-sql.md) do wykonywania stronicowania fizycznego.|
|[ORDER BY](order-by-entity-sql.md)|Określa kolejność sortowania, która jest używana dla obiektów zwracanych w instrukcji [SELECT](select-entity-sql.md) .|
|[ZAZNACZENIA](select-entity-sql.md)|Określa elementy w projekcji, które są zwracane przez zapytanie.|
|[Skocz](skip-entity-sql.md)|Używany z klauzulą [order by](order-by-entity-sql.md) do wykonywania stronicowania fizycznego.|
|[Do góry](top-entity-sql.md)|Określa, że tylko pierwszy zestaw wierszy zostanie zwrócony z wyniku zapytania.|
|[WHERE](where-entity-sql.md)|Warunkowe filtrowanie danych zwracanych przez zapytanie.|

## <a name="reference-operators"></a>Operatory odwołań

Odwołanie jest wskaźnikiem logicznym (kluczem obcym) do określonej jednostki w określonym zestawie jednostek. Entity SQL obsługuje następujące operatory do konstruowania, dekonstrukcji i nawigowania po odwołaniach:

|Operator|Zastosowanie|
|--------------|---------|
|[CREATEREF](createref-entity-sql.md)|Tworzy odwołania do jednostki w zestawie jednostek.|
|[DEREF](deref-entity-sql.md)|Odwołuje się do wartości odniesienia i tworzy wynik tego odwołania.|
|[GŁÓWNYCH](key-entity-sql.md)|Wyodrębnia klucz odwołania lub wyrażenia jednostki.|
|[NIMI](navigate-entity-sql.md)|Umożliwia nawigowanie po relacjach z jednego typu jednostki do innego|
|[UMIESZCZONE](ref-entity-sql.md)|Zwraca odwołanie do wystąpienia jednostki.|

## <a name="set-operators"></a>Ustaw operatory

Entity SQL oferuje różne Zaawansowane operacje zestawu. Obejmuje to operatory ustawiające podobne do operatorów Transact-SQL, takich jak UNION, INTERSECT, EXCEPT i EXISTS. Entity SQL obsługuje również operatory do usuwania duplikatów (SET), testowania członkostwa (w programie) i sprzężeń (JOIN). W poniższej tabeli wymieniono operatory zestawu Entity SQL:

|Operator|Zastosowanie|
|--------------|---------|
|[ANYELEMENT](anyelement-entity-sql.md)|Wyodrębnia element z kolekcji wielowartościowej.|
|[EXCEPT](except-entity-sql.md)|Zwraca kolekcję wszystkich odrębnych wartości z wyrażenia zapytania na lewo od operandu EXCEPT, które nie są zwracane z wyrażenia zapytania na prawo od operandu EXCEPT.|
|[\[NIE \] istnieje](exists-entity-sql.md)|Określa, czy kolekcja jest pusta.|
|[FLATTEN](flatten-entity-sql.md)|Konwertuje kolekcję kolekcji na spłaszczoną kolekcję.|
|[\[NIE \] w](in-entity-sql.md)|Określa, czy wartość jest zgodna z dowolną wartością w kolekcji.|
|[INTERSECT](intersect-entity-sql.md)|Zwraca kolekcję wszelkich unikatowych wartości, które są zwracane przez wyrażenia zapytania po lewej stronie i po prawej stronie operandu INTERSECT.|
|[OVERLAPS](overlaps-entity-sql.md)|Określa, czy dwie kolekcje mają wspólne elementy.|
|[ZBIÓR](set-entity-sql.md)|Służy do konwertowania kolekcji obiektów do zestawu przez wypróbowanie nowej kolekcji z usuniętymi wszystkimi zduplikowanymi elementami.|
|[Unii](union-entity-sql.md)|Łączy wyniki dwóch lub więcej zapytań w jedną kolekcję.|

## <a name="type-operators"></a>Operatory typów

Entity SQL zawiera operacje, które umożliwiają konstruowanie typu wyrażenia (wartości), zapytania i manipulowanie nimi. W poniższej tabeli wymieniono operatory, które są używane do pracy z typami:

|Operator|Zastosowanie|
|--------------|---------|
|[CAST](cast-entity-sql.md)|Konwertuje wyrażenie jednego typu danych na inne.|
|[ZBIERA](collection-entity-sql.md)|Używane w operacji [funkcji](function-entity-sql.md) do deklarowania kolekcji typów jednostek lub typów złożonych.|
|[\[nie jest \]](isof-entity-sql.md)|Określa, czy typ wyrażenia jest określonego typu czy jednego z jego podtypów.|
|[OFTYPE](oftype-entity-sql.md)|Zwraca kolekcję obiektów z wyrażenia zapytania, które jest określonego typu.|
|[Konstruktor typu nazwanego](named-type-constructor-entity-sql.md)|Służy do tworzenia wystąpień typów jednostek lub typów złożonych.|
|[MULTISET](multiset-entity-sql.md)|Tworzy wystąpienie zestawu wielokrotnego z listy wartości.|
|[ROW](row-entity-sql.md)|Konstruuje anonimowe, strukturalnie wpisane rekordy z co najmniej jednej wartości.|
|[TREAT](treat-entity-sql.md)|Traktuje obiekt określonego typu podstawowego jako obiekt określonego typu pochodnego.|

## <a name="other-operators"></a>Inne operatory

W poniższej tabeli wymieniono inne operatory Entity SQL:

|Operator|Zastosowanie|
|--------------|---------|
|[+ (Łączenie ciągów)](string-concatenation-entity-sql.md)|Służy do łączenia ciągów w Entity SQL.|
|[. (Dostęp do elementów członkowskich)](member-access-entity-sql.md)|Służy do uzyskiwania dostępu do wartości właściwości lub pola wystąpienia strukturalnego modelu koncepcyjnego.|
|[-- (Komentarz)](comment-entity-sql.md)|Uwzględnij Komentarze Entity SQL.|
|[FUNKCYJN](function-entity-sql.md)|Definiuje wbudowaną funkcję, która może być wykonywana w kwerendzie Entity SQL.|

## <a name="see-also"></a>Zobacz także

- [Jednostki języka SQL](entity-sql-language.md)
