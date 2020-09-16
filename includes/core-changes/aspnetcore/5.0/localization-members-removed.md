---
ms.openlocfilehash: 41e80a9dbcfa2a857e0b52674ef0724a542458a0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539523"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a>Lokalizacja: Usunięto klasę ResourceManagerWithCultureStringLocalizer i element członkowski interfejsu WithCulture

Klasa [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) i Metoda [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) zostały usunięte w programie .NET 5,0 Preview 1.

W przypadku kontekstu zobacz [ASPNET/anonse # 346](https://github.com/aspnet/Announcements/issues/346) i [dotnet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324). Aby uzyskać więcej dyskusji na temat tej zmiany, zobacz [dotnet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 1

#### <a name="old-behavior"></a>Stare zachowanie

`ResourceManagerWithCultureStringLocalizer`Klasa i `ResourceManagerStringLocalizer.WithCulture` Metoda są [przestarzałe w programie .NET Core 3,0 w wersji zapoznawczej 3 i nowszych](../../../../docs/core/compatibility/2.2-3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).

#### <a name="new-behavior"></a>Nowe zachowanie

`ResourceManagerWithCultureStringLocalizer`Klasa i Metoda zostały `ResourceManagerStringLocalizer.WithCulture` usunięte w programie .NET 5,0 Preview 1. Aby uzyskać spis zmian wprowadzonych w programie, zobacz żądanie ściągnięcia w programie [dotnet/Extensions # 2562](https://github.com/dotnet/extensions/pull/2562/files).

#### <a name="reason-for-change"></a>Przyczyna zmiany

Metody [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) i [ResourceManagerStringLocalizer. WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) często są źródłami pomyłek dla użytkowników lokalizacji. Pomyłka była szczególnie wysoka podczas tworzenia niestandardowej <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementacji. Ta klasa i Metoda zapewniają konsumentom wrażenie, że `IStringLocalizer` wystąpienie jest oczekiwane na "dla poszczególnych zasobów". W rzeczywistości wystąpienie powinno mieć tylko wartość "dla zasobu". W czasie wykonywania <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> Właściwość określa język, który ma być używany.

#### <a name="recommended-action"></a>Zalecana akcja

Zatrzymaj korzystanie z `ResourceManagerWithCultureStringLocalizer` klasy i `ResourceManagerStringLocalizer.WithCulture` metody.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
