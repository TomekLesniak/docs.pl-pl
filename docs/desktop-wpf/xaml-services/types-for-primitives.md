---
title: Typy wbudowane dla wspólnych elementów podstawowych języka XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: ec0e2a29a191d5057ce66a5f3272d00e92b01bd7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540032"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a>Typy wbudowane dla wspólnych elementów podstawowych języka XAML

XAML 2009 wprowadza obsługę poziomu języka XAML dla kilku typów danych, które są często używane jako elementy pierwotne w środowisku uruchomieniowym języka wspólnego (CLR) i w innych językach programowania. Język XAML 2009 dodaje obsługę tych elementów podstawowych:,,,,,,,,, `x:Object` `x:Boolean` `x:Char` `x:String` `x:Decimal` `x:Single` `x:Double` `x:Int16` `x:Int32` `x:Int64` , `x:TimeSpan` , `x:Uri` ,, `x:Byte` i `x:Array`

## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a>Poprzednie techniki dla elementów podstawowych języka w znacznikach XAML

 W języku XAML dla wcześniejszych wersji WPF można przywołać elementy podstawowe języka CLR, mapując zestaw i przestrzeń nazw, które zawierały klasę definicji pierwotnej CLR dla .NET Framework. Większość z nich znajduje się w zestawie mscorlib i <xref:System> przestrzeni nazw. Na przykład, aby użyć <xref:System.Int32> , można zadeklarować następujące mapowanie (z przykładowym użyciem):

```xaml
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Application.Resources>
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>
  </Application.Resources>
</Application>
```

## <a name="xaml-2009-language-primitives"></a>Elementy podstawowe języka XAML 2009

Zgodnie z Konwencją, są wyświetlane elementy podstawowe języka XAML i wszystkich innych elementów języka XAML, łącznie z `x:` prefiksem. Jest to sposób, w jaki elementy języka XAML są zwykle używane w oznakowaniu rzeczywistym. Ta konwencja jest stosowana w dokumentacji koncepcyjnej języka XAML w WPF, a także w specyfikacji języka XAML.

### <a name="xobject"></a>x:Object

W przypadku środowiska CLR element `x:Object` podstawowy odpowiada <xref:System.Object> .

Ten element podstawowy nie jest zazwyczaj używany w znacznikach aplikacji, ale może być przydatny w niektórych scenariuszach, takich jak sprawdzanie możliwości przypisywania w systemie typów XAML.

### <a name="xboolean"></a>x:Boolean

W przypadku środowiska CLR element `x:Boolean` podstawowy odpowiada <xref:System.Boolean> .

KOD XAML analizuje wartości `x:Boolean` jako nieuwzględniające wielkości liter. Należy zauważyć, że `x:Bool` nie jest zaakceptowaną alternatywą. Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.17 i 5.4.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xchar"></a>x:Char

W przypadku środowiska CLR element `x:Char` podstawowy odpowiada <xref:System.Char> .

Typy String i char mają interakcję z ogólnym kodowaniem pliku na poziomie XML. Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.7 i 5.4.1](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xstring"></a>x:String

W przypadku środowiska CLR element `x:String` podstawowy odpowiada <xref:System.String> .

Typy String i char mają interakcję z ogólnym kodowaniem pliku na poziomie XML. Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xdecimal"></a>x:Decimal

W przypadku środowiska CLR element `x:Decimal` podstawowy odpowiada <xref:System.Decimal> .

Analiza kodu XAML jest zaimplementowana w ramach `en-US` kultury. W obszarze `en-US` kultura prawidłowy separator składników dziesiętnych jest zawsze kropką ( `.` ) niezależnie od ustawień kultury środowiska programistycznego lub miejsca docelowego klienta, gdzie XAML jest ładowany w czasie wykonywania.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.14 i 5.4.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xsingle"></a>x:Single

W przypadku środowiska CLR element `x:Single` podstawowy odpowiada <xref:System.Single> .

Oprócz wartości liczbowych, składnia tekstu dla `x:Single` również zezwala na tokeny `Infinity` , `-Infinity` i `NaN` . Te tokeny są traktowane jako uwzględniające wielkość liter.

`x:Single` może obsługiwać wartości w postaci notacji naukowej, jeśli pierwszy znak w składni tekstu jest `e` lub `E` .

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.8 i 5.4.2](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xdouble"></a>x:Double

W przypadku środowiska CLR element `x:Double` podstawowy odpowiada <xref:System.Double> .

Oprócz wartości liczbowych, składnia tekstu dla zezwala na `x:Double` tokeny `Infinity` , `-Infinity` i `NaN` . Te tokeny są traktowane jako uwzględniające wielkość liter.

`x:Double` może obsługiwać wartości w postaci notacji naukowej. Użyj znaku `e` lub, `E` Aby wprowadzić część wykładnika.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.9 i 5.4.3](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xint16"></a>x:Int16

W przypadku tworzenia kopii zapasowych CLR element `x:Int16` podstawowy odpowiada <xref:System.Int16> i `x:Int16` jest traktowany jako podpisany. W języku XAML nieobecność znaku plus ( `+` ) w składni tekstu jest implikowana jako dodatnia wartość ze znakiem.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.11 i 5.4.5](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xint32"></a>x:Int32

W przypadku środowiska CLR element `x:Int32` podstawowy odpowiada <xref:System.Int32> . `x:Int32` jest traktowane jako podpisane. W języku XAML nieobecność znaku plus ( `+` ) w składni tekstu jest implikowana jako dodatnia wartość ze znakiem.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.12 i 5.4.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xint64"></a>x:Int64

W przypadku środowiska CLR element `x:Int64` podstawowy odpowiada <xref:System.Int64> . `x:Int64` jest traktowane jako podpisane. W języku XAML nieobecność znaku plus ( `+` ) w składni tekstu jest implikowana jako dodatnia wartość ze znakiem.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.13 i 5.4.7](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xtimespan"></a>x:TimeSpan

W przypadku środowiska CLR element `x:TimeSpan` podstawowy odpowiada <xref:System.TimeSpan> .

Analiza kodu XAML dla formatu daty i godziny jest zaimplementowana w ramach `en-US` kultury.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.16 i 5.4.10](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xuri"></a>x:Uri

W przypadku środowiska CLR element `x:Uri` podstawowy odpowiada <xref:System.Uri> .

Sprawdzanie protokołów nie jest częścią definicji XAML dla `x:Uri` .

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.15 i 5.4.9](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xbyte"></a>x:Byte

W przypadku środowiska CLR element `x:Byte` podstawowy odpowiada <xref:System.Byte> . A <xref:System.Byte>  /  `x:Byte` jest traktowana jako niepodpisana.

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.10 i 5.4.4](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xarray"></a>x:Array

W przypadku środowiska CLR element `x:Array` podstawowy odpowiada <xref:System.Array> .

Można zdefiniować tablicę w języku XAML 2006 przy użyciu składni rozszerzenia znaczników; Jednak składnia XAML 2009 jest zdefiniowaną przez język podstawową, która nie wymaga dostępu do rozszerzenia znacznika. Aby uzyskać więcej informacji na temat obsługi języka XAML 2006, zobacz [X:Array Markup Extension](xarray-markup-extension.md).

Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.18](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="wpf-support"></a>Obsługa WPF

W programie WPF można używać funkcji języka XAML 2009, ale tylko dla języka XAML, który nie jest kompilowany do znaczników. Skompilowane znaczniki XAML dla WPF i forma BAML języka XAML nie obsługują obecnie słów kluczowych i funkcji języka XAML 2009.

Scenariusz, w którym można używać funkcji języka XAML 2009 razem z WPF, to jeśli utworzysz luźny kod XAML, a następnie załadujesz ten kod XAML do środowiska uruchomieniowego WPF i grafu obiektów przy użyciu <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> . WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> i jego <xref:System.Windows.Markup.XamlReader.Load%2A> Funkcja może przetwarzać słowa kluczowe języka XAML 2009 i funkcje do prawidłowej reprezentacji grafu obiektów.
