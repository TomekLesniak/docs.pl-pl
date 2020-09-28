---
ms.openlocfilehash: 4a7616d2ffaabab5279342ebc1082c93a174a52d
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406179"
---
### <a name="ca1416-platform-compatibility"></a>CA1416: zgodność platformy

Reguła analizatora kodu platformy .NET [CA1416](/visualstudio/code-quality/ca1416) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla wywołań interfejsów API specyficznych dla platformy z lokacji wywołań, które nie weryfikują systemu operacyjnego.

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA1416](/visualstudio/code-quality/ca1416). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji. Reguła CA1416 informuje użytkownika, gdy korzystasz z interfejsów API specyficznych dla platformy z miejsc, w których kontekst platformy nie został zweryfikowany.

[CA1416](/visualstudio/code-quality/ca1416)reguły, Analizator zgodności platformy, umożliwia dostęp do innych funkcji, które są nowe w programie .NET 5,0. W programie .NET 5,0 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> wprowadzono <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> funkcję i, która pozwala określić platformy, na których interfejs API *jest* lub *nie* jest obsługiwany. W przypadku braku tych atrybutów przyjmuje się, że interfejs API jest obsługiwany na wszystkich platformach. Te atrybuty zostały zastosowane do interfejsów API specyficznych dla platformy w podstawowych bibliotekach platformy .NET.

W projektach przeznaczonych dla platform, dla których używane interfejsy API są niedostępne, reguła [CA1416](/visualstudio/code-quality/ca1416) flaguje każde wywołanie interfejsu API specyficzne dla platformy, w którym nie zweryfikowano kontekstu platformy. Większość interfejsów API, które są teraz uzupełnione <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> atrybutami i generują <xref:System.PlatformNotSupportedException> wyjątki, gdy są wywoływane w nieobsługiwanym systemie operacyjnym. Teraz, gdy te interfejsy API są oznaczone jako specyficzne dla platformy, reguła [CA1416a](/visualstudio/code-quality/ca1416) pomaga zapobiegać <xref:System.PlatformNotSupportedException> wyjątkom w czasie wykonywania, DODAJĄC sprawdzenia systemu operacyjnego do witryn wywołań.

#### <a name="examples"></a>Przykłady

- <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType>Metoda jest obsługiwana tylko w systemie Windows i jest dekoracyjna `[SupportedOSPlatform("windows")]` . Poniższy kod generuje ostrzeżenie CA1416 w czasie kompilacji, jeśli [obiekt docelowy](../../../../docs/standard/frameworks.md) projektu `net5.0` (ale nie `net5.0-windows` ). W przypadku akcji, które można wykonać, aby uniknąć tego ostrzeżenia, zobacz [zalecane działanie](#recommended-action).

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType>Metoda nie jest obsługiwana w przeglądarce i jest dekoracyjna `[UnsupportedOSPlatform("browser")]` . Poniższy kod generuje ostrzeżenie CA1416 w czasie kompilacji, jeśli projekt obsługuje platformę przeglądarki.

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - Projekty Blazor webassembly i projekty biblioteki klas Razor obejmują obsługę przeglądarki automatycznie.
  > - Aby ręcznie dodać przeglądarkę jako obsługiwaną platformę dla projektu, Dodaj następujący wpis do pliku projektu:
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC1

#### <a name="recommended-action"></a>Zalecana akcja

Upewnij się, że interfejsy API specyficzne dla platformy są wywoływane tylko wtedy, gdy kod jest uruchomiony na odpowiedniej platformie. `Is<Platform>` <xref:System.OperatingSystem?displayProperty=nameWithType> <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> Przed wywołaniem interfejsu API specyficznego dla platformy można sprawdzić bieżący system operacyjny przy użyciu jednej z metod w klasie.

Można użyć jednej z `Is<Platform>` metod w warunku `if` instrukcji:

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

Lub, jeśli nie chcesz obciążać dodatkowej `if` instrukcji w czasie wykonywania, <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> zamiast tego wywołaj:

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

Jeśli tworzysz bibliotekę, możesz oznaczyć interfejs API jako specyficzny dla platformy. W takim przypadku obciążenie związane z sprawdzaniem wymagań znajduje się w programie wywołującym. Można oznaczyć konkretne metody lub typy lub cały zestaw.

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

Jeśli nie chcesz naprawić wszystkich witryn wywołań, możesz wybrać jedną z następujących opcji, aby pominąć ostrzeżenie:

- Aby pominąć regułę CA1416, można to zrobić za pomocą `#pragma` flagi kompilatora lub z flagą [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) lub ustawiając [ważność reguły](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) do `none` w pliku. editorconfig.

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

- Analiza kodu
- Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Platforma systemu Windows:

- Wszystkie interfejsy API wymienione w <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md> .
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

Na platformie Blazor webassembly:

- Wszystkie interfejsy API wymienione w <https://github.com/dotnet/runtime/issues/41087> .

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a>Zobacz także

- [CA1416: Weryfikowanie zgodności platformy](/visualstudio/code-quality/ca1416)
- [Analizator interfejsów API platformy .NET](../../../../docs/standard/analyzers/api-analyzer.md)
