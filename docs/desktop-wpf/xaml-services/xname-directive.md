---
title: x:Name — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: ddaa35b18d1c632fc49b18dabf0d992dc1c78fcc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549486"
---
# <a name="xname-directive"></a>x:Name — dyrektywa

Jednoznacznie identyfikuje elementy zdefiniowane w języku XAML w namescope języka XAML. Zakresy nazw WPF języka XAML i ich unikalne modele można stosować do obiektów skonkretyzowanych, gdy struktury zapewniają interfejsy API lub implementują zachowania, które uzyskują dostęp do grafu obiektów utworzonych w języku XAML w czasie wykonywania.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`XAMLNameValue`|Ciąg, który jest zgodny z ograniczeniami [gramatyki XamlName](xamlname-grammar.md).|

## <a name="remarks"></a>Uwagi

Po `x:Name` zastosowaniu do modelu programowania zapasowego platformy, nazwa jest równoważna zmiennej, która zawiera odwołanie do obiektu lub wystąpienie zwracane przez konstruktora.

Wartość `x:Name` użycia dyrektywy musi być unikatowa w obrębie namescope języka XAML. Domyślnie, gdy jest używany przez interfejs API usług języka XAML platformy .NET, podstawowy namescope XAML jest zdefiniowany w elemencie głównym XAML pojedynczej produkcji XAML i obejmuje elementy, które są zawarte w tej produkcji XAML. Dodatkowe dyskretne Zakresy nazw WPF języka XAML, które mogą wystąpić w ramach jednej produkcji XAML, mogą być definiowane przez platformy w celu rozwiązania określonych scenariuszy. Na przykład w WPF nowe zakresy nazw WPF języka XAML są definiowane i tworzone przez każdy szablon, który jest również zdefiniowany w tej produkcji XAML. Aby uzyskać więcej informacji na temat języka XAML Zakresy nazw WPF (na przykład w przypadku wielu koncepcji namescope języka XAML), zobacz [WPF XAML Zakresy nazw WPF](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes).

Ogólnie rzecz biorąc `x:Name` nie należy stosować się do sytuacji, w których również są używane `x:Key` . Implementacje języka XAML według określonych istniejących platform wprowadziły koncepcje podstawienia `x:Key` `x:Name` , ale nie jest to zalecane rozwiązanie. Usługi programu .NET XAML nie obsługują takich koncepcji podstawienia podczas obsługi informacji o nazwach/kluczach, takich jak <xref:System.Windows.Markup.INameScope> lub <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> .

Reguły pozwalające na zezwolenie `x:Name` , a także wymuszanie unikatowości nazwy są potencjalnie zdefiniowane przez określone struktury implementujące. Jednak, aby można było korzystać z usług .NET XAML, definicje struktury języka XAML namescope muszą być zgodne z definicją <xref:System.Windows.Markup.INameScope> informacji w tej dokumentacji i powinny używać tych samych zasad, w których są stosowane informacje. Na przykład [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementacja dzieli różne elementy znaczników na oddzielne <xref:System.Windows.NameScope> zakresy, takie jak słowniki zasobów, Drzewo logiczne utworzone przez kod XAML, szablony i inną odroczoną zawartość, a następnie Wymusza unikatowość nazw XAML w ramach każdego z tych Zakresy nazw WPF języka XAML.

W przypadku typów niestandardowych, które używają modułów zapisujących obiektów XAML usług .NET XAML, właściwość, która jest mapowana na `x:Name` na typ, może zostać ustanowiona lub zmieniona. Należy zdefiniować to zachowanie, odwołując się do nazwy właściwości, która ma zostać zmapowana <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> w kodzie definicji typu.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> jest atrybutem na poziomie typu.

Usługi XAML Using.NET umożliwiają zdefiniowanie logiki zapasowej dla obsługi namescope języka XAML w sposób neutralny w strukturze przez implementację <xref:System.Windows.Markup.INameScope> interfejsu.

## <a name="wpf-usage-notes"></a>Uwagi dotyczące użycia WPF

W ramach standardowej konfiguracji kompilacji dla [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] aplikacji, która używa języka XAML, klas częściowych i kodu, określony obiekt jest `x:Name` nazwą pola, które jest tworzone w kodzie źródłowym, gdy [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] jest przetwarzana przez zadanie kompilacji tworzenia znaczników, a to pole zawiera odwołanie do obiektu. Domyślnie utworzone pole jest polem wewnętrznym. Można zmienić dostęp do pola, określając [atrybut x:FieldModifier —](xfieldmodifier-directive.md). W WPF i Silverlight, sekwencja polega na tym, że kompilacja adiustacji definiuje i nazwać pole w klasie częściowej, ale wartość jest początkowo pusta. Następnie wygenerowana Metoda o nazwie `InitializeComponent` jest wywoływana z poziomu konstruktora klasy. `InitializeComponent` składa się z `FindName` wywołań przy użyciu każdej `x:Name` wartości, która istnieje w części klasy częściowej zdefiniowanej w kodzie XAML jako ciągów wejściowych. Wartości zwracane są następnie przypisywane do odwołania do pola o podobnej nazwie, aby wypełnić wartości pola obiektami, które zostały utworzone na podstawie analizy XAML. Wykonanie może `InitializeComponent` odwoływać się do grafu obiektu czasu wykonywania przy użyciu `x:Name` nazwy pola lub bezpośrednio, a nie musi być jawnie wywoływana, gdy `FindName` potrzebujesz odwołania do obiektu zdefiniowanego w języku XAML.

W przypadku aplikacji WPF, która używa obiektów docelowych Microsoft Visual Basic i zawiera pliki XAML z `Page` akcją kompilacji, oddzielna Właściwość odwołania jest tworzona podczas kompilacji, która dodaje `WithEvents` słowo kluczowe do wszystkich elementów, które mają `x:Name` do obsługi `Handles` składni delegatów obsługi zdarzeń. Ta właściwość jest zawsze publiczna. Aby uzyskać więcej informacji, zobacz [Visual Basic i obsługa zdarzeń WPF](/dotnet/desktop/wpf/advanced/visual-basic-and-wpf-event-handling).

`x:Name` jest używany przez procesor WPF XAML do zarejestrowania nazwy w namescope języka XAML w czasie ładowania, nawet w przypadku przypadków, gdy strona nie jest skompilowana do adiustacji przez akcje kompilacji (na przykład luźny kod XAML słownika zasobów). Jedną z przyczyn tego problemu jest to, że `x:Name` jest potencjalnie wymagana do <xref:System.Windows.Data.Binding.ElementName%2A> powiązania. Aby uzyskać szczegółowe informacje, zobacz temat [powiązanie danych — omówienie](../data/data-binding-overview.md).

Jak wspomniano wcześniej, `x:Name` (lub `Name` ) nie należy stosować w sytuacjach, w których są również używane `x:Key` . [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> Ma specjalne zachowanie w zakresie definiowania siebie jako namescope języka XAML, ale zwracając wartość nie zaimplementowane lub wartość null dla <xref:System.Windows.Markup.INameScope> interfejsów API w celu wymuszenia tego zachowania. Jeśli analizator XAML WPF napotka `Name` lub `x:Name` w zdefiniowanej przez kod XAML <xref:System.Windows.ResourceDictionary> , nazwa nie zostanie dodana do żadnych namescope języka XAML. Podjęto próbę znalezienia tej nazwy z dowolnych namescope języka XAML, a `FindName` metody nie będą zwracać prawidłowych wyników.

### <a name="xname-and-name"></a>x:Name i nazwa

Wiele scenariuszy aplikacji WPF może uniknąć użycia `x:Name` atrybutu, ponieważ `Name` Właściwość zależności określona w domyślnej przestrzeni nazw XAML dla kilku ważnych klas bazowych, takich jak <xref:System.Windows.FrameworkElement> i <xref:System.Windows.FrameworkContentElement> spełnia ten sam cel. Nadal istnieją typowe scenariusze języka XAML i WPF, w przypadku których kod dostępu do elementu bez `Name` właściwości na poziomie struktury jest ważny. Na przykład niektóre klasy obsługi animacji i scenorysu nie obsługują `Name` właściwości, ale często muszą być przywoływane w kodzie w celu kontrolowania animacji. Należy określić `x:Name` jako atrybut na osiach czasu i transformacje, które są tworzone w języku XAML, jeśli zamierzasz odwoływać je od kodu później.

Jeśli <xref:System.Windows.FrameworkElement.Name%2A> jest dostępna jako właściwość w klasie <xref:System.Windows.FrameworkElement.Name%2A> i `x:Name` może być używana zamiennie jako atrybuty, ale wyjątek analizy spowoduje, jeśli oba te elementy zostaną określone w tym samym elemencie. Jeśli XAML ma skompilowane znaczniki, wyjątek wystąpi podczas kompilowania znaczników, w przeciwnym razie następuje po załadowaniu.

<xref:System.Windows.FrameworkElement.Name%2A> można ustawić przy użyciu składni atrybutu XAML i w kodzie przy użyciu <xref:System.Windows.DependencyObject.SetValue%2A> ; Pamiętaj jednak, że ustawienie <xref:System.Windows.FrameworkElement.Name%2A> właściwości w kodzie nie tworzy odwołania do pola reprezentatywnego w namescope XAML w większości sytuacji, gdy XAML jest już załadowany. Zamiast próbować ustawić <xref:System.Windows.FrameworkElement.Name%2A> w kodzie, użyj <xref:System.Windows.NameScope> metod z kodu, względem odpowiednich NameScope.

<xref:System.Windows.FrameworkElement.Name%2A> można również ustawić przy użyciu składni elementu właściwości z tekstem wewnętrznym, ale jest to nietypowe. W przeciwieństwie, `x:Name` nie można ustawić w składni elementu właściwości XAML ani w kodzie za pomocą <xref:System.Windows.DependencyObject.SetValue%2A> ; można ustawić ją tylko przy użyciu składni atrybutów dla obiektów, ponieważ jest to dyrektywa.

## <a name="silverlight-usage-notes"></a>Uwagi dotyczące użycia programu Silverlight

`x:Name` program Silverlight jest udokumentowany osobno. Aby uzyskać więcej informacji, zobacz [przestrzeń nazw XAML (x:) Funkcje języka (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Drzewa w WPF](/dotnet/desktop/wpf/advanced/trees-in-wpf)
