---
title: x:Class — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: 8f7ca5fdb170411aba24d34b8bf4d6c4f5776cc4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555149"
---
# <a name="xclass-directive"></a>x:Class — dyrektywa
Konfiguruje kompilację znaczników XAML, aby dołączyć klasy częściowe między adiustacją i kodem. Klasa fragmentu kodu jest definiowana w osobnym pliku kodu w języku Common Language Specification (CLS), natomiast Klasa fragmentu znaczników jest zazwyczaj tworzona przez generowanie kodu podczas kompilacji XAML.

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`namespace`|Opcjonalny. Określa przestrzeń nazw CLR, która zawiera klasę częściową identyfikowaną przez `classname` . Jeśli `namespace` jest określony, kropka (.) oddziela `namespace` i `classname` . Zobacz uwagi.|
|`classname`|Wymagany. Określa nazwę CLR klasy częściowej, która łączy załadowany kod XAML i związany z kodem dla tego języka XAML.|

## <a name="dependencies"></a>Zależności

`x:Class` można określić tylko dla elementu głównego w środowisku produkcyjnym XAML. `x:Class` jest nieprawidłowy dla każdego obiektu, który ma element nadrzędny w środowisku produkcyjnym XAML. Aby uzyskać więcej informacji, zobacz [ \[ sekcję MS-XAML \] 4.3.1.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Uwagi

`namespace`Wartość może zawierać dodatkowe kropki do organizowania powiązanych przestrzeni nazw w hierarchie nazw, które są typową techniką w programowaniu platformy .NET. Tylko Ostatnia kropka w ciągu `x:Class` wartości jest interpretowana jako oddzielona `namespace` , a `classname.` Klasa, która jest używana jako `x:Class` nie może być klasą zagnieżdżoną. Klasy zagnieżdżone są niedozwolone, ponieważ określenie znaczenia kropek dla `x:Class` ciągów jest niejednoznaczne, jeśli zagnieżdżone klasy są dozwolone.

W istniejących modelach programowania, które używają `x:Class` , `x:Class` jest opcjonalne w sensie, że jest całkowicie prawidłowy, aby mieć stronę XAML, która nie zawiera kodu. Jednak ta funkcja współdziała z akcjami kompilacji zaimplementowanymi przez platformy, które używają języka XAML. `x:Class` na możliwość ma także wpływ na role, które różne klasyfikacje zawartości w języku XAML mają w modelu aplikacji i w odpowiednich akcjach kompilacji. Jeśli kod XAML deklaruje wartości atrybutów obsługi zdarzeń lub tworzy wystąpienia elementów niestandardowych, w których klasy definiujące znajdują się w klasie związanej z kodem, należy podać `x:Class` odwołanie do dyrektywy (lub [x:Subclass —](xsubclass-directive.md)) do odpowiedniej klasy dla kodu.

Wartość `x:Class` dyrektywy musi być ciągiem, który określa w pełni kwalifikowaną nazwę klasy, ale nie zawiera żadnych informacji o zestawie (równoważnych <xref:System.Type.FullName%2A?displayProperty=nameWithType> ). W przypadku prostych aplikacji można pominąć informacje o przestrzeni nazw środowiska CLR, jeśli kod źródłowy jest również strukturalny w ten sposób (definicja kodu jest uruchamiana na poziomie klasy).

Plik związany z kodem dla definicji strony lub aplikacji musi znajdować się w pliku kodu, który jest zawarty w projekcie, który tworzy skompilowaną aplikację i obejmuje kompilację znaczników. Należy przestrzegać reguł nazw dla klas CLR. Aby uzyskać więcej informacji, zobacz [Framework — wskazówki dotyczące projektowania](../../../api/index.md). Domyślnie Klasa z kodem musi być, `public` ale można ją zdefiniować na innym poziomie dostępu za pomocą [dyrektywy x:ClassModifier —](xclassmodifier-directive.md).

Ta interpretacja `x:Class` atrybutu dotyczy tylko implementacji języka XAML opartego na środowisku CLR, w szczególności dla usług .NET XAML. Inne implementacje języka XAML, które nie są oparte na środowisku CLR i nie korzystają z usług .NET XAML, mogą używać innej formuły rozwiązania do łączenia znaczników XAML i zapasowego kodu czasu wykonywania. Aby uzyskać więcej informacji na temat bardziej ogólnych interpretacji `x:Class` , zobacz [ \[ MS- \] XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

W przypadku określonego poziomu architektury znaczenie `x:Class` jest niezdefiniowane w usługach .NET XAML. Wynika to z faktu, że usługi programu .NET XAML nie określają modelu programowania, w którym są połączone znaczniki XAML i kod zapasowy. Dodatkowe zastosowania `x:Class` dyrektywy mogą być implementowane przez konkretne struktury, które używają modeli programowania lub modeli aplikacji do definiowania sposobu łączenia ZNACZNIKÓW XAML i kodu opartego na środowisku CLR. Każda struktura może mieć własne akcje kompilacji, które umożliwiają zachowanie niektórych zachowań lub określonych składników, które muszą być zawarte w środowisku kompilacji. W ramach struktury akcje kompilacji mogą się różnić w zależności od konkretnego języka CLR, który jest używany w kodzie.

## <a name="xclass-in-the-wpf-programming-model"></a>x:Class w modelu programowania WPF

W aplikacjach WPF i modelu aplikacji WPF `x:Class` można zadeklarować jako atrybut dla dowolnego elementu, który jest elementem głównym pliku XAML i jest kompilowany (gdzie kod XAML jest zawarty w projekcie aplikacji WPF z `Page` akcją kompilacji) lub dla <xref:System.Windows.Application> katalogu głównego w definicji aplikacji skompilowanej aplikacji WPF. Deklarowanie `x:Class` dla elementu innego niż katalog główny lub katalog główny strony, lub w pliku XAML WPF, który nie jest kompilowany, powoduje błąd czasu kompilacji w ramach kompilatora .NET Framework 3,0 i .NET Framework 3,5 WPF XAML. Aby uzyskać informacje na temat innych aspektów `x:Class` obsługi w WPF, zobacz sekcję [kod i XAML w WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf).

## <a name="xclass-for-windows-workflow-foundation"></a>x:Class Windows Workflow Foundation
W przypadku Windows Workflow Foundation `x:Class` Nazwa klasy działania niestandardowego składa się w całości w języku XAML lub nazwa klasy częściowej strony XAML dla projektanta działań z kodem.

## <a name="silverlight-usage-notes"></a>Uwagi dotyczące użycia programu Silverlight

`x:Class` program Silverlight jest udokumentowany osobno. Aby uzyskać więcej informacji, zobacz [przestrzeń nazw XAML (x:) Funkcje języka (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Zobacz także

- [x:Subclass — dyrektywa](xsubclass-directive.md)
- [Klasy XAML i niestandardowe dla WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [x:ClassModifier — dyrektywa](xclassmodifier-directive.md)
- [Typy migrowane z WPF do System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
