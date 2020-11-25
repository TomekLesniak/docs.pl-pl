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
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="e63cb-103">MVC: ObjectModelValidator wywołuje nowe Przeciążenie ValidationVisitor. Validate</span><span class="sxs-lookup"><span data-stu-id="e63cb-103">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="e63cb-104">W ASP.NET Core 5,0 <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> zostało dodane Przeciążenie elementu.</span><span class="sxs-lookup"><span data-stu-id="e63cb-104">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="e63cb-105">Nowe Przeciążenie akceptuje wystąpienie modelu najwyższego poziomu, które zawiera właściwości:</span><span class="sxs-lookup"><span data-stu-id="e63cb-105">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="e63cb-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> wywołuje to nowe Przeciążenie, `ValidationVisitor` Aby przeprowadzić walidację.</span><span class="sxs-lookup"><span data-stu-id="e63cb-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="e63cb-107">To nowe Przeciążenie jest przydatne, jeśli biblioteka walidacji jest zintegrowana z systemem ASP.NET Core MVC modelem walidacji.</span><span class="sxs-lookup"><span data-stu-id="e63cb-107">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="e63cb-108">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 26020](https://github.com/dotnet/aspnetcore/issues/26020).</span><span class="sxs-lookup"><span data-stu-id="e63cb-108">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e63cb-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="e63cb-109">Version introduced</span></span>

<span data-ttu-id="e63cb-110">5,0</span><span class="sxs-lookup"><span data-stu-id="e63cb-110">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="e63cb-111">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="e63cb-111">Old behavior</span></span>

<span data-ttu-id="e63cb-112">`ObjectModelValidator` wywołuje następujące Przeciążenie podczas walidacji modelu:</span><span class="sxs-lookup"><span data-stu-id="e63cb-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a><span data-ttu-id="e63cb-113">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="e63cb-113">New behavior</span></span>

<span data-ttu-id="e63cb-114">`ObjectModelValidator` wywołuje następujące Przeciążenie podczas walidacji modelu:</span><span class="sxs-lookup"><span data-stu-id="e63cb-114">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a><span data-ttu-id="e63cb-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="e63cb-115">Reason for change</span></span>

<span data-ttu-id="e63cb-116">Ta zmiana została wprowadzona w celu obsługi modułów walidacji, takich jak <xref:System.ComponentModel.DataAnnotations.CompareAttribute> , które opierają się na inspekcji innych właściwości.</span><span class="sxs-lookup"><span data-stu-id="e63cb-116">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e63cb-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="e63cb-117">Recommended action</span></span>

<span data-ttu-id="e63cb-118">Struktury sprawdzania poprawności, które polegają na `ObjectModelValidator` wywołaniu istniejącego przeciążenia, `ValidationVisitor` muszą przesłaniać nową metodę, gdy jest przeznaczony dla programu .NET 5,0 lub nowszego:</span><span class="sxs-lookup"><span data-stu-id="e63cb-118">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a><span data-ttu-id="e63cb-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="e63cb-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
