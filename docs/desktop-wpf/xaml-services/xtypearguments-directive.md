---
title: x:TypeArguments — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543554"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments — dyrektywa

Przekazuje argumenty typu ograniczającego ogólnego do konstruktora typu ogólnego.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`object`|Deklaracja elementu obiektu typu XAML, która jest obsługiwana przez typ ogólny środowiska CLR. Jeśli `object` odwołuje się do typu XAML, który nie pochodzi z domyślnej przestrzeni nazw XAML, program `object` wymaga prefiksu, aby wskazać przestrzeń nazw XAML, gdzie `object` istnieje.|
|`typeString`|Ciąg, który deklaruje co najmniej jedną nazwę typu XAML jako ciągi znaków, który dostarcza argumentów typu dla typu ogólnego CLR. Zobacz uwagi, aby uzyskać dodatkowe informacje o składni.|

## <a name="remarks"></a>Uwagi

W większości przypadków typy XAML, które są używane jako element informacji w `typeString` ciągu, są poprzedzone prefiksem. Typowe typy ograniczeń ogólnych CLR (na przykład <xref:System.Int32> i <xref:System.String> ) pochodzą z bibliotek klas podstawowych CLR. Te biblioteki nie są zamapowane na typowe obszary nazw języka XAML specyficzne dla platformy i dlatego wymagają mapowania prefiksów dla użycia XAML.

Można określić więcej niż jedną nazwę typu XAML przy użyciu ogranicznika przecinka.

Jeśli ogólne ograniczenia same używają typów ogólnych, argumenty zagnieżdżonych typów ograniczeń mogą być zawarte w nawiasach ().

Należy zauważyć, że ta definicja `x:TypeArguments` jest specyficzna dla usług .NET XAML i tworzenia kopii zapasowych przy użyciu środowiska CLR. Definicję poziomu języka można znaleźć w [ \[ sekcji MS-XAML \] 5.3.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Przykłady użycia

W poniższych przykładach założono, że są zadeklarowane następujące definicje przestrzeni nazw XAML:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>Staw\<String>

`<scg:List x:TypeArguments="sys:String" ...>` tworzy wystąpienie elementu New <xref:System.Collections.Generic.List%601> z <xref:System.String> argumentem typu.

### <a name="dictionarystringstring"></a>Słownik\<String,String>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` tworzy wystąpienie nowego <xref:System.Collections.Generic.Dictionary%602> z dwoma <xref:System.String> argumentami typu.

### <a name="queuekeyvaluepairstringstring"></a>Kolejka<KeyValuePair\<String,String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` tworzy wystąpienie nowego <xref:System.Collections.Generic.Queue%601> , który ma ograniczenie z <xref:System.Collections.Generic.KeyValuePair%602> argumentami typu ograniczenia wewnętrznego <xref:System.String> i <xref:System.String> .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 i WPF — ogólne użycia XAML

W przypadku użycia języka XAML 2006 i języka XAML, który jest używany przez aplikacje WPF, istnieją następujące ograniczenia dotyczące `x:TypeArguments` użycia typów ogólnych w języku XAML:

- Tylko element główny pliku XAML może obsługiwać ogólne użycie XAML, które odwołuje się do typu ogólnego.

- Element główny musi być mapowany do typu ogólnego z co najmniej jednym argumentem typu. Może to być na przykład <xref:System.Windows.Navigation.PageFunction%601>. Funkcje strony są głównym scenariuszem obsługi ogólnych zastosowań XAML w programie WPF.

- Element główny elementu XAML elementu generycznego musi również deklarować klasy częściowej przy użyciu `x:Class` . Jest to prawdziwe nawet w przypadku definiowania akcji kompilacji WPF.

- `x:TypeArguments` nie można odwoływać się do zagnieżdżonych ograniczeń ogólnych.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 lub XAML 2006 bez zależności WPF 3,0 lub WPF 3,5

W usługach .NET XAML dla języka XAML 2006 lub XAML 2009 ograniczenia związane z WPF dla ogólnego użycia XAML są swobodne. Można utworzyć wystąpienie elementu ogólnego obiektu w dowolnym miejscu w znaczniku XAML, który może obsługiwać system typu zapasowego i model obiektów.

Jeśli używasz języka XAML 2009 zamiast mapowania typów podstawowych CLR w celu uzyskania typów XAML dla elementów podstawowych języka wspólnego, możesz użyć [typów wbudowanych dla wspólnych prymitywów języka XAML](types-for-primitives.md) jako elementy informacji w `typeString` . Można na przykład zadeklarować następujące elementy (mapowania prefiksów nie są wyświetlane, ale x jest przestrzenią nazw XAML języka XAML dla XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

W programie WPF i w przypadku określania wartości docelowej .NET Framework 4 lub .NET Core 3,0 (lub nowszej) można używać funkcji języka XAML 2009 razem z programem, `x:TypeArguments` ale tylko w przypadku swobodnego języka XAML (XAML, który nie jest skompilowany do adiustacji). Skompilowane znaczniki XAML dla WPF i forma BAML języka XAML nie obsługują obecnie słów kluczowych i funkcji języka XAML 2009. Jeśli zachodzi konieczność skompilowania kodu XAML, należy wykonać działania zgodnie z ograniczeniami wymienionymi w sekcji [języka xaml 2006 i WPF ogólnych użycia XAML](#xaml-2006-and-wpf-generic-xaml-usages) . BAML jest obsługiwana tylko w .NET Framework.

## <a name="see-also"></a>Zobacz także

- [x:Class — dyrektywa](xclass-directive.md)
- [x:Type — Rozszerzenie znaczników](xtype-markup-extension.md)
- [Typy wbudowane dla wspólnych elementów podstawowych języka XAML](types-for-primitives.md)
- [Typy ogólne w XAML](generics.md)
