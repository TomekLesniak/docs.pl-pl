---
title: Platformy docelowe w projektach w stylu zestawu SDK — .NET
description: Dowiedz się więcej na temat platform docelowych dla aplikacji i bibliotek platformy .NET.
ms.date: 11/06/2020
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: a37634bc9f4cbee5f7901fcb085d3801a7452573
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441048"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Platformy docelowe w projektach w stylu zestawu SDK

Gdy docelowa jest struktura w aplikacji lub bibliotece, określasz zestaw interfejsów API, które mają być dostępne dla aplikacji lub biblioteki. Należy określić platformę docelową w pliku projektu przy użyciu monikera platformy docelowej (TFM).

Aplikacja lub biblioteka może być ukierunkowana na wersję [.NET Standard](net-standard.md). Wersje .NET Standard reprezentują standardowe zestawy interfejsów API we wszystkich implementacjach platformy .NET. Na przykład biblioteka może kierować do .NET Standard 1,6 i uzyskać dostęp do interfejsów API, które działają w ramach platformy .NET Core i .NET Framework przy użyciu tej samej bazy kodu.

W celu uzyskania dostępu do interfejsów API specyficznych dla implementacji aplikacja lub biblioteka może być również ukierunkowana na określoną implementację platformy .NET. Na przykład aplikacja, która jest przeznaczona dla platformy Xamarin. iOS (na przykład `Xamarin.iOS10` ), ma dostęp do otok interfejsu API systemu iOS dostarczonych przez platformę iOS 10 lub aplikację, która jest przeznaczona dla platforma uniwersalna systemu Windows (platformy UWP `uap10.0` ), ma dostęp do interfejsów API, które kompilują dla urządzeń z systemem Windows 10.

W przypadku niektórych platform docelowych, takich jak .NET Framework, interfejsy API są definiowane przez zestawy, które są instalowane przez platformę w systemie i mogą zawierać interfejsy API platformy aplikacji (na przykład ASP.NET).

W przypadku platform docelowych opartych na pakietach (na przykład .NET 5, .NET Core i .NET Standard) interfejsy API są definiowane przez pakiety zawarte w aplikacji lub bibliotece. Pakiet *jest* pakietem NuGet, który nie ma własnej zawartości, ale jest listą zależności (inne pakiety). Platforma docelowa oparta na pakiecie NuGet niejawnie określa pakiet, który odwołuje się do wszystkich pakietów, które razem tworzą strukturę.

## <a name="latest-versions"></a>Najnowsze wersje

Poniższa tabela zawiera definicje najpopularniejszych platform docelowych, ich odwołań oraz wersji [.NET Standard](net-standard.md) implementujących te platformy. Te wersje platformy docelowej są najnowszymi stabilnymi wersjami. Wersje wstępne nie są wyświetlane. Moniker platformy docelowej (TFM) to standardowy format tokenu służący do określania docelowej platformy aplikacji lub biblioteki platformy .NET.

| Platforma docelowa      | Najnowsza <br/> stabilna wersja | Moniker platformy docelowej (TFM) | Realizowane <br/> Wersja .NET Standard |
| :-: | :-: | :-: | :-: |
| .NET 5                | 5,0                         | NET 5.0                         | Nie dotyczy                                     |
| .NET Standard         | 2.1                         | Standard 2.1                 | Nie dotyczy                                     |
| .NET Core             | 3,1                         | netcoreapp 3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2,0                                     |

## <a name="supported-target-frameworks"></a>Obsługiwane platformy docelowe

Platforma docelowa jest zwykle przywoływana przez TFM. W poniższej tabeli przedstawiono Platformy docelowe obsługiwane przez zestaw .NET SDK i klienta NuGet. Odpowiedniki są wyświetlane w nawiasach kwadratowych. Na przykład, `win81` jest odpowiednikiem TFM do `netcore451` .

| Struktura docelowa           | TFM |
| -------------------------- | --- |
| .NET 5 (i .NET Core)     | netcoreapp 1.0<br>netcoreapp 1.1<br>netcoreapp2.0<br>netcoreapp 2.1<br>netcoreapp 2.2<br>netcoreapp 3.0<br>netcoreapp 3.1<br>NET 5.0 * |
| .NET Standard              | Standard 1.0<br>Standard 1.1<br>Standard 1.2<br>Standard 1.3<br>Standardowa 1.4<br>Standard 1.5<br>Standard 1.6<br>Standard 2.0<br>Standard 2.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Windows Store              | Rdzeń [netcore45]<br>netcore45 [win] [Win8]<br>netcore451 [Win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | WP [WP7]<br>wp7<br>wp75<br>WP8<br>wp81<br>wpa81 |
| Platforma uniwersalna systemu Windows | UAP [UAP 10.0]<br>UAP 10.0 [Win10] [netcore50] |

\* Program .NET 5,0 i nowsze TFMs obejmują różnice specyficzne dla systemu operacyjnego. Aby uzyskać więcej informacji, zapoznaj się z sekcją [TFMs dla systemu operacyjnego .NET 5](#net-5-os-specific-tfms).

### <a name="net-5-os-specific-tfms"></a>TFMs specyficzne dla systemu operacyjnego .NET 5

Dla każdego programu .NET 5,0 i nowszych TFM, na przykład, istnieją `net5.0` TFM Wariacje obejmujące powiązania specyficzne dla systemu operacyjnego. Te różnice przedstawiono w poniższej tabeli.

| Format specyficzny dla systemu operacyjnego | Przykład        |
|--------------------|----------------|
| \<base-tfm>— Android | NET 5.0 — Android |
| \<base-tfm>— iOS     | NET 5.0 — iOS     |
| \<base-tfm>-MacOS   | NET 5.0 — MacOS   |
| \<base-tfm>-systemu tvOS    | NET 5.0 — systemu tvOS    |
| \<base-tfm>-systemu watchOS | NET 5.0 — systemu watchOS |
| \<base-tfm>— System Windows | NET 5.0 — Windows |

`net5.0`TFM obejmuje tylko technologie, które działają na wielu platformach. Określenie TFM specyficznych dla systemu operacyjnego sprawia, że interfejsy API, które są specyficzne dla systemu operacyjnego dostępnego dla aplikacji, na przykład powiązania Windows Forms lub systemu iOS. TFMs specyficzne dla systemu operacyjnego dziedziczą również każdy interfejs API dostępny dla `net5.0` TFM.

Aby aplikacja była przenośna na różnych platformach, można kierować wiele TFMs specyficznych dla systemu operacyjnego i dodać do nich funkcję ochrony platformy wokół wywołań interfejsu API właściwych dla systemu operacyjnego przy użyciu `#if` dyrektyw preprocesora.

W poniższej tabeli przedstawiono zgodność programu .NET 5 TFMs z TFMs dla wcześniejszych wersji platformy .NET.

| TFM             | Zgodne z                                            | Uwagi |
|-----------------|------------------------------------------------------------|-|
| NET 5.0          | net1.. 4 (z ostrzeżeniem NU1701)<br />netcoreapp1.. 3,1 (ostrzeżenie, gdy występuje odwołanie do WinForms lub WPF)<br />netstandard1.. 2,1 | |
| NET 5.0 — Android  | Xamarin. Android (plus wszystkie inne dziedziczone z `net5.0` ) | |
| NET 5.0 — iOS      | Xamarin. iOS (plus wszystkie inne dziedziczone z `net5.0` ) | |
| NET 5.0 — MacOS    | Xamarin. Mac (plus wszystkie inne dziedziczone z `net5.0` ) | |
| NET 5.0 — systemu tvOS     | Xamarin. systemu tvOS (plus wszystkie inne dziedziczone z `net5.0` ) | |
| NET 5.0 — systemu watchOS  | Xamarin. systemu watchOS (plus wszystkie inne dziedziczone z `net5.0` ) | |
| NET 5.0 — Windows  | netcoreapp1.. 3,1 (plus wszystkie inne dziedziczone z `net5.0` ) | Obejmuje funkcje WinForms, WPF i platformy UWP.<br />Aby uzyskać więcej informacji, zobacz [wywoływanie środowisko wykonawcze systemu Windows interfejsów API w aplikacjach klasycznych](/windows/apps/desktop/modernize/desktop-to-uwp-enhance). |

#### <a name="suggested-targets"></a>Sugerowane cele

Skorzystaj z poniższych wskazówek, aby określić, które TFM mają być używane w aplikacji:

- Aplikacje, które są przenośne na wiele platform, powinny mieć miejsce docelowe `net5.0` . Obejmuje to większość bibliotek, ale również ASP.NET Core i Entity Framework.

- Biblioteki specyficzne dla platformy powinny dotyczyć wersji specyficznych dla platformy. Na przykład, WinForms i projekty WPF powinny być ukierunkowane `net5.0-windows` .

- Modele aplikacji dla wielu platform (narzędzia Xamarin Forms, ASP.NET Core) i pakiety mostkowe (Xamarin Essentials) powinny mieć co najmniej cel `net5.0` , ale mogą również kierować się dodatkowymi wersjami specyficznymi dla platformy w celu uzyskania bardziej szczegółowych interfejsów API lub funkcji.

#### <a name="os-version-in-tfms"></a>Wersja systemu operacyjnego w TFMs

Możesz również określić opcjonalną wersję systemu operacyjnego na końcu TFM, na przykład, `net5.0-ios13.0` która wskazuje, jakie interfejsy API są dostępne dla aplikacji. (Zestaw SDK programu .NET 5 zostanie zaktualizowany w celu uwzględnienia obsługi nowszych wersji systemu operacyjnego w miarę ich wydania). Aby uzyskać dostęp do nowo wydanych interfejsów API, zwiększ wersję systemu operacyjnego w TFM. Nadal możesz zapewnić zgodność aplikacji z wcześniejszymi wersjami systemu operacyjnego (i dodać osłony dla wywołań do nowszych wersji interfejsów API) przez dodanie `SupportedOSPlatformVersion` elementu do pliku projektu. `SupportedOSPlatformVersion`Element wskazuje minimalną wersję systemu operacyjnego wymaganą do uruchomienia aplikacji.

Na przykład poniższy fragment pliku projektu określa, że interfejsy API systemu iOS 14 są dostępne dla aplikacji, ale można je uruchomić na komputerach z systemem iOS 13 lub nowszym.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net5.0-ios14.0</TargetFramework>
    <SupportedOSPlatformVersion>13.0</SupportedOSPlatformVersion> (minimum os platform version)
  </PropertyGroup>

  ...

</Project>
```

## <a name="how-to-specify-a-target-framework"></a>Jak określić platformę docelową

Struktury docelowe są określone w pliku projektu. W przypadku określenia pojedynczej platformy docelowej należy użyć [elementu TargetFramework](../core/project-sdk/msbuild-props.md#targetframework). Poniższy plik projektu aplikacji konsolowej pokazuje, w jaki sposób należy kierować platformą .NET 5,0:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

W przypadku określania wielu platform docelowych można warunkowo odwoływać się do zestawów dla każdej platformy docelowej. W kodzie można warunkowo kompilować do tych zestawów przy użyciu symboli preprocesora z logiką *if-then-else* .

Następujący projekt biblioteki odwołuje się do interfejsów API .NET Standard ( `netstandard1.4` ) i .NET Framework ( `net40` i `net45` ). Użyj [elementu TargetFrameworks](../core/project-sdk/msbuild-props.md#targetframeworks) w liczbie mnogiej z wieloma platformami docelowymi. `Condition`Atrybuty obejmują pakiety specyficzne dla implementacji, gdy biblioteka jest skompilowana dla dwóch .NET Framework TFMs:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

W ramach biblioteki lub aplikacji napiszesz kod warunkowy przy użyciu [dyrektyw preprocesora](../csharp/language-reference/preprocessor-directives/preprocessor-if.md) , aby kompilować dla każdej platformy docelowej:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

System kompilacji ma świadomość symboli preprocesora reprezentujących Platformy docelowe, które są wyświetlane w tabeli [obsługiwane wersje platformy docelowej](#supported-target-frameworks) w przypadku korzystania z projektów w stylu zestawu SDK. Przy użyciu symbolu, który reprezentuje .NET Standard, .NET Core lub .NET 5 TFM, Zastąp kropki i łączniki znakiem podkreślenia i Zmień małe litery na wielkie litery (na przykład symbol " `netstandard1.4` is" `NETSTANDARD1_4` ).

Kompletna lista symboli preprocesora dla platform docelowych .NET to:

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Przestarzałe Platformy docelowe

Poniższe Platformy docelowe są przestarzałe. Pakiety, które są przeznaczone dla tych platform docelowych, powinny migrować do wskazanych zamian.

| Przestarzałe TFM                                                                             | Funkcja zastępująca |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>środowiska DNX<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | UAP 10.0     |
| kupione                                                                                        | netcore45   |
| Win8                                                                                       | netcore45   |
| Win81                                                                                      | netcore451  |
| Win10                                                                                      | UAP 10.0     |
| środowiska                                                                                      | netcore45   |

## <a name="see-also"></a>Zobacz też

- [Nazwy platformy docelowej w programie .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [Tworzenie bibliotek za pomocą narzędzi międzyplatformowych](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [Obsługa wersji platformy .NET Core](../core/versions/index.md)
- [repozytorium dotnet/standardowe usługi GitHub](https://github.com/dotnet/standard)
- [Repozytorium GitHub narzędzi NuGet](https://github.com/joelverhagen/NuGetTools)
- [Profile struktury w programie .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
- [Analizator zgodności platformy](analyzers/platform-compat-analyzer.md)
