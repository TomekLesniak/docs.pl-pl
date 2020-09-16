---
title: x:Shared — Atrybut
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557791"
---
# <a name="xshared-attribute"></a>x:Shared — Atrybut

Gdy jest ustawiona na `false` , modyfikuje zachowanie pobierania zasobów WPF, tak że żądania dla zasobu z atrybutami tworzą nowe wystąpienie dla każdego żądania, zamiast udostępniać to samo wystąpienie dla wszystkich żądań.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Uwagi

`x:Shared` jest mapowany do przestrzeni nazw XAML języka XAML i jest rozpoznawany jako prawidłowy element języka XAML przez usługi .NET XAML i jego czytelnicy XAML. Jednak podane możliwości programu `x:Shared` są odpowiednie dla aplikacji WPF i analizatora XAML WPF. W WPF, `x:Shared` jest przydatna tylko jako atrybut, gdy jest stosowany do obiektu, który istnieje w WPF <xref:System.Windows.ResourceDictionary> . Inne użycia nie generują wyjątków analizy ani innych błędów, ale nie mają żadnego wpływu.

Znaczenie `x:Shared` nie jest określone w specyfikacji języka XAML. Inne implementacje XAML, takie jak te, które kompilują się w usługach .NET XAML, nie muszą zapewniać obsługi udostępniania zasobów. Takie implementacje XAML mogą zapewnić podobne zachowanie w strukturze pomocniczej, która również używa `x:Shared` wartości.

W WPF, domyślny `x:Shared` warunek dla zasobów to `true` . Ten stan oznacza, że każde żądanie zasobu zawsze zwraca to samo wystąpienie.

Modyfikowanie obiektu, który jest zwracany przez interfejs API zasobów, na przykład <xref:System.Windows.FrameworkElement.FindResource%2A> lub modyfikowanie obiektu bezpośrednio w ramach <xref:System.Windows.ResourceDictionary> , powoduje zmianę oryginalnego zasobu. Jeśli odwołania do tego zasobu były odwołaniami do zasobów dynamicznych, odbiorcy tego zasobu otrzymują zmieniony zasób.

Jeśli odwołania do zasobu były odwołaniami zasobów statycznych, zmiany w zasobie po [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] czasie przetwarzania są nieistotne. Aby uzyskać więcej informacji na temat odwołań do zasobów statycznych i dynamicznych, zobacz [zasoby XAML](../fundamentals/xaml-resources-define.md).

Jawne określenie `x:Shared="true"` jest rzadko wykonywane, ponieważ jest już wartością domyślną. W modelu obiektów WPF nie ma bezpośredniego odpowiednika kodu `x:Shared` . można go określić tylko w użyciu języka XAML i musi być przetwarzany przy użyciu domyślnego zachowania WPF lub w pośrednim strumieniu węzła XAML w ścieżce ładowania, jeśli przetworzono je za pomocą usług .NET XAML i ich czytników XAML.

Scenariusz dla programu `x:Shared="false"` jest zdefiniowany <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> jako zasób lub Klasa pochodna, a następnie wprowadzasz zasób elementu do modelu zawartości. `x:Shared="false"` umożliwia wprowadzenie zasobu elementu wiele razy w tej samej kolekcji (na przykład <xref:System.Windows.Controls.UIElementCollection> ). Bez `x:Shared="false"` tego jest nieprawidłowa, ponieważ kolekcja Wymusza unikatowość jego zawartości. Jednak `x:Shared="false"` zachowanie tworzy inne identyczne wystąpienie zasobu, a nie zwraca tego samego wystąpienia.

Innym scenariuszem dla `x:Shared="false"` jest użycie <xref:System.Windows.Freezable> zasobu do wartości animacji, ale chcesz zmodyfikować zasób dla każdej animacji.

W obsłudze ciągów `false` nie jest rozróżniana wielkość liter.

W WPF, `x:Shared` jest prawidłowy tylko w następujących warunkach:

- <xref:System.Windows.ResourceDictionary>Element zawierający elementy z `x:Shared` musi być skompilowany. <xref:System.Windows.ResourceDictionary>Nie może znajdować się w luźnym kodzie XAML ani używać dla motywów.

- <xref:System.Windows.ResourceDictionary>Element zawierający elementy nie może być zagnieżdżony w innym <xref:System.Windows.ResourceDictionary> . Na przykład nie można użyć `x:Shared` dla elementów znajdujących się w, która znajduje się już w <xref:System.Windows.ResourceDictionary> <xref:System.Windows.Style> <xref:System.Windows.ResourceDictionary> elemencie.

## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.ResourceDictionary>
- [Zasoby XAML](../fundamentals/xaml-resources-define.md)
- [Elementy bazy](/dotnet/desktop/wpf/advanced/base-elements)
