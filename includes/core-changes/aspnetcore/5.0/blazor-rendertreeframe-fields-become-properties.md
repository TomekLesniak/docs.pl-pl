---
ms.openlocfilehash: edff55d540f08e8a9fd4d0687aaf6bd963ee3a84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539531"
---
### <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a>Blazor: RenderTreeFrame pola publiczne ReadOnly mają właściwości

W ASP.NET Core 3,0 i 3,1, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> Struktura uwidacznia różne `readonly public` pola, w tym <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType> , <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> i innych. W ASP.NET Core 5,0 RC1 i nowszych wersjach wszystkie `readonly public` pola zostały zmienione na `readonly public` właściwości.

Ta zmiana nie wpłynie na wielu deweloperów, ponieważ:

* Każda aplikacja lub biblioteka, która po prostu używa `.razor` plików (lub nawet wywołań ręcznych <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> ) w celu zdefiniowania jej składników, nie będzie bezpośrednio odwoływać się do tego typu.
* `RenderTreeFrame`Sam typ jest traktowany jako szczegóły implementacji, nie jest przeznaczony do użycia poza platformą. ASP.NET Core 3,0 i nowsze zawierają Analizator, który wystawia ostrzeżenia kompilatora, jeśli typ jest używany bezpośrednio.
* Nawet w przypadku bezpośredniego odwoływania `RenderTreeFrame` się do tej zmiany są rozdzieleniem danych binarnych, ale nie ze źródłem. Oznacza to, że istniejący kod źródłowy będzie kompilować i działać prawidłowo. Wystąpi problem tylko w przypadku kompilowania z platformą .NET Core 3. x, a następnie uruchamiania tych plików binarnych dla architektury .NET 5,0 RC1 i nowszych.

Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25727](https://github.com/dotnet/aspnetcore/issues/25727).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC1

#### <a name="old-behavior"></a>Stare zachowanie

Publiczne składowe w programie `RenderTreeFrame` są zdefiniowane jako pola. Na przykład `renderTreeFrame.Sequence` i `renderTreeFrame.ElementName`.

#### <a name="new-behavior"></a>Nowe zachowanie

Publiczne składowe w `RenderTreeFrame` programie są zdefiniowane jako właściwości o takich samych nazwach jak poprzednio. Na przykład `renderTreeFrame.Sequence` i `renderTreeFrame.ElementName`.

Jeśli starszy wstępnie skompilowany kod nie został ponownie skompilowany od tej zmiany, może zgłosić wyjątek podobny do *MissingFieldException: nie znaleziono pola: "Microsoft. AspNetCore. Components. RenderTree. RenderTreeFrame. FrameType"*.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana była niezbędna do zaimplementowania ulepszeń wydajności o dużym wpływie na renderowanie składników Blazor w ASP.NET Core 5,0. Te same poziomy bezpieczeństwa i hermetyzacji są obsługiwane.

#### <a name="recommended-action"></a>Zalecana akcja

Ta zmiana nie dotyczy większości deweloperów Blazor. Zmiana jest prawdopodobnie niekorzystnie wpływać na bibliotekę i autorów pakietów, ale tylko w rzadkich przypadkach. W przypadku tworzenia:

* Aplikacja i używanie ASP.NET Core 3. x lub uaktualniania do 5,0 RC1 lub nowszego, nie musisz zmieniać własnego kodu. Jeśli jednak zależą od biblioteki uaktualnionej do konta dla tej zmiany, należy zaktualizować ją do nowszej wersji tej biblioteki.
* Biblioteka i chce obsługiwać tylko ASP.NET Core 5,0 RC1 lub nowszy, nie jest wymagana żadna akcja. Upewnij się, że plik projektu deklaruje `<TargetFramework>` wartość `net5.0` lub nowszą wersję.
* Biblioteka i chcesz obsługiwać oba ASP.NET Core 3. x *i* 5,0, ustal, czy kod odczytuje wszelkich `RenderTreeFrame` członków. Na przykład Ocena `someRenderTreeFrame.FrameType` .
  * Większość bibliotek nie odczytuje `RenderTreeFrame` elementów członkowskich, w tym bibliotek zawierających `.razor` składniki. W takim przypadku nie jest wymagana żadna akcja.
  * Jeśli jednak Twoja biblioteka działa, musisz mieć wiele obiektów docelowych, aby obsługiwać jednocześnie `netstandard2.1` i `net5.0` . Zastosuj następujące zmiany w pliku projektu:
    * Zamień istniejący `<TargetFramework>` element na `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>` .
    * Użyj `Microsoft.AspNetCore.Components` odwołania do pakietu warunkowego do konta dla obu wersji, które mają być obsługiwane. Na przykład:

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

Aby uzyskać więcej wyjaśnień, zobacz to [porównanie pokazuje, jak @jsakamoto już uaktualniono `Toolbelt.Blazor.HeadElement` bibliotekę](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
