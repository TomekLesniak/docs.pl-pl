---
title: 'Nieprzerwana zmiana: MVC: ObjectModelValidator wywołuje nowe Przeciążenie ValidationVisitor. Validate'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej MVC: ObjectModelValidator wywołuje nowe Przeciążenie ValidationVisitor. Validate'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b28c357f51291a4f73889d5d413a983f79e09daf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761680"
---
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a>MVC: ObjectModelValidator wywołuje nowe Przeciążenie ValidationVisitor. Validate

W ASP.NET Core 5,0 <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> zostało dodane Przeciążenie elementu. Nowe Przeciążenie akceptuje wystąpienie modelu najwyższego poziomu, które zawiera właściwości:

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> wywołuje to nowe Przeciążenie, `ValidationVisitor` Aby przeprowadzić walidację. To nowe Przeciążenie jest przydatne, jeśli biblioteka walidacji jest zintegrowana z systemem ASP.NET Core MVC modelem walidacji.

Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 26020](https://github.com/dotnet/aspnetcore/issues/26020).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="old-behavior"></a>Stare zachowanie

`ObjectModelValidator` wywołuje następujące Przeciążenie podczas walidacji modelu:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a>Nowe zachowanie

`ObjectModelValidator` wywołuje następujące Przeciążenie podczas walidacji modelu:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona w celu obsługi modułów walidacji, takich jak <xref:System.ComponentModel.DataAnnotations.CompareAttribute> , które opierają się na inspekcji innych właściwości.

## <a name="recommended-action"></a>Zalecana akcja

Struktury sprawdzania poprawności, które polegają na `ObjectModelValidator` wywołaniu istniejącego przeciążenia, `ValidationVisitor` muszą przesłaniać nową metodę, gdy jest przeznaczony dla programu .NET 5,0 lub nowszego:

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
