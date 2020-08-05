---
ms.openlocfilehash: 1cb6e953aa57c72ee6a2665c521bada10e0786cf
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455759"
---
### <a name="utf-7-code-paths-are-obsolete"></a>Ścieżki kodu UTF-7 są przestarzałe

Kodowanie UTF-7 nie jest już używane między aplikacjami, a wiele specyfikacji już [zabroni jego użycia](https://security.stackexchange.com/a/68609/3573) w wymianie. Jest to również sporadycznie [używane jako wektor ataku](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) w aplikacjach, które nie przewidziano do napotkania danych zakodowanych w formacie UTF-7. Firma Microsoft ostrzega przed użyciem, <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> ponieważ nie zapewnia wykrywania błędów.

W związku z tym <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> Właściwość i <xref:System.Text.UTF7Encoding.%23ctor%2A> konstruktory są obecnie przestarzałe. Ponadto <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> nie można już określić `UTF-7` .

#### <a name="change-description"></a>Zmień opis

Wcześniej można było utworzyć wystąpienie kodowania UTF-7 za pomocą <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> interfejsów API. Na przykład:

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

Ponadto wystąpienie, które reprezentuje kodowanie UTF-7, zostało wyliczone przez <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> metodę, która wylicza wszystkie <xref:System.Text.Encoding> wystąpienia zarejestrowane w systemie.

Począwszy od platformy .NET 5,0, <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> Właściwość i <xref:System.Text.UTF7Encoding.%23ctor%2A> konstruktory są przestarzałe i generują ostrzeżenia `SYSLIB0001` (lub w wersjach zapoznawczych `MSLIB0001` ). Aby jednak zmniejszyć liczbę ostrzeżeń odbieranych przez wywołujących podczas korzystania z <xref:System.Text.UTF7Encoding> klasy, <xref:System.Text.UTF7Encoding> sam typ nie jest oznaczony jako przestarzały.

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

Ponadto <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> metody traktują nazwę kodowania `utf-7` i stronę kodową `65000` jako `unknown` . Traktując kodowanie jako `unknown` powodujące metodę, aby zgłosić <xref:System.ArgumentException> .

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

Na koniec <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> Metoda nie zawiera kodowania UTF-7 w <xref:System.Text.EncodingInfo> zwracanej tablicy. Kodowanie jest wykluczone, ponieważ nie można utworzyć jego wystąpienia.

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

#### <a name="reason-for-change"></a>Przyczyna zmiany

Wiele aplikacji wywołuje `Encoding.GetEncoding("encoding-name")` wartość nazwy kodowania, która jest dostarczana przez niezaufane źródło. Na przykład klient sieci Web lub serwer może pobrać `charset` część `Content-Type` nagłówka i przekazać wartość bezpośrednio do programu `Encoding.GetEncoding` bez sprawdzania poprawności. Może to umożliwić określenie złośliwego punktu końcowego `Content-Type: ...; charset=utf-7` , co może spowodować niezachowanie aplikacji odbiorczej.

Ponadto wyłączenie ścieżek kodu UTF-7 pozwala zoptymalizować kompilatory, takie jak te używane przez Blazor, aby usunąć te ścieżki kodu w całości z aplikacji. W związku z tym skompilowane aplikacje działają wydajniej i zajmuje mniej miejsca na dysku.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

W większości przypadków nie trzeba podejmować żadnych działań. Jednak w przypadku aplikacji, które wcześniej aktywowali ścieżki kodu związane z kodowaniem UTF-7, należy wziąć pod uwagę poniższe wskazówki.

- Jeśli aplikacja wywołuje <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> nieznane nazwy kodowania dostarczone przez niezaufane Źródło:

  Zamiast tego należy porównać nazwy kodowania z konfigurowalną listą dozwolonych. Lista dozwolonych konfigurowalnych powinna zawierać co najmniej wartość "UTF-8". W zależności od klientów i wymagań prawnych może być również konieczne zezwolenie na kodowanie specyficzne dla regionu, takie jak "GB18030".

  Jeśli lista dozwolonych nie zostanie wdrożona, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> program zwróci wszystkie <xref:System.Text.Encoding> wbudowane w system lub zarejestrowane za pośrednictwem niestandardowej <xref:System.Text.EncodingProvider> . Przeprowadź inspekcję wymagań usługi, aby sprawdzić, czy jest to odpowiednie zachowanie. Kodowanie UTF-7 nadal jest domyślnie wyłączone, chyba że aplikacja ponownie włączy przełącznik zgodności wymieniony w dalszej części tego artykułu.

- W przypadku korzystania z programu <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> lub <xref:System.Text.UTF7Encoding> w ramach własnego protokołu lub formatu pliku:

  Przełącz się do korzystania z <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> lub <xref:System.Text.UTF8Encoding> . UTF-8 jest standardem branżowym i jest szeroko obsługiwany w różnych językach, systemach operacyjnych i w czasie wykonywania. Użycie UTF-8 ułatwia przyszłą konserwację kodu i sprawia, że jest to bardziej obsługiwane w pozostałej części ekosystemu.

- Jeśli porównujesz <xref:System.Text.Encoding> wystąpienie z <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> :

  Zamiast tego należy rozważyć przeprowadzenie sprawdzenia względem dobrze znanej strony kodowej UTF-7, która jest `65000` . Porównując względem strony kodowej, można uniknąć ostrzeżenia, a także obsłużyć niektóre przypadki brzegowe, na przykład jeśli ktoś wywołał `new UTF7Encoding()` lub podklasy typ.

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

- Jeśli musisz użyć <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> lub <xref:System.Text.UTF7Encoding> :

  Możesz pominąć `SYSLIB0001` ostrzeżenie w kodzie lub w pliku *. csproj* projektu.

  ```csharp
  #pragma warning disable SYSLIB0001 // Disable the warning.
  Encoding enc = Encoding.UTF7;
  #pragma warning restore SYSLIB0001 // Re-enable the warning.
  ```

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > Pomijanie `SYSLIB0001` powoduje wyłączenie tylko <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> <xref:System.Text.UTF7Encoding> ostrzeżeń i obsoletion. Nie wyłącza żadnych innych ostrzeżeń ani nie zmienia zachowania interfejsów API, takich jak <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> .

- Jeśli musisz obsługiwać `Encoding.GetEncoding("utf-7", ...)` :

  Można ponownie włączyć obsługę tego programu za pośrednictwem przełącznika zgodności. Ten przełącznik zgodności można określić w pliku *. csproj* aplikacji lub w [pliku konfiguracji czasu wykonywania](../../../../docs/core/run-time-config/index.md), jak pokazano w poniższych przykładach.

  W pliku *. csproj* aplikacji:

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  W *runtimeconfig.template.jsaplikacji w* pliku:

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > W przypadku ponownego włączenia obsługi UTF-7 należy przeprowadzić przegląd zabezpieczeń kodu, który wywołuje <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> .

#### <a name="category"></a>Kategoria

- Podstawowe biblioteki platformy .NET
- Zabezpieczenia

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Text.Encoding.UTF7?displayProperty=fullName>
- <xref:System.Text.UTF7Encoding.%23ctor>
- <xref:System.Text.UTF7Encoding.%23ctor(System.Boolean)>
- <xref:System.Text.Encoding.GetEncoding(System.Int32)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncodings?displayProperty=fullName>

<!--

#### Affected APIs

- `System.Text.Encoding.UTF7`
- `System.Text.UTF7Encoding.#ctor`
- `System.Text.UTF7Encoding.#ctor(System.Boolean)`
- `System.Text.Encoding.GetEncoding(System.Int32)`
- `System.Text.Encoding.GetEncoding(System.String)`
- `System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncodings`

-->
