---
title: Rozszerzenia znaczników dla przeglądu XAML
ms.date: 03/30/2017
helpviewer_keywords:
- markup extensions [XAML Services], custom
- XAML [XAML Services], markup extensions
ms.assetid: 261b2b11-2dc0-462f-8c66-55b8c9c6e436
ms.openlocfilehash: efb41f31a3baa895b5739021af5fa36e32aefeea
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556996"
---
# <a name="overview-of-markup-extensions-for-xaml"></a>Omówienie rozszerzeń znaczników dla języka XAML

Rozszerzenia znaczników są techniką języka XAML do uzyskiwania wartości, która nie jest pierwotna lub określonego typu XAML. W przypadku użycia atrybutów rozszerzenia znaczników używają znanej sekwencji znaków otwierającego nawiasu klamrowego `{` , aby wprowadzić zakres rozszerzenia znacznika i zamykającego nawiasu klamrowego `}` . W przypadku korzystania z usług języka XAML platformy .NET można użyć niektórych wstępnie zdefiniowanych rozszerzeń znaczników języka XAML z zestawu System. XAML. Można również utworzyć podklasę z <xref:System.Windows.Markup.MarkupExtension> klasy, zdefiniowanej w pliku System. XAML i zdefiniować własne rozszerzenia znaczników. Lub można użyć rozszerzeń znaczników zdefiniowanych przez określoną strukturę, jeśli już odwołujesz się do tej struktury.

Po uzyskaniu dostępu do rozszerzenia znaczników moduł zapisujący obiektów XAML może dostarczać usługi do niestandardowej <xref:System.Windows.Markup.MarkupExtension> klasy za pomocą punktu połączenia usługi w <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A?displayProperty=nameWithType> przesłonięciu. Usługi mogą służyć do uzyskania kontekstu dotyczącego użycia, określonych możliwości składnika zapisywania obiektów, kontekstu schematu XAML i tak dalej.

## <a name="xaml-defined-markup-extensions"></a>Rozszerzenia znaczników zdefiniowane w języku XAML

Usługa .NET XAML obsługuje kilka rozszerzeń znaczników do obsługi języka XAML. Te rozszerzenia znaczników odpowiadają części specyfikacji języka XAML jako języka. Są one zazwyczaj identyfikowane przez `x:` prefiks w składni, jak pokazano w typowym użyciu. Implementacje usług .NET XAML dla tych elementów języka XAML wszystkie pochodzą od  <xref:System.Windows.Markup.MarkupExtension> klasy bazowej.

> [!NOTE]
> `x:`Prefiks jest używany dla typowego mapowania przestrzeni nazw XAML w przestrzeni nazw języka XAML, w elemencie głównym produkcji XAML. Na przykład szablon projektu i strony programu Visual Studio dla różnych określonych platform inicjują plik XAML przy użyciu tego `x:` mapowania. Można wybrać inny token prefiksu w ramach własnego mapowania przestrzeni nazw XAML, ale w tej dokumentacji założono domyślne `x:` Mapowanie jako środek identyfikacji tych jednostek, które są zdefiniowaną częścią przestrzeni nazw XAML języka XAML, w przeciwieństwie do domyślnej przestrzeni nazw XAML lub innych dowolnych przestrzeni nazw CLR lub XML.

### <a name="xtype"></a>X:Type —

`x:Type` dostarcza <xref:System.Type> obiekt dla nazwanego typu. Ta funkcja jest używana najczęściej w przypadku mechanizmów odroczenia, które używają podstawowego typu CLR i wyprowadzania typu jako moniker lub identyfikator grupowania. Przykładem są style i szablony WPF oraz ich użycie `TargetType` właściwości. Aby uzyskać więcej informacji, zobacz [X:Type — Markup Extension](xtype-markup-extension.md).

### <a name="xstatic"></a>X:static —

`x:Static` tworzy wartości statyczne z jednostek kodu typu wartości, które nie są bezpośrednio typem wartości właściwości, ale można je ocenić dla tego typu. Jest to przydatne w przypadku określania wartości, które już istnieją jako dobrze znanych stałych w definicji typu. Aby uzyskać więcej informacji, zobacz [X:Static — Markup Extension](xstatic-markup-extension.md).

### <a name="xnull"></a>X:null —

`x:Null` Określa `null` jako wartość dla elementu członkowskiego języka XAML. W zależności od projektu określonych typów lub większych pojęć związanych z platformą, `null` nie zawsze jest wartością domyślną dla właściwości lub wartością implikowaną pustego atrybutu ciągu. Aby uzyskać więcej informacji, zobacz [X:null — Markup Extension](xnull-markup-extension.md).

### <a name="xarray"></a>x:Array

`x:Array` obsługuje tworzenie ogólnych tablic w składni języka XAML w przypadkach, gdy obsługa kolekcji, która jest dostarczana przez elementy podstawowe i modele kontroli, nie jest świadomie używana. Aby uzyskać więcej informacji, zobacz [X:Array Markup Extension](xarray-markup-extension.md). W języku XAML 2009 w szczególnych przypadkach tablice są dostępne jako elementy podstawowe języka, a nie jako rozszerzenia. Aby uzyskać więcej informacji, zobacz [funkcje języka XAML 2009](xaml-2009-language-features.md).

### <a name="xreference"></a>X:Reference —

`x:Reference` jest częścią XAML 2009, rozszerzenie oryginalnego zestawu językowego (2006). `x:Reference` reprezentuje odwołanie do innego istniejącego obiektu w grafie obiektów. Ten obiekt jest identyfikowany przez jego `x:Name` . Aby uzyskać więcej informacji, zobacz [X:Reference — Markup Extension](xreference-markup-extension.md).

### <a name="other-x-constructs"></a>Inne elementy x: Konstrukcje

`x:`Istnieją inne konstrukcje obsługujące funkcje języka XAML, ale nie są one zaimplementowane jako rozszerzenia znaczników. Aby uzyskać więcej informacji, zobacz [przestrzeń nazw XAML (x:) Funkcje językowe](namespace-language-features.md).

## <a name="the-markupextension-base-class"></a>Klasa bazowa MarkupExtension

Aby zdefiniować niestandardowe rozszerzenie znaczników, które może współtworzyć z domyślnymi implementacjami czytników XAML i autorów XAML w pliku System. XAML, należy utworzyć klasę z klasy abstrakcyjnej <xref:System.Windows.Markup.MarkupExtension> . Ta klasa ma jedną metodę do przesłonięcia, czyli <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> . Może być również konieczne zdefiniowanie dodatkowych konstruktorów do obsługi argumentów do użycia rozszerzenia znaczników i dopasowanie właściwości settable.

W <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> programie niestandardowe rozszerzenie znaczników ma dostęp do kontekstu usługi, który zgłasza środowisko, w którym rozszerzenie znacznika jest wywoływane przez procesor XAML. W ścieżce ładowania zwykle jest to <xref:System.Xaml.XamlObjectWriter> . W ścieżce zapisu zwykle jest to <xref:System.Xaml.XamlXmlWriter> . Każdy raport kontekstu usługi jako wewnętrznej klasy kontekstu dostawcy usług XAML implementującej wzorzec dostawcy usług. Aby uzyskać więcej informacji na temat dostępnych usług i ich reprezentowania, zobacz [Typy konwerterów i rozszerzenia znaczników dla języka XAML](type-converters-and-markup-extensions.md).

Klasa rozszerzenia znaczników musi używać publicznego poziomu dostępu; Procesory XAML muszą zawsze być w stanie utworzyć wystąpienie klasy obsługi rozszerzenia znaczników, aby można było korzystać z jej usług.

## <a name="defining-the-support-type-for-a-custom-markup-extension"></a>Definiowanie typu pomocy technicznej dla niestandardowego rozszerzenia znaczników

W przypadku korzystania z usług lub platform programu .NET XAML, które kompilują się w usługach .NET XAML, dostępne są dwie opcje określające nazwę typu obsługi rozszerzenia znaczników. Nazwa typu jest istotna dla sposobu, w jaki autorzy obiektów XAML próbują uzyskać dostęp i wywoływać typ obsługi rozszerzenia znaczników, gdy napotykają użycie rozszerzenia znacznika w języku XAML. Użyj jednej z następujących strategii nazewnictwa:

- Wpisz nazwę typu, aby być dokładnym dopasowaniem do tokenu użycia znaczników języka XAML. Na przykład aby obsłużyć `{Collate ...}` użycie rozszerzenia, nazwij typ pomocy technicznej `Collate` .
- Nazwij nazwę typu jako token ciągu użycia i sufiks `Extension` . Na przykład aby obsłużyć `{Collate ...}` użycie rozszerzenia, nazwij typ pomocy technicznej `CollateExtension` .

Kolejność wyszukiwania ma najpierw wyszukać `Extension` nazwę klasy z sufiksem, a następnie poszukać nazwy klasy bez `Extension` sufiksu.

W perspektywie użycia znaczników, w tym `Extension` sufiks w ramach użycia, jest prawidłowy. Jednakże zachowuje się tak, jakby `Extension` jest rzeczywiście częścią nazwy klasy, a autorzy obiektów XAML nie rozpoznają klasy obsługi rozszerzenia znaczników dla tego użycia, jeśli Klasa pomocy nie ma `Extension` sufiksu.

### <a name="the-parameterless-constructor"></a>Konstruktor bez parametrów

Dla wszystkich typów obsługi rozszerzeń znaczników należy uwidocznić publiczny Konstruktor bez parametrów. Konstruktor bez parametrów jest wymagany w każdym przypadku, gdy moduł zapisujący obiektów XAML tworzy wystąpienie rozszerzenia znaczników z użycia elementu obiektu. Użycie elementu pomocniczego obiektu jest uczciwym oczekiwaniem dla rozszerzenia znacznika, szczególnie w przypadku serializacji. Można jednak zaimplementować rozszerzenie znacznika bez konstruktora publicznego, jeśli zamierzasz obsługiwać użycie atrybutów rozszerzenia znaczników.

Jeśli użycie rozszerzenia znaczników nie ma argumentów, Konstruktor bez parametrów jest wymagany do obsługi użycia.

## <a name="constructor-patterns-and-positional-arguments-for-a-custom-markup-extension"></a>Wzorce konstruktora i argumenty pozycyjne dla niestandardowego rozszerzenia znaczników

W przypadku rozszerzenia znacznika z zamierzonym użyciem argumentów konstruktory publiczne muszą odpowiadać trybów zamierzonego użycia. Innymi słowy, jeśli rozszerzenie znacznika zaprojektowano tak, aby wymagało jednego argumentu pozycyjnego jako prawidłowego użycia, należy obsługiwać Konstruktor publiczny z jednym parametrem wejściowym, który przyjmuje argument pozycyjny.

Załóżmy na przykład, że `Collate` rozszerzenie znaczników jest przeznaczone do obsługi tylko trybu, w którym istnieje jeden argument pozycyjny reprezentujący tryb, określony jako `CollationMode` stała wyliczenia. W takim przypadku powinien być Konstruktor o następującej postaci:

```csharp
public Collate(CollationMode collationMode) {...}
```

Na poziomie podstawowym argumenty przekazane do rozszerzenia znacznika są ciągiem, ponieważ są przekazywane z wartości atrybutów znacznika. Można utworzyć wszystkie ciągi argumentów i pracy z danymi wejściowymi na tym poziomie. Jednak masz dostęp do pewnego przetwarzania, które występuje przed przekazaniem argumentów rozszerzenia znacznika do klasy obsługi.

Przetwarzanie działa koncepcyjnie tak, jakby rozszerzenie znaczników jest obiektem, który ma zostać utworzony, a następnie jego wartości elementów członkowskich są ustawione. Każda określona właściwość, która ma zostać ustawiona, jest szacowana podobnie jak określony element członkowski może być ustawiony dla utworzonego obiektu, gdy kod XAML jest analizowany. Istnieją dwie istotne różnice:

- Jak wspomniano wcześniej, typ obsługi rozszerzenia znaczników nie musi mieć konstruktora bez parametrów, aby można było utworzyć wystąpienie w języku XAML. Konstruowanie obiektu jest odroczone do momentu, gdy jego możliwe argumenty w składni tekstu są określane jako argumenty pozycyjne lub nazwane, a odpowiedni Konstruktor jest wywoływany w tym czasie.
- Użycie rozszerzeń znaczników może być zagnieżdżone. Najbardziej wewnętrzne rozszerzenie znacznika jest oceniane jako pierwsze. W związku z tym można założyć takie użycie i zadeklarować jeden z parametrów konstrukcyjnych jako typ, który wymaga konwertera wartości (takiego jak rozszerzenie znacznika) do utworzenia.

W poprzednim przykładzie pokazano zależność tego przetwarzania. Moduł zapisywania obiektów XAML usług programu .NET XAML przetwarza stałe nazwy wyliczenia na wartości wyliczane na poziomie natywnym.

Przetwarzanie składni tekstu dla parametru pozycyjnego rozszerzenia znaczników może również polegać na konwerterze typów, który jest skojarzony z typem, który znajduje się w argumencie konstrukcji.

Argumenty są nazywane argumentami pozycyjnymi, ponieważ kolejność, w której wykryto tokeny w wykorzystaniu, odpowiada kolejności pozycyjnyej parametru konstruktora, do którego są przypisane. Rozważmy na przykład następujący podpis konstruktora:

```csharp
public Collate(CollationMode collationMode, object collateThis) {...}
```

Procesor XAML oczekuje dwóch argumentów pozycyjnych dla tego rozszerzenia znacznika. Jeśli wystąpiło użycie `{Collate AlphaUp,{x:Reference circularFile}}` , `AlphaUp` token jest wysyłany do pierwszego parametru i oceniany jako `CollationMode` Wyliczenie o nazwie stała. Wynik wewnętrzny `x:Reference` jest wysyłany do drugiego parametru i oceniany jako obiekt.

W języku XAML określone reguły składni i przetwarzania rozszerzenia znaczników przecinek jest ogranicznikiem między argumentami, niezależnie od tego, czy te argumenty są argumentami pozycyjnymi, czy nazwanymi argumentami.

### <a name="duplicate-arity-of-positional-arguments"></a>Zduplikowane argumenty argumentów pozycyjnych

Jeśli moduł zapisujący obiektów XAML napotyka użycie rozszerzenia znacznika z argumentami pozycyjnymi, a istnieje wiele argumentów konstruktora, które pobierają liczbę argumentów (zduplikowane liczby argumentów), które nie muszą być błędem. Zachowanie jest zależne od dostosowywalnego ustawienia kontekstu schematu XAML <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> . Jeśli <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> tak `true` , moduł zapisujący obiektów XAML nie powinien zgłaszać wyjątku tylko z powodu zduplikowanych argumentów. Zachowanie wykraczające poza ten punkt nie jest ściśle zdefiniowane. Podstawowa założenie projektu polega na tym, że kontekst schematu ma informacje o typie dostępne dla określonych parametrów i może próbować jawnie rzutowania, które pasują do zduplikowanych kandydatów, aby zobaczyć, który podpis może być najlepszym dopasowaniem. Wyjątek może być nadal zgłaszany, jeśli żadna sygnatura nie może przekazać testów, które są nakładane przez określony kontekst schematu, który jest uruchomiony w składniku zapisywania obiektów XAML.

Domyślnie program <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> jest `false` w środowisku CLR opartym <xref:System.Xaml.XamlSchemaContext> na platformie .NET XAML. W ten sposób domyślnie <xref:System.Xaml.XamlObjectWriter> zgłasza wyjątki, jeśli napotka użycie rozszerzenia znacznika, w którym występują zduplikowane liczby argumentów w konstruktorach typu kopii zapasowej.

## <a name="named-arguments-for-a-custom-markup-extension"></a>Nazwane argumenty dla niestandardowego rozszerzenia znaczników

Rozszerzenia znaczników określone przez język XAML mogą również użyć formularza nazwanych argumentów do użycia. Na pierwszym poziomie tokenizacji składnia tekstu jest podzielona na argumenty. Obecność znaku równości (=) w dowolnym argumencie identyfikuje argument jako argument nazwany. Taki argument jest również tokenem w parze nazwa/wartość. Nazwa w tym przypadku nazywa publiczną właściwość settable typu obsługi rozszerzenia znaczników. Jeśli zamierzasz obsługiwać użycie argumentów nazwanych, należy podać te właściwości. Właściwości mogą być dziedziczonymi właściwościami, o ile pozostaną one publiczne.

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Uzyskiwanie dostępu do kontekstu dostawcy usług z implementacji rozszerzenia znaczników

Dostępne usługi są takie same dla dowolnego konwertera wartości. Różnica polega na tym, jak każdy konwerter wartości otrzymuje kontekst usługi. Dostęp do usług i dostępnych usług są udokumentowane w sekcji [konwertery typów i rozszerzenia znaczników dla języka XAML](type-converters-and-markup-extensions.md).

## <a name="property-element-usage-of-a-markup-extension"></a>Użycie elementu właściwości w rozszerzeniu znaczników

Scenariusze użycia rozszerzenia znaczników są często zaprojektowane przy użyciu rozszerzenia znaczników w użyciu atrybutu. Jest jednak możliwe również zdefiniowanie klasy zapasowej do obsługi użycia elementów właściwości.

Aby obsługiwać użycie elementu właściwości w rozszerzeniu znacznika, zdefiniuj publiczny Konstruktor bez parametrów. Powinien to być Konstruktor wystąpienia nie jest konstruktorem statycznym. Jest to wymagane, ponieważ procesor XAML musi ogólnie wywołać Konstruktor bez parametrów dla dowolnego elementu obiektu, który przetwarza z znaczników, i obejmuje klasy rozszerzeń znaczników jako elementy obiektu. W przypadku zaawansowanych scenariuszy można definiować inne niż domyślne ścieżki konstrukcyjne dla klas. (Aby uzyskać więcej informacji, zobacz [dyrektywa x:FactoryMethod](xfactorymethod-directive.md)). Nie należy jednak używać tych wzorców do celów rozszerzeń znaczników, ponieważ sprawia to, że odnajdywanie wzorca użycia znacznie trudniejsze, zarówno dla projektantów, jak i dla użytkowników nieprzetworzonych znaczników.

## <a name="attributing-for-a-custom-markup-extension"></a>Przypisywanie do niestandardowego rozszerzenia znaczników

Aby obsługiwać zarówno środowiska projektowe, jak i niektóre scenariusze modułu zapisywania obiektów XAML, należy atrybutować typ obsługi rozszerzenia znaczników z kilkoma atrybutami CLR. Te atrybuty raportują zamierzone użycie rozszerzenia znaczników.

 <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute> raportuje <xref:System.Type> Informacje dla zwracanego typu obiektu <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> . Za pomocą czystego podpisu, <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> zwraca <xref:System.Object> . Jednak różni klienci mogą chcieć dokładniej zwracać informacje o typie. Obejmuje on:

- Projektanci i środowisk IDE, którzy mogą mieć możliwość zapewnienia pomocy technicznej opartej na typie dla użycia rozszerzenia znaczników.
- Zaawansowane implementacje `SetMarkupExtension` programów obsługi w klasach docelowych, które mogą polegać na odbiciu w celu określenia typu zwracanego rozszerzenia znacznika zamiast rozgałęziania określonych znanych <xref:System.Windows.Markup.MarkupExtension> implementacji według nazwy.

## <a name="serialization-of-markup-extension-usages"></a>Serializacja użycia rozszerzenia znaczników

Gdy moduł zapisujący obiektów XAML przetwarza użycie i wywołania rozszerzenia znaczników <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> , kontekst dla niego poprzednio jest używany do rozszerzenia znaczników w strumieniu węzła XAML, ale nie na grafie obiektów. Na grafie obiektów zachowywana jest tylko wartość. Jeśli masz scenariusze projektowania lub inne powody, aby zachować oryginalne użycie rozszerzenia znacznika w serializowanych danych wyjściowych, musisz zaprojektować własną infrastrukturę do śledzenia użycia rozszerzenia znaczników ze strumienia węzłów XAML ścieżki ładowania. Możesz zaimplementować zachowanie, aby ponownie utworzyć elementy strumienia węzła ze ścieżki ładowania i odtworzyć je z powrotem do modułów zapisujących XAML w celu serializacji w ścieżce zapisu, zastępując wartość w odpowiedniej pozycji strumienia węzła.

## <a name="markup-extensions-in-the-xaml-node-stream"></a>Rozszerzenia znaczników w strumieniu węzła XAML

Jeśli pracujesz ze strumieniem węzła XAML na ścieżce ładowania, użycie rozszerzenia znacznika jest wyświetlane w strumieniu węzła jako obiekt.

Jeśli użycie rozszerzenia znacznika używa argumentów pozycyjnych, jest reprezentowane jako obiekt początkowy z wartością inicjalizacji. Jako tekstowa reprezentacja, strumień węzłów jest podobny do następującego:

`StartObject` ( <xref:System.Xaml.XamlType> jest typem definicji rozszerzenia znacznika, a nie jego typem zwracanym)

`StartMember` (nazwa elementu <xref:System.Xaml.XamlMember> is `_InitializationText` )

`Value` (wartość to argumenty pozycyjne jako ciąg obejmujący ograniczników)

`EndMember`

`EndObject`

Użycie rozszerzenia znacznika z nazwanymi argumentami jest reprezentowane jako obiekt z elementami członkowskimi odpowiednich nazw, z których każdy ma ustawioną wartość ciągu tekstowego.

Faktyczne wywoływanie `ProvideValue` implementacji rozszerzenia znacznika wymaga kontekstu schematu XAML, ponieważ wymaga mapowania typu i tworzenia wystąpienia typu rozszerzenia znaczników. Jest to jedną z przyczyn, dlaczego użycie rozszerzeń znaczników jest zachowywane w ten sposób w domyślnych strumieniach węzłów usług XAML platformy .NET — część czytnika ścieżki ładowania często nie ma dostępnego kontekstu schematu XAML.

Jeśli pracujesz ze strumieniem węzła XAML na ścieżce zapisu, ogólnie nie ma nic obecne w reprezentacji grafu obiektów, która może informować o tym, że obiekt do serializacji został pierwotnie dostarczony przez użycie rozszerzenia znacznika i `ProvideValue` wynik. Scenariusze, które muszą utrwalać użycie rozszerzeń znaczników dla operacji przerywania, a także przechwytywania innych zmian na grafie obiektów muszą opracować własne techniki, aby zachować wiedzę na temat użycia rozszerzenia znaczników z oryginalnego danych wejściowych XAML. Na przykład, aby przywrócić użycie rozszerzenia znaczników, może być konieczne współdziałanie ze strumieniem węzła na ścieżce zapisu w celu przywrócenia użycia rozszerzenia znaczników lub wykonania pewnego typu scalania między oryginalnym XAML i okrągłym wyłącznikiem XAML. Niektóre struktury implementujące kod XAML, takie jak WPF, używają typów pośrednich (Expressions) do reprezentowania przypadków, w których użycie rozszerzenia znaczników dostarczyło wartości.

## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.Markup.MarkupExtension>
- [Typy konwerterów i rozszerzenia znaczników dla XAML](type-converters-and-markup-extensions.md)
- [Rozszerzenia znacznikowania i WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
