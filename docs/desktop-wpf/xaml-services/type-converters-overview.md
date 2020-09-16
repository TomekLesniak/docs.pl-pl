---
title: Typy konwerterów dla XAML — Omówienie
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converters
- XAML [XAML Services], TypeConverter
- type conversion for XAML [XAML Services]
ms.assetid: 51a65860-efcb-4fe0-95a0-1c679cde66b7
ms.openlocfilehash: 6e78210178fda65bb3baad0d24eb3a20cd6f2a3e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540116"
---
# <a name="overview-of-type-converters-for-xaml"></a>Omówienie konwerterów typów dla języka XAML

Typy konwerterów dostarczają logiki dla składnika zapisywania obiektów, który konwertuje z ciągu znaków XAML na określone obiekty w grafie obiektów. W usługach programu .NET XAML konwerter typu musi być klasą, która pochodzi od <xref:System.ComponentModel.TypeConverter> . Niektóre konwertery obsługują również ścieżkę zapisu XAML i mogą służyć do serializacji obiektu w postaci ciągu w znaczniku serializacji. W tym temacie opisano, jak i kiedy są wywoływane konwertery typów w języku XAML, i przedstawiono porady dotyczące implementacji metod przesłania <xref:System.ComponentModel.TypeConverter> .

## <a name="type-conversion-concepts"></a>Pojęcia dotyczące konwersji typów

W poniższych sekcjach objaśniono podstawowe pojęcia związane z używaniem ciągów przez XAML i sposobu, w jaki moduły zapisujące obiektów w usługach .NET XAML używają konwerterów typów do przetwarzania niektórych wartości ciągów, które są napotkane w źródle XAML.

### <a name="xaml-and-string-values"></a>Wartości XAML i String

Po ustawieniu wartości atrybutu w pliku XAML, początkowy typ tej wartości jest ciągiem w ogólnym sensie, a wartość atrybutu String w sensie XML. Nawet inne elementy podstawowe, takie jak, <xref:System.Double> są początkowo ciągami do procesora XAML.

W większości przypadków procesor XAML wymaga dwóch informacji do przetworzenia wartości atrybutu. Pierwsza część informacji jest typem wartości właściwości, która jest ustawiana. Dowolny ciąg, który definiuje wartość atrybutu i który jest przetwarzany w języku XAML, musi ostatecznie być konwertowany lub rozpoznany jako wartość tego typu. Jeśli wartość jest typem podstawowym, który jest zrozumiały dla analizatora XAML (na przykład wartość liczbowa), podejmowana jest bezpośrednia Konwersja ciągu. Jeśli wartość atrybutu odwołuje się do wyliczenia, dostarczony ciąg jest sprawdzany pod kątem zgodności nazw z nazwaną stałą w tym wyliczeniu. Jeśli wartość nie jest rozpoznawana jako nazwa pierwotna lub stała z wyliczenia, odpowiedni typ musi być w stanie podać wartość lub odwołanie na podstawie przekonwertowanego ciągu.

> [!NOTE]
> Dyrektywy języka XAML nie używają konwerterów typów.

### <a name="type-converters-and-markup-extensions"></a>Konwertery typów i rozszerzenia znaczników

Użycie rozszerzeń znaczników musi być obsługiwane przez procesor XAML przed sprawdzeniem typu właściwości i innych zagadnień. Na przykład, jeśli właściwość ustawiana jako atrybut zwykle ma konwersję typu, ale w konkretnym przypadku jest ustawiana za pomocą rozszerzenia znaczników, wówczas zachowanie rozszerzenia znaczników jest najpierw przetwarzane. Jedną z typowych sytuacji, gdy wymagane jest rozszerzenie znaczników, jest odwołanie do obiektu, który już istnieje. W tym scenariuszu konwerter typu bezstanowego może generować tylko nowe wystąpienie, które może nie być pożądane. Aby uzyskać więcej informacji na temat rozszerzeń znaczników, zobacz [znaczniki rozszerzeń dla języka XAML — Omówienie](markup-extensions-overview.md).

### <a name="native-type-converters"></a>Konwertery typów natywnych

We wdrożeniach usług Windows Presentation Foundation (WPF) i .NET XAML istnieją pewne typy CLR, które mają obsługę konwersji typu macierzystego. Jednak te typy CLR nie są zwyczajowo uważane za elementy pierwotne. Przykładem takiego typu jest <xref:System.DateTime> . Jednym z powodów tego jest to, jak działa architektura .NET Framework: typ <xref:System.DateTime> jest zdefiniowany w bibliotece Mscorlib, a najbardziej podstawowa Biblioteka w programie .NET. <xref:System.DateTime> nie jest dozwolone, aby mieć atrybut pochodzący z innego zestawu, który wprowadza zależność ( <xref:System.ComponentModel.TypeConverterAttribute> pochodzi z systemu). W związku z tym nie można obsługiwać standardowego mechanizmu wykrywania konwertera typów przez przypisanie. Zamiast tego Analizator XAML ma listę typów, które wymagają przetwarzania natywnego, i przetwarza te typy podobnie jak w przypadku przetwarzania prawdziwych elementów podstawowych. W przypadku <xref:System.DateTime> , przetwarzanie obejmuje wywołanie <xref:System.DateTime.Parse%2A> .

## <a name="implementing-a-type-converter"></a>Implementowanie konwertera typów

W poniższych sekcjach omówiono interfejs API <xref:System.ComponentModel.TypeConverter> klasy.

### <a name="typeconverter"></a>TypeConverter

W obszarze usługi platformy .NET XAML wszystkie konwertery typów, które są używane na potrzeby języka XAML, są klasami pochodnymi od klasy bazowej <xref:System.ComponentModel.TypeConverter> . <xref:System.ComponentModel.TypeConverter>Klasa istniała w wersjach .NET Framework przed istnieniem XAML; jednym z oryginalnych <xref:System.ComponentModel.TypeConverter> scenariuszy było zapewnienie konwersji ciągów dla edytorów właściwości w projektantach wizualizacji.

Dla języka XAML rola <xref:System.ComponentModel.TypeConverter> jest rozwinięta. W celach XAML <xref:System.ComponentModel.TypeConverter> jest klasą bazową w celu zapewnienia obsługi określonych ciągów i konwersji ciągów. Parametry from umożliwiają analizowanie wartości atrybutu String z XAML. Ciąg może umożliwiać przetwarzanie wartości właściwości określonego obiektu z powrotem do atrybutu w kodzie XAML dla serializacji.

<xref:System.ComponentModel.TypeConverter> definiuje cztery składowe, które są istotne dla konwersji do-String i z-String dla celów przetwarzania kodu XAML:

- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>

Z tych elementów członkowskich najważniejsze metody to <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> , które konwertuje ciąg wejściowy na wymagany typ obiektu. <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>Metodę można zaimplementować w celu przekonwertowania szerszego zakresu typów na zamierzony typ docelowy konwertera. W związku z tym może obsługiwać cele wykraczające poza kod XAML, takie jak obsługa konwersji w czasie wykonywania. Jednak w przypadku użycia XAML tylko ścieżka kodu, która może przetwarzać <xref:System.String> dane wejściowe, jest ważna.

Druga z najważniejszych metod to <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> . Jeśli aplikacja jest konwertowana na reprezentację znaczników (na przykład jeśli jest zapisywana w języku XAML jako plik), jest uwzględniany <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> w większym scenariuszu składnika zapisywania tekstu XAML, aby utworzyć reprezentację znaczników. W takim przypadku ważną ścieżką kodu dla języka XAML jest, gdy wywołujący przekazuje `destinationType` element <xref:System.String> .

<xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> i <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> obsługują metody, które są używane, gdy usługa wysyła zapytanie o możliwości <xref:System.ComponentModel.TypeConverter> implementacji. Należy zaimplementować te metody, aby zwrócić się do `true` przypadków specyficznych dla typów, które są równoważnymi metodami konwersji konwertera. Na potrzeby języka XAML zazwyczaj oznacza to <xref:System.String> Typ.

### <a name="culture-information-and-type-converters-for-xaml"></a>Informacje o kulturze i konwertery typów dla języka XAML

Każda <xref:System.ComponentModel.TypeConverter> implementacja może jednoznacznie interpretować, co jest prawidłowym ciągiem dla konwersji, i może również używać lub ignorować opis typu, który jest przesyłany jako parametry. Ważnym zagadnieniem dotyczącym konwersji kultury i języka XAML są następujące: Chociaż użycie lokalizowalnych ciągów jako wartości atrybutów jest obsługiwane przez język XAML, nie można używać tych lokalizowalnych ciągów jako danych wejściowych konwertera typów z określonymi wymaganiami kultury. To ograniczenie wynika z faktu, że konwertery typów dla wartości atrybutów XAML wymagają stałego języka XAML, który używa `en-US` kultury. Aby uzyskać więcej informacji na temat przyczyn związanych z projektowaniem tego ograniczenia, zobacz Specyfikacja języka XAML ([ \[ MS \] -XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10))) lub [Omówienie globalizacji i lokalizacji platformy WPF](/dotnet/desktop/wpf/advanced/wpf-globalization-and-localization-overview).

Przykładowo, gdy kultura może być problemem, niektóre kultury używają przecinka zamiast kropki jako ogranicznika przecinka dziesiętnego dla liczb w postaci ciągów. To użycie koliduje z zachowaniem wielu istniejących konwerterów typów, które ma używać przecinka jako ogranicznika. Przekazywanie kultury przez `xml:lang` w otaczającym XAML nie rozwiązuje problemu.

### <a name="implementing-convertfrom"></a>Implementowanie ConvertFrom

Aby można było używać ich jako <xref:System.ComponentModel.TypeConverter> implementacji, która obsługuje XAML, <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> Metoda dla tego konwertera musi akceptować ciąg jako `value` parametr. Jeśli ciąg jest w prawidłowym formacie i może być konwertowany przez <xref:System.ComponentModel.TypeConverter> implementację, zwracany obiekt musi obsługiwać rzutowanie do typu, który jest oczekiwany przez właściwość. W przeciwnym razie <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> implementacja musi zwrócić `null` .

Każda <xref:System.ComponentModel.TypeConverter> implementacja może jednoznacznie interpretować, co stanowi prawidłowy ciąg dla konwersji, i może również używać lub ignorować opis typu lub kontekstów kultury, które są przesyłane jako parametry. Jednak przetwarzanie w języku XAML WPF może nie przekazywać wartości do kontekstu opisu typu we wszystkich przypadkach, a także może nie przekazywać kultury opartej na `xml:lang` .

> [!NOTE]
> Nie używaj nawiasów klamrowych ( {} ), a w odniesieniu do nawiasu otwierającego ({) jako elementu w formacie ciągu. Te znaki są zarezerwowane jako wejście i wyjście dla sekwencji rozszerzenia znaczników.

Jest to konieczne, aby zgłosić wyjątek, gdy konwerter typu musi mieć dostęp do usługi XAML z składnika zapisywania obiektów programu .NET XAML, ale <xref:System.IServiceProvider.GetService%2A> wywołanie wykonane względem kontekstu nie zwraca tej usługi.

### <a name="implementing-convertto"></a>Implementowanie ConvertTo

<xref:System.ComponentModel.TypeConverter.ConvertTo%2A> jest potencjalnie używany do obsługi serializacji. Obsługa serializacji za pomocą <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> dla typu niestandardowego i jego konwertera typów nie jest wymaganiem bezwzględnym. Jednak jeśli wdrażasz kontrolkę lub korzystasz z serializacji jako części funkcji lub projektu klasy, należy zaimplementować <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> .

Aby można było używać ich jako <xref:System.ComponentModel.TypeConverter> implementacji, która obsługuje XAML, <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> Metoda dla tego konwertera musi akceptować wystąpienie typu (lub wartość), które jest obsługiwane jako `value` parametr. Gdy `destinationType` parametr jest typu <xref:System.String> , zwracany obiekt musi być w stanie rzutować jako <xref:System.String> . Zwrócony ciąg musi reprezentować wartość serializowaną `value` . Najlepiej, gdy wybrany format serializacji powinien być w stanie generować tę samą wartość, co w przypadku, gdy ten ciąg został przekazano do <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> implementacji tego samego konwertera, bez znacznej utraty informacji.

Jeśli wartość nie może być serializowana lub konwerter nie obsługuje serializacji, <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> implementacja musi zwracać `null` i może zgłosić wyjątek. Jednakże w przypadku zgłaszania wyjątków należy zgłosić niezdolność do korzystania z tej konwersji w ramach <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> implementacji, tak aby najlepszym rozwiązaniem w zakresie sprawdzania z <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> pierwszym sposobem na uniknięcie wyjątków jest obsługiwane.

Jeśli `destinationType` parametr nie jest typu, możesz <xref:System.String> wybrać własny sposób obsługi konwertera. Zwykle przywracana jest podstawowa obsługa implementacji, która w bazie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> zgłasza konkretny wyjątek.

Jest to konieczne, aby zgłosić wyjątek, gdy konwerter typu musi mieć dostęp do usługi XAML z składnika zapisywania obiektów programu .NET XAML, ale <xref:System.IServiceProvider.GetService%2A> wywołanie wykonane względem kontekstu nie zwraca tej usługi.

### <a name="implementing-canconvertfrom"></a>Implementowanie CanConvertFrom

Twoja <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> implementacja powinna zwracać `true` dla `sourceType` typu <xref:System.String> i w przeciwnym razie przełożyć na implementację podstawową. Nie zgłaszaj wyjątków z programu <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> .

### <a name="implementing-canconvertto"></a>Implementowanie CanConvertTo

<xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>Implementacja powinna zwracać `true` dla `destinationType` typu <xref:System.String> i w inny sposób odroczyć na implementację podstawową. Nie zgłaszaj wyjątków z programu <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> .

## <a name="applying-the-typeconverterattribute"></a>Stosowanie TypeConverterAttribute

Dla niestandardowego konwertera typów, który ma być używany jako typ działającego konwertera klasy niestandardowej przez usługi .NET XAML, należy zastosować <xref:System.ComponentModel.TypeConverterAttribute> do definicji klasy. <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A>Określony za pomocą atrybutu musi być nazwą typu niestandardowego konwertera typów. W przypadku zastosowania tego atrybutu, gdy procesor XAML obsługuje wartości, w których typ właściwości używa typu klasy niestandardowej, może wprowadzać ciągi i zwracać wystąpienia obiektów.

Można również udostępnić konwerter typów dla poszczególnych właściwości. Zamiast stosować <xref:System.ComponentModel.TypeConverterAttribute> do definicji klasy, zastosuj ją do definicji właściwości (głównej definicji, a nie w `get` / `set` ramach jej implementacji). Typ właściwości musi być zgodny z typem, który jest przetwarzany przez konwerter typów niestandardowych. Po zastosowaniu tego atrybutu, gdy procesor XAML obsługuje wartości tej właściwości, może przetwarzać ciągi wejściowe i zwracać wystąpienia obiektów. Technika konwertera typów dla właściwości jest przydatna, jeśli zdecydujesz się użyć typu właściwości z Microsoft .NET Framework lub z innej biblioteki, w której nie można kontrolować definicji klasy i nie można jej zastosować <xref:System.ComponentModel.TypeConverterAttribute> .

Aby podać zachowanie konwersji typu dla niestandardowego dołączonego elementu członkowskiego, Zastosuj <xref:System.ComponentModel.TypeConverterAttribute> do `Get` metody dostępu wzorca implementacji dla dołączonego elementu członkowskiego.

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Uzyskiwanie dostępu do kontekstu dostawcy usług z implementacji rozszerzenia znaczników

Dostępne usługi są takie same dla dowolnego konwertera wartości. Różnica polega na tym, jak każdy konwerter wartości otrzymuje kontekst usługi. Dostęp do usług i dostępnych usług są udokumentowane w sekcji [konwertery typów i rozszerzenia znaczników dla języka XAML](type-converters-and-markup-extensions.md).

## <a name="type-converters-in-the-xaml-node-stream"></a>Konwertery typów w strumieniu węzła XAML

Jeśli pracujesz ze strumieniem węzła XAML, Akcja lub wynik końcowy konwertera typów nie został jeszcze wykonany. W ścieżce ładowania ciąg atrybutu, który ostatecznie musi być przekonwertowany na typ, w celu załadowania pozostanie jako wartość tekstowa w obrębie początkowego elementu członkowskiego i końcowego elementu członkowskiego. Konwerter typu, który jest ostatecznie potrzebny do wykonania tej operacji, można określić za pomocą <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> właściwości. Jednak uzyskanie prawidłowej wartości polega na wykorzystaniu <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> kontekstu schematu XAML, który może uzyskać dostęp do tych informacji za pośrednictwem bazowego elementu członkowskiego lub typu wartości obiektu używanej przez element członkowski. Wywoływanie zachowania konwersji typu wymaga również kontekstu schematu XAML, ponieważ wymaga on mapowania typów i tworzenia wystąpienia konwertera.

## <a name="see-also"></a>Zobacz także

- <xref:System.ComponentModel.TypeConverterAttribute>
- [Typy konwerterów i rozszerzenia znaczników dla XAML](type-converters-and-markup-extensions.md)
- [Omówienie XAML (WPF)](../fundamentals/xaml.md)
