---
title: x:Subclass — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540722"
---
# <a name="xsubclass-directive"></a>x:Subclass — dyrektywa

Modyfikuje zachowanie kompilowania znaczników XAML, gdy `x:Class` jest również udostępniane. Zamiast tworzenia klasy częściowej, która jest oparta na `x:Class` , dostarczony `x:Class` element jest tworzony jako Klasa pośrednicząca, a następnie powinna być oparta na podanej klasie pochodnej `x:Class` .

## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`namespace`|Opcjonalny. Określa przestrzeń nazw środowiska CLR, która zawiera `classname` . Jeśli `namespace` jest określony, kropka (.) oddziela `namespace` i `classname` .|
|`classname`|Wymagany. Określa nazwę CLR klasy częściowej, która łączy załadowany kod XAML i związany z kodem dla tego języka XAML. Zobacz uwagi.|
|`subclassNamespace`|Opcjonalny. Może się różnić od `namespace` tego, czy każda przestrzeń nazw może rozwiązać ten problem. Określa przestrzeń nazw środowiska CLR, która zawiera `subclassName` . Jeśli `subclassName` jest określony, kropka (.) oddziela `subclassNamespace` i `subclassName` .|
|`subclassName`|Wymagany. Określa nazwę środowiska CLR podklasy.|

## <a name="dependencies"></a>Zależności

[dyrektywa x:Class](xclass-directive.md) musi być również podana dla tego samego obiektu i musi być elementem głównym produkcji XAML.

## <a name="remarks"></a>Uwagi

`x:Subclass` Użycie jest przeznaczone głównie dla języków, które nie obsługują deklaracji klasy częściowej.

Klasa używana jako `x:Subclass` nie może być klasą zagnieżdżoną i `x:Subclass` musi odwoływać się do obiektu głównego zgodnie z opisem w sekcji "zależności".

W przeciwnym razie koncepcyjne znaczenie `x:Subclass` jest niezdefiniowane przez implementację usług .NET XAML. Wynika to z faktu, że zachowanie usług .NET XAML nie określa ogólnego modelu programowania, w którym są połączone znaczniki XAML i kod zapasowy. Implementacje dalszych koncepcji związanych z programem `x:Class` i `x:Subclass` są wykonywane przez określone platformy, które używają modeli programowania lub modeli aplikacji do definiowania sposobu łączenia znaczników XAML, skompilowanych znaczników i kodu opartego na środowisku CLR. Każda struktura może mieć własne akcje kompilacji, które umożliwiają zachowanie niektórych zachowań lub określonych składników, które muszą być zawarte w środowisku kompilacji. W ramach struktury akcje kompilacji mogą się różnić w zależności od języka CLR, który jest używany w kodzie.

## <a name="wpf-usage-notes"></a>Uwagi dotyczące użycia WPF

`x:Subclass` może znajdować się w katalogu głównym strony lub w <xref:System.Windows.Application> katalogu głównym w definicji aplikacji, która już ma `x:Class` . Deklarowanie `x:Subclass` dla dowolnego elementu, innego niż strona lub katalog główny lub określenie, gdzie nie `x:Class` istnieje, powoduje błąd czasu kompilacji.

Tworzenie klas pochodnych, które działają poprawnie dla `x:Subclass` scenariusza, jest dość skomplikowane. Może być konieczne przeanalizowanie plików pośrednich (plików g produkowanych w folderze obj projektu przez kompilację znaczników z nazwami, które zawierają nazwy plików. XAML). Te pliki pośrednie mogą pomóc określić źródło niektórych konstrukcji programistycznych w sprzężonych klasach częściowych w skompilowanej aplikacji.

Procedury obsługi zdarzeń w klasie pochodnej muszą być `internal override` ( `Friend Overrides` w programie Microsoft Visual Basic), aby przesłonić elementy pośredniczące dla programów obsługi jako utworzone w klasie pośredniej podczas kompilacji. W przeciwnym razie implementacje klas pochodnych ukryją (Shadow) implementację klasy pośredniej i procedury obsługi klasy pośredniczącej nie są wywoływane.

Podczas definiowania obu `x:Class` i `x:Subclass` , nie trzeba podawać żadnej implementacji dla klasy, do której odwołuje się `x:Class` . Wystarczy nadać mu nazwę przy użyciu `x:Class` atrybutu, aby kompilator miał pewne wskazówki dotyczące klasy, którą tworzy w plikach pośrednich (w tym przypadku kompilator nie wybiera nazwy domyślnej). Można nadać `x:Class` klasie implementację, ale nie jest to typowy scenariusz użycia obu `x:Class` i `x:Subclass` .

## <a name="see-also"></a>Zobacz także

- [x:Class — dyrektywa](xclass-directive.md)
- [Klasy XAML i niestandardowe dla WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
