---
ms.openlocfilehash: 9544b65f31772d0f4cee918528a73171fec4de99
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032053"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Zmień wartość domyślną UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> ma wartość domyślną `false` w programie .NET Core. W .NET Framework wartość domyślna to `true` .

#### <a name="change-description"></a>Zmień opis

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> umożliwia uruchamianie aplikacji bezpośrednio, na przykład przy użyciu kodu, takiego jak `Process.Start("mspaint.exe")` uruchomienie programu Paint. Umożliwia ona również pośrednio uruchomienie skojarzonej aplikacji, jeśli <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> jest ustawiona na `true` . Na .NET Framework wartość domyślna <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `true` , co oznacza, że kod taki jak `Process.Start("mytextfile.txt")` zostałby uruchomiony Notatnik, jeśli masz skojarzone pliki *txt* z tym edytorem. Aby zapobiec pośredniemu uruchamianiu aplikacji na .NET Framework, musisz jawnie ustawić <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> wartość `false` . W przypadku platformy .NET Core wartość domyślna <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false` . Oznacza to, że domyślnie skojarzone aplikacje nie są uruchamiane podczas wywoływania `Process.Start` .

Ta zmiana została wprowadzona w programie .NET Core ze względu na wydajność. Zwykle <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> jest używany do bezpośredniego uruchamiania aplikacji. Bezpośrednie uruchamianie aplikacji nie wymaga ponoszenia powłoki systemu Windows i wiąże się z powiązanymi kosztami wydajności. Aby ten przypadek domyślny był szybszy, program .NET Core zmienia wartość domyślną <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> na `false` . Jeśli potrzebujesz, możesz zrezygnować z wolniejszej ścieżki.

#### <a name="version-introduced"></a>Wprowadzona wersja

2.1

> [!NOTE]
> We wcześniejszych wersjach programu .NET Core `UseShellExecute` nie została zaimplementowana dla systemu Windows.

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli aplikacja korzysta ze starego zachowania, należy wywołać polecenie <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> z <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> ustawioną `true` na wartość dla <xref:System.Diagnostics.ProcessStartInfo> obiektu.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
