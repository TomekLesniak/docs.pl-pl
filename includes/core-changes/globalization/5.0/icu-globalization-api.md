---
ms.openlocfilehash: 74c3d3247912dcd638a9379d54e682967c5e400b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302720"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>Interfejsy API globalizacji korzystają z bibliotek ICU w systemie Windows

.NET 5,0 i nowsze wersje używają [międzynarodowych składników dla bibliotek Unicode (ICU)](http://site.icu-project.org/home) do obsługi funkcji globalizacji w przypadku uruchamiania w systemie Windows 10 maja 2019 Update lub nowszym.

#### <a name="change-description"></a>Zmień opis

Wcześniej biblioteki platformy .NET używały interfejsów API [obsługi języka narodowego (NLS)](/windows/win32/intl/national-language-support) dla funkcji globalizacji. Na przykład funkcje NLS były używane do pobierania danych kultury, takich jak wzorce formatu daty i godziny, porównywania ciągów i wykonywania wielkich liter w odpowiedniej kulturze.

Począwszy od platformy .NET 5,0, jeśli aplikacja działa w systemie Windows 2019 10 z aktualizacją Update lub nowszym, biblioteki platformy .NET używają interfejsów API [ICU](http://site.icu-project.org/home) globalizacji. System Windows 10 maja 2019 Update i nowsze wersje są dostarczane z natywną biblioteką ICU. Jeśli środowisko uruchomieniowe platformy .NET nie może załadować ICU, zamiast tego używa środowiska NLS.

Ta zmiana została wprowadzona z dwóch powodów:

- Aplikacje mają takie samo zachowanie globalizacji między platformami, w tym Linux, macOS i Windows.
- Aplikacje mogą kontrolować zachowanie globalizacji przy użyciu niestandardowych bibliotek ICU.

#### <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0 (wersja zapoznawcza 4)

#### <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja. Jeśli jednak chcesz kontynuować korzystanie z interfejsów API globalizacji NLS, możesz ustawić [przełącznik czasu wykonywania](../../../../docs/core/run-time-config/globalization.md#nls) w celu przywrócenia tego zachowania. Aby uzyskać więcej informacji na temat dostępnych przełączników, zobacz artykuł [globalizacja i ICU platformy .NET](/dotnet/standard/globalization-localization/globalization-icu) .

#### <a name="category"></a>Kategoria

Globalizacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- Większość typów w <xref:System.Globalization?displayProperty=fullName> przestrzeni nazw

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
