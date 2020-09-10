---
title: 'Atrybuty zastrzeżone języka C#: statycznej analizy dopuszczające wartość null'
ms.date: 04/14/2020
description: Te atrybuty są interpretowane przez kompilator w celu zapewnienia lepszej statycznej analizy dla typów odwołań dopuszczających wartości null i niedopuszczających wartości null.
ms.openlocfilehash: d2405162ece3df209111de65fdef54f70cc86d45
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656314"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a>Atrybuty zastrzeżone przyczyniają się do analizy statycznej stanu kompilatora o wartości null

W kontekście dopuszczającym wartość null kompilator wykonuje statyczną analizę kodu, aby określić stan null dla wszystkich zmiennych typu odwołania:

- *nie null*: analiza statyczna ustaliła, że zmienna jest przypisana do wartości innej niż null.
- może *mieć wartość null*: analiza statyczna nie może określić, że zmienna ma przypisaną wartość różną od null.

Można zastosować wiele atrybutów, które dostarczają informacje dla kompilatora o semantyki interfejsów API. Te informacje ułatwiają kompilatorowi wykonywanie analizy statycznej i określanie, kiedy zmienna nie ma wartości null. W tym artykule przedstawiono krótki opis każdego z tych atrybutów oraz sposób ich używania. We wszystkich przykładach przyjęto język C# 8,0 lub nowszy, a kod jest w kontekście dopuszczającym wartość null.

Zacznijmy od znanego przykładu. Wyobraź sobie, że biblioteka zawiera następujący interfejs API do pobrania ciągu zasobu:

```csharp
bool TryGetMessage(string key, out string message)
```

Poprzedni przykład jest zgodny ze znajomym `Try*` wzorcem w programie .NET. Istnieją dwa argumenty odwołania dla tego interfejsu API: `key` i `message` parametru. Ten interfejs API ma następujące reguły dotyczące wartości null tych argumentów:

- Obiekty wywołujące nie powinny być przekazywane `null` jako argument dla elementu `key` .
- Obiekty wywołujące mogą przekazywać zmienną, której wartość jest `null` argumentem dla `message` .
- Jeśli `TryGetMessage` Metoda zwraca `true` , wartość `message` nie jest równa null. Jeśli wartość zwracana jest `false,` wartością parametru `message` (i jego stan zerowy) ma wartość null.

Reguła dla `key` może być wyrażona przez typ zmiennej: `key` powinien być typem referencyjnym, który nie dopuszcza wartości null. `message`Parametr jest bardziej skomplikowany. Umożliwia `null` jako argument, ale gwarantuje, że w przypadku powodzenia ten `out` argument nie ma wartości null. W tych scenariuszach potrzebujesz bogatszego słownictwa do opisywania oczekiwań.

Dodano kilka atrybutów w celu wyrażenia dodatkowych informacji o stanie null zmiennych. Wszystkie kod, który zapisano przed C# 8 wprowadziły typy odwołań dopuszczających wartości null, miał *wartość null Oblivious*. Oznacza to, że jakakolwiek zmienna typu referencyjnego może mieć wartość null, ale sprawdzanie wartości null nie jest wymagane. Gdy kod *dopuszcza wartość null*, te reguły zostaną zmienione. Typy odwołań nigdy nie powinny być `null` wartościami, a typy referencyjne dopuszczające wartość null muszą zostać sprawdzone przed `null` usunięciem odwołania.

Reguły interfejsów API mogą być bardziej skomplikowane, jak pokazano w `TryGetValue` scenariuszu interfejsu API. Wiele interfejsów API ma bardziej złożone reguły dla sytuacji, gdy zmienne mogą być lub niemożliwe `null` . W takich przypadkach użyjesz jednego z następujących atrybutów, aby przedstawić te reguły:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Argument wejściowy niedopuszczający wartości null może mieć wartość null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Argument wejściowy dopuszczający wartość null nigdy nie powinien mieć wartości null.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): wartość zwracana niedopuszczający wartości null może być równa null.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): wartość zwracana do wartości null nigdy nie będzie równa null.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Argument wejściowy, który nie dopuszcza wartości null, może mieć wartość null, gdy metoda zwraca określoną `bool` wartość.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Argument wejściowy do wartości null nie będzie miał wartości null, gdy metoda zwróci określoną `bool` wartość.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): wartość zwracana nie ma wartości null, jeśli argument dla określonego parametru nie ma wartości null.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): Metoda nigdy nie zwraca. Innymi słowy, zawsze zgłasza wyjątek.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): Ta metoda nigdy nie zwraca, czy skojarzony `bool` parametr ma określoną wartość.

Powyższe opisy stanowią krótkie informacje o tym, co robi każdy atrybut. W poniższych sekcjach opisano zachowanie i ich znaczenie.

Dodanie tych atrybutów zapewnia kompilatorowi więcej informacji na temat reguł dla interfejsu API. Gdy Wywoływanie kodu jest kompilowane w kontekście włączonego wartości null, kompilator ostrzega wywoływania, gdy narusza te reguły. Te atrybuty nie umożliwiają wykonywania dodatkowych operacji sprawdzania w implementacji.

## <a name="specify-preconditions-allownull-and-disallownull"></a>Określ warunki wstępne: `AllowNull` i `DisallowNull`

Rozważ użycie właściwości do odczytu/zapisu, która nigdy nie zwraca, `null` ponieważ ma ona rozsądną wartość domyślną. Obiekty wywołujące przejdą `null` do zestawu metod dostępu podczas ustawiania tej wartości domyślnej. Rozważmy na przykład system obsługi komunikatów, który prosi o podanie nazwy ekranu w pokoju rozmowy. Jeśli żaden nie jest podany, system generuje nazwę losową:

```csharp
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName;
```

Gdy kompilujesz poprzedni kod w kontekście dopuszczającym wartość null, wszystko jest bardzo precyzyjne. Po włączeniu typów referencyjnych dopuszczających wartość null, `ScreenName` Właściwość ta będzie odwołaniem niedopuszczanym do wartości null. Jest to poprawne dla `get` metody dostępu: nigdy nie zwraca `null` . Obiekty wywołujące nie muszą sprawdzać zwracanej właściwości dla elementu `null` . Ale teraz ustawienie właściwości w celu `null` wygenerowania ostrzeżenia. Aby kontynuować obsługę tego typu kodu, Dodaj <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> atrybut do właściwości, jak pokazano w poniższym kodzie:

```csharp
[AllowNull]
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName = GenerateRandomScreenName();
```

Może być konieczne dodanie dyrektywy do programu `using` <xref:System.Diagnostics.CodeAnalysis> w celu użycia tego i innych atrybutów omówionych w tym artykule. Ten atrybut jest stosowany do właściwości, a nie do `set` metody dostępu. `AllowNull`Atrybut określa *warunki wstępne*i ma zastosowanie tylko do danych wejściowych. `get`Metoda dostępu ma wartość zwracaną, ale nie ma argumentów wejściowych. W związku z tym `AllowNull` atrybut ma zastosowanie tylko do `set` metody dostępu.

W poprzednim przykładzie pokazano, co należy szukać podczas dodawania `AllowNull` atrybutu do argumentu:

1. Ogólną umową dla tej zmiennej jest to, że nie powinna ona być `null` , więc potrzebujesz typu referencyjnego, który nie dopuszcza wartości null.
1. Istnieją scenariusze dla zmiennej wejściowej `null` , chociaż nie są one najczęstszym użyciem.

Najczęściej ten atrybut jest potrzebny dla właściwości,, `in` `out` i `ref` argumentów. Ten `AllowNull` atrybut jest najlepszym wyborem, gdy zmienna jest zwykle inna niż null, ale musisz zezwolić `null` jako warunek wstępny.

Przeciwieństwo do użycia `DisallowNull` : ten atrybut służy do określenia, że zmienna wejściowa typu referencyjnego nullable nie powinna być `null` . Rozważmy Właściwość `null` , gdzie jest wartością domyślną, ale klienci mogą ustawić ją tylko na wartość różną od null. Spójrzmy na poniższy kod:

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

Poprzedni kod jest najlepszym sposobem, aby wyrazić projekt `ReviewComment` , który może być `null` , ale nie może być ustawiony na `null` . Gdy ten kod dopuszcza wartość null, można jawnie wyrazić takie koncepcje dla wywołujących przy użyciu <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType> :

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

W kontekście dopuszczającym wartość null `ReviewComment` `get` metoda dostępu może zwrócić wartość domyślną `null` . Kompilator ostrzega o tym, że musi zostać sprawdzony przed dostępem. Ponadto ostrzega wywołujących, że mimo że może się to zdarzyć `null` , obiekty wywołujące nie powinny jawnie ustawiać `null` . `DisallowNull`Atrybut określa również *warunek wstępny*, nie ma wpływu na `get` metodę dostępu. Ten atrybut jest używany `DisallowNull` podczas przestrzegania następujących cech:

1. Zmienna może być `null` w scenariuszach podstawowych, często podczas pierwszego wystąpienia.
1. Zmienna nie powinna być jawnie ustawiona na wartość `null` .

Te sytuacje często występują w kodzie, który pierwotnie miał *wartość null Oblivious*. Może być to, że właściwości obiektu są ustawiane w dwóch odrębnych operacjach inicjalizacji. Niektóre właściwości mogą być ustawione tylko po zakończeniu pewnej asynchronicznej pracy.

`AllowNull`Atrybuty i `DisallowNull` umożliwiają określenie, że warunki wstępne dla zmiennych mogą nie pasować do adnotacji dopuszczających wartości null w tych zmiennych. Zapewniają one więcej szczegółowych informacji o cechach interfejsu API. Te dodatkowe informacje ułatwiają wywoływanie interfejsu API. Należy pamiętać o określeniu warunków wstępnych przy użyciu następujących atrybutów:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Argument wejściowy niedopuszczający wartości null może mieć wartość null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Argument wejściowy dopuszczający wartość null nigdy nie powinien mieć wartości null.

## <a name="specify-post-conditions-maybenull-and-notnull"></a>Określ warunki końcowe: `MaybeNull` i `NotNull`

Załóżmy, że masz metodę o następującej sygnaturze:

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

Prawdopodobnie Zapisano metodę podobną do tej, aby zwracała się `null` , gdy nie znaleziono nazwy. `null`Jasno wskazuje, że rekord nie został znaleziony. W tym przykładzie można zmienić typ zwracany z `Customer` na `Customer?` . Deklarowanie wartości zwracanej jako typ referencyjny dopuszczający wartość null Określa zamiar tego interfejsu API jasno.

Z przyczyn objętych [definicjami ogólnymi i wartością null](../../nullable-migration-strategies.md#generic-definitions-and-nullability) ta technika nie działa z metodami ogólnymi. Może istnieć Metoda ogólna, która następuje po podobnym wzorcu:

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

Nie można określić, że wartość zwracana to `T?` . Metoda zwraca `null` , gdy nie znaleziono szukanego elementu. Ponieważ nie można zadeklarować `T?` zwracanego typu, należy dodać `MaybeNull` adnotację do zwracanej metody:

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

Poprzedni kod informuje wywołujących, że kontrakt implikuje typ niedopuszczający wartości null, ale zwracana wartość *może* być równa null.  Użyj `MaybeNull` atrybutu, gdy interfejs API powinien być typu niedopuszczający wartości null, zazwyczaj parametru typu ogólnego, ale mogą występować wystąpienia, w których `null` zostałyby zwrócone.

Można również określić, że wartość zwracana lub `out` argument or nie mają wartości null, mimo że `ref` Typ jest typem referencyjnym dopuszczającym wartość null. Rozważmy metodę, która zapewnia, że tablica jest wystarczająco duża, aby pomieścić liczbę elementów. Jeśli argument wejściowy nie ma pojemności, procedura przydzieli nową tablicę i skopiuje do niej wszystkie istniejące elementy. Jeśli argumentem wejściowym jest `null` , procedura przydzieli nowy magazyn. W przypadku wystarczającej pojemności procedura nie wykonuje żadnych czynności:

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

Tę procedurę można wywołać w następujący sposób:

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

Po włączeniu typów odwołań o wartości null, należy upewnić się, że poprzedni kod kompiluje bez ostrzeżeń. Gdy metoda zwraca, `storage` argument ma gwarantowaną wartość nie równą null. Jednak jest to możliwe do wywołania `EnsureCapacity` z odwołaniem o wartości null. Można wprowadzić `storage` typ referencyjny dopuszczający wartość null i dodać `NotNull` warunek post do deklaracji parametru:

```csharp
public void EnsureCapacity<T>([NotNull] ref T[]? storage, int size)
```

Poprzedni kod wyraża istniejący kontrakt jasno: obiekty wywołujące mogą przekazać zmienną o `null` wartości, ale wartość zwracana jest gwarantowana, aby nigdy nie była równa null. Ten `NotNull` atrybut jest najbardziej przydatny `ref` dla `out` argumentów i `null` , gdzie mogą być przekazane jako argument, ale ten argument jest gwarantowany, że nie ma wartości null, gdy metoda zwraca.

Należy określić warunki końcowe bezwarunkowe, korzystając z następujących atrybutów:

- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): wartość zwracana niedopuszczający wartości null może być równa null.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): wartość zwracana do wartości null nigdy nie będzie równa null.

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a>Określ warunkowe warunki końcowe: `NotNullWhen` , `MaybeNullWhen` i `NotNullIfNotNull`

Najkorzystniej znasz `string` metodę <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> . Ta metoda zwraca `true` , gdy argument ma wartość null lub jest pustym ciągiem. Jest to forma sprawdzania wartości null: obiekty wywołujące nie muszą mieć wartości null — Sprawdź argument, jeśli metoda zwraca wartość `false` . Aby określić metodę, taką jak ta, która dopuszcza wartość null, należy ustawić argument na typ referencyjny dopuszczający wartość null i dodać `NotNullWhen` atrybut:

```csharp
bool IsNullOrEmpty([NotNullWhen(false)] string? value);
```

Informuje kompilator, że żaden kod, w którym nie jest wymagana wartość zwracana, `false` nie może mieć wartości null. Dodanie atrybutu informuje analizę statyczną kompilatora, która `IsNullOrEmpty` wykonuje niezbędne sprawdzanie wartości null: gdy zwraca `false` , argument wejściowy nie jest `null` .

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

<xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>Metoda zostanie umieszczona w adnotacji, jak pokazano powyżej dla programu .NET Core 3,0. W bazie kodu mogą znajdować się podobne metody, które sprawdzają stan obiektów dla wartości null. Kompilator nie rozpoznaje niestandardowych metod sprawdzania wartości null i należy samodzielnie dodać adnotacje. Po dodaniu atrybutu analiza statyczna kompilatora wie, kiedy sprawdzona zmienna ma wartość null.

Innym zastosowaniem dla tych atrybutów jest `Try*` wzorzec. Warunki końcowe dla `ref` i `out` zmienne są przekazywane przez wartość zwracaną. Rozważmy tę metodę pokazaną wcześniej:

```csharp
bool TryGetMessage(string key, out string message)
```

Poprzednia metoda jest zgodna z typowym środowiskiem .NET idiom: wartość zwracana wskazuje `message` , czy została ustawiona na znalezioną wartość, czy nie zostanie znaleziony komunikat do wartości domyślnej. Jeśli metoda zwraca `true` , wartość `message` nie jest równa null; w przeciwnym razie metoda jest ustawiana `message` na wartość null.

Można komunikować się z idiom przy użyciu `NotNullWhen` atrybutu. W przypadku aktualizowania sygnatury dla typów referencyjnych dopuszczających wartość null wprowadź `message` `string?` i Dodaj atrybut:

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

W poprzednim przykładzie wartość `message` jest znana od null, gdy `TryGetMessage` zwraca `true` . Należy dodać adnotacje do podobnych metod w bazie kodu w taki sam sposób: argumenty mogą być `null` i nie mieć wartości null, gdy metoda zwraca `true` .

Istnieje również jeden atrybut końcowy. Czasami stan null wartości zwracanej zależy od stanu zerowego co najmniej jednego argumentu wejściowego. Metody te zwracają wartość różną od null, gdy nie ma określonych argumentów wejściowych `null` . Aby poprawnie dodać adnotację do tych metod, należy użyć `NotNullIfNotNull` atrybutu. Weź pod uwagę następującą metodę:

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

Jeśli `url` argument nie ma wartości null, dane wyjściowe nie są `null` . Po włączeniu odwołań do wartości null ten podpis działa prawidłowo, pod warunkiem, że interfejs API nigdy nie akceptuje danych wejściowych o wartości null. Jeśli jednak dane wejściowe mogą mieć wartość null, wówczas wartość zwracana może być również wartością null. W związku z tym można zmienić sygnaturę na następujący kod:

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

To również działa, ale często zmusza wywołujących do wdrożenia dodatkowych `null` kontroli. Kontrakt jest, że wartość zwracana będzie tylko wtedy, `null` gdy argument wejściowy `url` to `null` . Aby można było wyrazić ten kontrakt, należy dodać adnotację do tej metody, jak pokazano w poniższym kodzie:

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

Zwracana wartość i argument mają adnotację ze `?` wskazaniem, że może to być `null` . Ten atrybut dokładniej objaśnia, że wartość zwracana nie będzie zerowa, gdy `url` argument nie jest `null` .

Należy określić warunkowe warunki końcowe przy użyciu następujących atrybutów:

- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Argument wejściowy, który nie dopuszcza wartości null, może mieć wartość null, gdy metoda zwraca określoną `bool` wartość.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Argument wejściowy do wartości null nie będzie miał wartości null, gdy metoda zwróci określoną `bool` wartość.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): wartość zwracana nie ma wartości null, jeśli argument wejściowy dla określonego parametru nie ma wartości null.

## <a name="verify-unreachable-code"></a>Weryfikuj nieosiągalny kod

Niektóre metody, zazwyczaj pomocniki wyjątków lub inne metody narzędzi, zawsze opuszczają się, zwracając wyjątek. Lub pomocnik może zgłosić wyjątek na podstawie wartości argumentu logicznego.

W pierwszym przypadku można dodać `DoesNotReturn` atrybut do deklaracji metody. Kompilator pozwala na trzy sposoby. Najpierw kompilator generuje ostrzeżenie, jeśli istnieje ścieżka, w której metoda może wyjść bez zgłaszania wyjątku. Po drugie, kompilator oznacza dowolny kod po wywołaniu tej metody jako *nieosiągalny*do czasu `catch` napotkania odpowiedniej klauzuli. Trzeci kod nieosiągalny nie wpłynie na żadne Stany null. Rozważmy tę metodę:

```csharp
[DoesNotReturn]
private void FailFast()
{
    throw new InvalidOperationException();
}

public void SetState(object containedField)
{
    if (!isInitialized)
    {
        FailFast();
    }

    // unreachable code:
    _field = containedField;
}
```

W drugim przypadku należy dodać `DoesNotReturnIf` atrybut do parametru Boolean metody. Poprzedni przykład można zmodyfikować w następujący sposób:

```csharp
private void FailFast([DoesNotReturnIf(false)] bool isValid)
{
    if (!isValid)
    {
        throw new InvalidOperationException();
    }
}

public void SetState(object containedField)
{
    FailFast(isInitialized);

    // unreachable code when "isInitialized" is false:
    _field = containedField;
}
```

## <a name="summary"></a>Podsumowanie

[!INCLUDE [C# version alert](../../includes/csharp-version-alert.md)]

Dodanie typów referencyjnych dopuszczających wartość null zapewnia wstępne słownictwo do opisywania oczekiwań interfejsów API dla zmiennych, które mogą być `null` . Dodatkowe atrybuty zapewniają bogatszy słownictwo do opisania stanu wartości null zmiennych jako warunków wstępnych i warunki końcowe. Te atrybuty bardziej wyraźnie opisują oczekiwania i zapewniają lepszy komfort używania interfejsów API przez deweloperów.

Podczas aktualizowania bibliotek dla kontekstu dopuszczającego wartość null należy dodać te atrybuty, aby ułatwić użytkownikom interfejsów API poprawne użycie. Te atrybuty pomagają w pełni opisać stan null argumentów wejściowych i zwracanych wartości:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Argument wejściowy niedopuszczający wartości null może mieć wartość null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Argument wejściowy dopuszczający wartość null nigdy nie powinien mieć wartości null.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): wartość zwracana niedopuszczający wartości null może być równa null.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): wartość zwracana do wartości null nigdy nie będzie równa null.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Argument wejściowy, który nie dopuszcza wartości null, może mieć wartość null, gdy metoda zwraca określoną `bool` wartość.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Argument wejściowy do wartości null nie będzie miał wartości null, gdy metoda zwróci określoną `bool` wartość.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): wartość zwracana nie ma wartości null, jeśli argument wejściowy dla określonego parametru nie ma wartości null.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): Metoda nigdy nie zwraca. Innymi słowy, zawsze zgłasza wyjątek.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): Ta metoda nigdy nie zwraca, czy skojarzony `bool` parametr ma określoną wartość.
