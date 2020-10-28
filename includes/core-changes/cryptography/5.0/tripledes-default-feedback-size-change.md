---
ms.openlocfilehash: 2599e1f65720c25695f1fb5cfa39cabb842efc1d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888624"
---
### <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a>Domyślna wartość FeedbackSize dla wystąpień utworzonych przez TripleDES. Create zmieniony

Wartość domyślna <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> właściwości <xref:System.Security.Cryptography.TripleDES> wystąpienia zwróconego z <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> został zmieniony z 64 na 8, aby ułatwić migrację z .NET Framework. Ta właściwość, chyba że jest używana bezpośrednio w kodzie wywołującym, jest używana tylko wtedy, gdy <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> Właściwość jest <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> .

Obsługa <xref:System.Security.Cryptography.CipherMode.CFB> tego trybu została najpierw dodana do platformy .NET dla wersji 5,0 RC1, dlatego ta zmiana powinna mieć wpływ tylko na aplikacje .net 5,0 RC1 i .net 5,0 RC2.

#### <a name="change-description"></a>Zmień opis

W programie .NET Core i starszych wersjach wstępnych programu .NET 5,0 `TripleDES.Create().FeedbackSize` ma wartość domyślną 64. Począwszy od wersji RTM programu .NET 5,0, `TripleDES.Create().FeedbackSize` ma wartość domyślną 8.

#### <a name="reason-for-change"></a>Przyczyna zmiany

W .NET Framework <xref:System.Security.Cryptography.TripleDES> Klasa bazowa domyślnie przyjmuje wartość <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> do 64, ale <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> Klasa zastępuje domyślnie 8. Gdy <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> Właściwość została wprowadzona do programu .NET Core w wersji 2,0, takie samo zachowanie zostało zachowane. Jednak w .NET Framework <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> zwraca wystąpienie <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> , dlatego wartość domyślna z fabryki algorytmów wynosi 8. W przypadku platformy .NET Core i .NET 5 + fabryka algorytmów zwraca niepubliczną implementację, która w razie potrzeby miała wartość domyślną 64.

Zmiana <xref:System.Security.Cryptography.TripleDES> klasy implementacji " <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> value to 8" umożliwia aplikacjom napisanym dla .NET Framework, które określiły tryb szyfru <xref:System.Security.Cryptography.CipherMode.CFB> , ale niejawnie przypisanie <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> właściwości, w celu kontynuowania działania w programie .NET 5.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RTM

#### <a name="recommended-action"></a>Zalecana akcja

Aplikacje, które szyfrują lub odszyfrowują dane w wersji RC1 lub RC2 programu .NET 5,0, to CFB64, gdy spełnione są następujące warunki:

- Z <xref:System.Security.Cryptography.TripleDES> wystąpieniem <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> .
- Używanie wartości domyślnej dla <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> .
- Z <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> właściwością ustawioną na <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> .

Aby zachować to zachowanie, przypisz <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> Właściwość do `64` .

Nie wszystkie `TripleDES` implementacje używają tego samego ustawienia domyślnego dla programu <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> . Zaleca się, aby w przypadku użycia <xref:System.Security.Cryptography.CipherMode.CFB> trybu szyfru w <xref:System.Security.Cryptography.TripleDES> wystąpieniach zawsze jawnie przypisać <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> wartość właściwości.

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

#### <a name="category"></a>Kategoria

- Kryptografia

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

-->
