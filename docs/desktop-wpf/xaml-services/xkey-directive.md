---
title: x:Key — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: 7e4e9cbded01297818f9f01df01e95e94d7dc4af
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548276"
---
# <a name="xkey-directive"></a>x:Key — dyrektywa
Jednoznacznie identyfikuje elementy, które są tworzone i przywoływane w słowniku zdefiniowanym przez język XAML. Dodanie `x:Key` wartości do elementu obiektu XAML jest najczęstszym sposobem identyfikowania zasobu w słowniku zasobów, na przykład w WPF <xref:System.Windows.ResourceDictionary> .  
  
## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Użycie atrybutu języka XAML (specyficzne dla platformy WPF)  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|`stringKeyValue`|Ciąg tekstowy, który ma być używany jako klucz. Ciąg tekstowy musi być zgodny z [gramatyką XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|W ramach ograniczników rozszerzenia znaczników {} użycie rozszerzenia znacznika zapewnia obiekt do użycia jako klucz. Zobacz uwagi.|  
  
## <a name="remarks"></a>Uwagi  
 `x:Key` obsługuje koncepcję słownika zasobów XAML. XAML jako język nie definiuje implementacji słownika zasobów, która jest pozostała do określonych platform interfejsu użytkownika. Aby dowiedzieć się więcej o sposobie implementacji słowników zasobów XAML w WPF, zobacz [zasoby XAML](../fundamentals/xaml-resources-define.md).  
  
 W języku XAML 2006 i WPF `x:Key` należy podać jako atrybut. Nadal można używać kluczy niebędących ciągami, ale wymaga to użycia rozszerzenia znacznika, aby zapewnić wartość niebędącą ciągiem w formie atrybutu. Jeśli używasz języka XAML 2009, `x:Key` można go określić jako element, aby jawnie obsługiwać słowniki z typami obiektów innymi niż ciągi bez konieczności pośredniego rozszerzenia znaczników. Zobacz sekcję "XAML 2009" w tym temacie. Pozostała część sekcji uwagi dotyczy implementacji języka XAML 2006.  
  
 Wartość atrybutu `x:Key` może być dowolnego ciągu zdefiniowanego w [gramatycename XAML](xamlname-grammar.md) lub może być obiektem ocenianym za pomocą rozszerzenia znacznika. Zobacz sekcję "uwagi dotyczące użycia WPF", aby zapoznać się z przykładem z platformy WPF.  
  
 Elementy podrzędne elementu nadrzędnego, który jest <xref:System.Collections.IDictionary> implementacją, muszą zazwyczaj zawierać `x:Key` atrybut, który określa unikatową wartość klucza w tym słowniku. Struktury mogą implementować aliasy właściwości klucza do podstawiania dla `x:Key` konkretnych typów; typy, które definiują takie właściwości, powinny być przypisane do <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> .  
  
 Odpowiednikiem kodu określającym `x:Key` jest klucz, który jest używany dla elementu bazowego <xref:System.Collections.IDictionary> . Na przykład, `x:Key` który jest stosowany podczas adiustacji dla zasobu w WPF, jest odpowiednikiem wartości `key` parametru <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> podczas dodawania zasobu do WPF <xref:System.Windows.ResourceDictionary> w kodzie.  
  
## <a name="wpf-usage-notes"></a>Uwagi dotyczące użycia WPF  
 Obiekty podrzędne obiektu nadrzędnego, który jest <xref:System.Collections.IDictionary> implementacją, taką jak WPF <xref:System.Windows.ResourceDictionary> , muszą zazwyczaj zawierać `x:Key` atrybut, a wartość klucza musi być unikatowa w obrębie tego słownika. Istnieją dwa istotne wyjątki:  
  
- Niektóre typy WPF deklarują klucz niejawny dla użycia słownika. Na przykład, <xref:System.Windows.Style> z <xref:System.Windows.Style.TargetType%2A> , lub z <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.DataType%2A> , może być w <xref:System.Windows.ResourceDictionary> i używać klucza niejawnego.  
  
- WPF obsługuje koncepcję scalonego słownika zasobów. Klucze mogą być współużytkowane przez scalone słowniki, a zachowanie klucza współużytkowanego można uzyskać za pomocą polecenia <xref:System.Windows.FrameworkContentElement.FindResource%2A> . Aby uzyskać więcej informacji, zobacz [scalone słowniki zasobów](/dotnet/desktop/wpf/advanced/merged-resource-dictionaries).  
  
 W ogólnej implementacji języka XAML WPF i modelu aplikacji Unikatowość klucza nie jest sprawdzana przez kompilator znaczników XAML. Zamiast tego brakujące lub nieunikatowe `x:Key` wartości powodują błędy analizatora XAML czasu ładowania. Jednak obsługa słowników dla WPF w programie Visual Studio może często zanotować takie błędy w fazie projektowania.  
  
 Należy zauważyć, że w pokazanej składni <xref:System.Windows.ResourceDictionary> obiekt jest niejawny w sposobie tworzenia kolekcji przez procesor WPF XAML <xref:System.Windows.FrameworkElement.Resources%2A> . Element <xref:System.Windows.ResourceDictionary> nie jest zwykle dostarczany w sposób jawny w znacznikach, chociaż może być w niektórych przypadkach, jeśli wolisz dla przejrzystości (będzie to element obiektu kolekcji między <xref:System.Windows.FrameworkElement.Resources%2A> elementem właściwości i elementami w tym zapełnieniu słownika). Aby uzyskać informacje o tym, dlaczego obiekt kolekcji prawie zawsze jest niejawny element w znaczniku, zobacz [Szczegóły składni XAML](/dotnet/desktop/wpf/advanced/xaml-syntax-in-detail).  
  
 W implementacji języka XAML WPF obsługa kluczy słownika zasobów jest definiowana przez <xref:System.Windows.ResourceKey> klasę abstrakcyjną. Jednak procesor WPF XAML produkuje różne podstawowe typy rozszerzeń dla kluczy na podstawie ich użycia. Na przykład klucz dla <xref:System.Windows.DataTemplate> lub dowolnej klasy pochodnej jest obsługiwany osobno i tworzy oddzielny <xref:System.Windows.DataTemplateKey> obiekt.  
  
 Klucze i nazwy używają różnych dyrektyw i elementów języka ( `x:Key` a `x:Name` ) w podstawowej definicji XAML. Klucze i nazwy są również używane w różnych sytuacjach przy użyciu definicji WPF i aplikacji. Aby uzyskać szczegółowe informacje, zobacz [WPF XAML Zakresy nazw WPF](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes).  
  
 Jak wspomniano wcześniej, wartość klucza może być dostarczana za pomocą rozszerzenia znacznika i może być inna niż wartość ciągu. Przykładowy scenariusz WPF polega na tym, że wartość `x:Key` może być [ComponentResourceKey](/dotnet/desktop/wpf/advanced/componentresourcekey-markup-extension). Niektóre formanty uwidaczniają klucz stylu tego typu dla zasobu stylu niestandardowego, który wpływa na część wyglądu i zachowania tej kontrolki bez całkowitego zastępowania stylu. Przykładem takiego klucza jest <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A> .  
  
 Funkcja scalonego słownika WPF zawiera dodatkowe zagadnienia dotyczące unikatowego klucza i zachowania wyszukiwania kluczy. Aby uzyskać więcej informacji, zobacz [scalone słowniki zasobów](/dotnet/desktop/wpf/advanced/merged-resource-dictionaries).  
  
## <a name="xaml-2009"></a>XAML 2009  
 KOD XAML 2009 ogranicza ograniczenia, które `x:Key` zawsze są udostępniane w formie atrybutu.  
  
 W programie WPF można używać funkcji języka XAML 2009, ale tylko dla języka XAML, który nie jest kompilowany do znaczników. Skompilowane znaczniki XAML dla WPF i forma BAML języka XAML nie obsługują obecnie słów kluczowych i funkcji języka XAML 2009.  
  
 W obszarze XAML 2009 można określić `x:Key` elementy za pomocą następującego użycia:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Użycie elementu XAML (tylko XAML 2009)  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|`keyObject`|Element obiektu dla obiektu, który jest używany jako klucz dla danego `object` w specjalnym słowniku.|  
  
- Nie pokazano tutaj kontenera/elementu nadrzędnego dla tego rodzaju użycia. `object` powinien być elementem podrzędnym elementu obiektu, który reprezentuje implementację wyspecjalizowanego słownika. `keyObject` oczekuje się, że jest to wystąpienie obiektu (lub wartość typu wartości), które jest odpowiednie jako klucz dla danej implementacji wyspecjalizowanego słownika.  
  
- WPF nie implementuje słowników, które wymagają tego użycia. Klucze obiektów to bardziej ogólna funkcja języka XAML, prawdopodobnie przydatna w przypadku niektórych scenariuszy słownika niestandardowego, w których tworzenie słownika w języku XAML jest pożądane. W przypadku funkcji WPF, takich jak niejawne style, które używają kluczy niebędących ciągami dla zasobów, inne techniki służące do ustanawiania lub określania kluczy istnieją, dlatego nie trzeba używać klucza obiektu.  
  
- `keyObject` może to również być użycie rozszerzenia znacznika w formularzu elementu obiektu, a nie w bezpośrednim wystąpieniu obiektu.  
  
## <a name="silverlight-usage-notes"></a>Uwagi dotyczące użycia programu Silverlight  
 `x:Key` program Silverlight jest udokumentowany osobno. Aby uzyskać więcej informacji, zobacz [przestrzeń nazw XAML (x:) Funkcje języka (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Zobacz także

- [Zasoby XAML](../fundamentals/xaml-resources-define.md)
- [Zasoby i kod](/dotnet/desktop/wpf/advanced/resources-and-code)
- [StaticResource — Rozszerzenie znaczników](/dotnet/desktop/wpf/advanced/staticresource-markup-extension)
