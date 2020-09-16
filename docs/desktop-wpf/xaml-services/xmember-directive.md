---
title: x:Member — dyrektywa
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: 1c5b26b405e574290af54b29b22fb5e19e4b6b95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548250"
---
# <a name="xmember-directive"></a>x:Member — dyrektywa
Deklaruje element członkowski języka XAML w znaczniku.

## <a name="xaml-object-element-usage"></a>Użycie elementu obiektu języka XAML

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a>Wartości XAML

|||
|-|-|
|`className`|Nazwa klasy zapasowej lub klasy częściowej dla produkcji XAML.|
|`memberName`|Nazwa elementu członkowskiego zdefiniowanej właściwości.|

## <a name="remarks"></a>Uwagi

W implementacji usług platformy .NET XAML. `x:Member` nie ma bezpośredniego typu zapasowego, ale jest obsługiwany przez <xref:System.Windows.Markup.MemberDefinition> klasę. W strumieniu węzła XAML `x:Member` element jest reprezentowany jako element członkowski o nazwie `Member` , z przestrzeni nazw XAML języka XAML. Składowa `Member` zawiera atrybuty zadeklarowane przez znacznik.

Znaczenie `Name` i `Type` nie są przypisane na poziomie usług .NET XAML. Są one przechowywane w początkowym strumieniu węzła XAML jako wartości ciągów, które mają być interpretowane później w ramach reguł, które mogą zostać nałożone przez określone struktury. Znaczenie może być wyrównane do nazwy XAML i typu XAML lub może być prawidłowe tylko w systemie typu zapasowego, w zależności od implementacji.

Aby obsłużyć praktyczne użycie `x:Members` jako środek do określenia definicji elementów członkowskich w znaczniku, elementy członkowskie muszą być skojarzone z klasą, która może być modyfikowana. Zamierzony model `x:Members` istnieje jako element członkowski typu, który określa `x:Class` . Jednak mechanizm kojarzenia typów i elementów członkowskich lub do tworzenia dynamicznych definicji elementów członkowskich nie jest obsługiwany na poziomie usług .NET XAML. Jest to pozostało do pojedynczych platform, które mają modele aplikacji, które obsługują definicje elementów członkowskich z języka XAML. Zazwyczaj akcje kompilacji programu MSBUILD, które umożliwiają adiustację i kompilowanie kodu XAML, i integrowanie go z kodem związanym lub wytwarzaniem czystych zestawów z języka XAML, które są niezbędne do obsługi tej funkcji.

## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property Windows Workflow Foundation

W przypadku Windows Workflow Foundation `x:Property` definiuje elementy członkowskie działania niestandardowego składające się całkowicie z języka XAML lub zdefiniowane w języku XAML dynamiczne elementy członkowskie dla projektanta działań z kodem. `x:Class` musi również być określony w elemencie głównym produkcji XAML. Nie jest to wymagane na poziomie usług .NET XAML, ale jest wymagane, gdy produkcja XAML jest ładowana przez akcje kompilacji MSBUILD, które obsługują działania niestandardowe i Windows Workflow Foundation XAML. Windows Workflow Foundation nie używa czystej nazwy typu XAML jako zamierzonej wartości `x:Property` `Type` atrybutu, a zamiast tego używa konwencji, która nie jest udokumentowana w tym miejscu. Aby uzyskać więcej informacji, zobacz [dynamiczne tworzenie](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).
