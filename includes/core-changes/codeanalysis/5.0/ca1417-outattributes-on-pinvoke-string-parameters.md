---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065170"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a>CA1417: atrybut unattribute dla parametru String dla elementu P/Invoke

Reguła analizatora kodu platformy .NET [CA1417](/visualstudio/code-quality/ca1417) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla wszystkich definicji metody [wywołania platformy (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) , w których <xref:System.String> parametr jest przesyłany przez wartość i oznaczony przez <xref:System.Runtime.InteropServices.OutAttribute> .

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA1417](/visualstudio/code-quality/ca1417). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

Reguły CA1417 flagi [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) definicje metod, gdzie <xref:System.String> parametr jest oznaczony <xref:System.Runtime.InteropServices.OutAttribute> atrybutem i jest przenoszona przez wartość. Na przykład:

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

Środowisko uruchomieniowe platformy .NET utrzymuje tabelę, nazywaną pulą InterNIC, która zawiera pojedyncze odwołanie do każdego unikatowego ciągu literału w programie. Jeśli ciąg z stażystem oznaczony jako z <xref:System.Runtime.InteropServices.OutAttribute> jest przenoszona przez wartość do metody P/Invoke, środowisko uruchomieniowe może być niestabilne. Aby uzyskać więcej informacji na temat informowania o ciągach, zobacz uwagi dla <xref:System.String.Intern(System.String)?displayProperty=nameWithType> .

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

- Jeśli musisz zorganizować zmodyfikowane dane ciągu z powrotem do obiektu wywołującego, Przekaż ciąg przez odwołanie.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- Jeśli nie musisz zorganizować zmodyfikowanych danych ciągu z powrotem do obiektu wywołującego, po prostu usuń <xref:System.Runtime.InteropServices.OutAttribute> .

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  Aby uzyskać więcej informacji, zobacz [CA1417](/visualstudio/code-quality/ca1417).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

Analiza kodu

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
