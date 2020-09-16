---
title: Generator EDM (EdmGen.exe)
ms.date: 03/30/2017
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
ms.openlocfilehash: da5b87fa76cbc8e44f6ed60b047e5a185c2aa603
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542558"
---
# <a name="edm-generator-edmgenexe"></a>Generator EDM (EdmGen.exe)

EdmGen.exe to narzędzie wiersza polecenia służące do pracy z modelem Entity Framework i plikami mapowania. Za pomocą narzędzia EdmGen.exe można wykonać następujące czynności:

- Nawiązywanie połączenia ze źródłem danych przy użyciu dostawcy danych .NET Framework określonego przez źródło danych i generowanie modelu koncepcyjnego (. csdl), modelu magazynu (. ssdl) i plików mapowania (. MSL), które są używane przez Entity Framework. Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

- Zweryfikuj istniejący model. Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by sprawdzić poprawność modelu i plików mapowania](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md).

- Generuj plik kodu C# lub Visual Basic, który zawiera klasy obiektów wygenerowane na podstawie pliku modelu koncepcyjnego (. csdl). Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować kod warstwy obiektu](how-to-use-edmgen-exe-to-generate-object-layer-code.md).

- Wygeneruj plik kodu C# lub Visual Basic, który zawiera wstępnie wygenerowane widoki dla istniejącego modelu. Aby uzyskać więcej informacji, [jak: wstępnie wygenerować widoki w celu zwiększenia wydajności zapytań](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).

Narzędzie EdmGen.exe jest zainstalowane w katalogu .NET Framework. W wielu przypadkach znajduje się to w C:\windows\Microsoft.NET\Framework\v4.0. W przypadku systemów 64-bitowych ten program znajduje się w C:\windows\Microsoft.NET\Framework64\v4.0. Możesz również uzyskać dostęp do narzędzia EdmGen.exe z poziomu wiersza polecenia programu Visual Studio (kliknij przycisk **Start**, wskaż **Wszystkie programy**, wskaż **Microsoft Visual Studio 2010**, wskaż **Visual Studio Tools**, a następnie kliknij przycisk **wiersz polecenia programu Visual Studio 2010**).

## <a name="syntax"></a>Składnia

```console
EdmGen /mode:choice [options]
```

## <a name="mode"></a>Tryb

W przypadku korzystania z narzędzia EdmGen.exe należy określić jeden z następujących trybów.

|Tryb|Opis|
|----------|-----------------|
|`/mode:ValidateArtifacts`|Sprawdza poprawność plików CSDL, SSDL i MSL oraz wyświetla błędy lub ostrzeżenia.<br /><br /> Ta opcja wymaga co najmniej jednego `/inssdl` `/incsdl` argumentu lub. Jeśli `/inmsl` jest określona, `/inssdl` `/incsdl` wymagane są również argumenty i.|
|`/mode:FullGeneration`|Program używa informacji o połączeniu z bazą danych określonych w `/connectionstring` opcji i generuje pliki CSDL, SSDL, MSL, warstwy obiektów i wyświetlaj.<br /><br /> Ta opcja wymaga argumentu oraz argumentu,,,,,, `/connectionstring` `/project` `/outssdl` `/outcsdl` `/outmsdl` `/outobjectlayer` `/outviews` `/namespace` i `/entitycontainer` argumentów.|
|`/mode:FromSSDLGeneration`|Generuje pliki CSDL i MSL, kod źródłowy i widoki z określonego pliku SSDL.<br /><br /> Ta opcja wymaga `/inssdl` argumentu oraz `/project` argumentu lub `/outcsdl` argumentów,,,, `/outmsl` `/outobjectlayer` `/outviews` `/namespace,` i `/entitycontainer` .|
|`/mode:EntityClassGeneration`|Tworzy plik kodu źródłowego, który zawiera klasy wygenerowane z pliku CSDL.<br /><br /> Ta opcja wymaga `/incsdl` argumentu oraz `/project` argumentu lub `/outobjectlayer` argumentu. `/language`Argument jest opcjonalny.|
|`/mode:ViewGeneration`|Tworzy plik kodu źródłowego, który zawiera widoki wygenerowane na podstawie plików. csdl,. ssdl i. MSL.<br /><br /> Ta opcja wymaga `/inssdl` argumentów, `/incsdl` `/inmsl,` i `/project` `/outviews` . `/language`Argument jest opcjonalny.|

## <a name="options"></a>Opcje

|Opcja|Opis|
|------------|-----------------|
|`/p[roject]:`\<string>|Określa nazwę projektu do użycia. Nazwa projektu jest używana jako wartość domyślna dla ustawienia przestrzeń nazw, nazwa modelu i pliki mapowania, nazwa pliku źródłowego obiektu i nazwa pliku źródłowego generacji widoku. Nazwa kontenera jednostek jest ustawiona na \<project> kontekst.|
|`/prov[ider]:`\<string>|Nazwa dostawcy danych .NET Framework, który ma zostać użyty do wygenerowania pliku modelu magazynu (SSDL). Domyślny dostawca to .NET Framework Dostawca danych dla SQL Server ( <xref:System.Data.SqlClient?displayProperty=nameWithType> ).|
|`/c[onnectionstring]:`\<connection string>|Określa ciąg, który jest używany do nawiązywania połączenia ze źródłem danych.|
|`/incsdl:`\<file>|Określa plik CSDL lub katalog, w którym znajdują się pliki. csdl. Ten argument można określić wiele razy, aby można było określić kilka katalogów lub plików CSDL. Określenie wielu katalogów może być przydatne w przypadku generowania klas ( `/mode:EntityClassGeneration` ) lub widoków ( `/mode:ViewGeneration` ), gdy model koncepcyjny jest podzielony na kilka plików. Może to być przydatne, jeśli chcesz sprawdzić poprawność wielu modeli ( `/mode:ValidateArtifacts` ).|
|`/refcsdl:`\<file>|Określa dodatkowy plik. csdl lub pliki używane do rozwiązywania wszelkich odwołań w źródłowym pliku CSDL. (Plik. CSDL jest plikiem, który jest określony przez `/incsdl` opcję). `/refcsdl`Plik zawiera typy, od których zależy plik source. csdl. Ten argument można określić wiele razy.|
|`/inmsl:`\<file>|Określa plik. MSL lub katalog, w którym znajdują się pliki. MSL. Ten argument można określić wiele razy, aby można było określić kilka katalogów lub plików MSL. Określenie wielu katalogów może być przydatne w przypadku generowania widoków ( `/mode:ViewGeneration` ), gdy model koncepcyjny jest podzielony na kilka plików. Może to być przydatne, jeśli chcesz sprawdzić poprawność wielu modeli ( `/mode:ValidateArtifacts` ).|
|`/inssdl:`\<file>|Określa plik SSDL lub katalog, w którym znajduje się plik. SSDL. Ten argument można określić wiele razy, aby można było określić kilka katalogów lub plików SSDL. Może to być przydatne, jeśli chcesz sprawdzić poprawność wielu modeli `(/mode:ValidateArtifacts)` .|
|`/outcsdl:`\<file>|Określa nazwę pliku. csdl, który zostanie utworzony.|
|`/outmsl:`\<file>|Określa nazwę pliku. MSL, który zostanie utworzony.|
|`/outssdl:`\<file>|Określa nazwę pliku SSDL, który zostanie utworzony.|
|`/outobjectlayer:`\<file>|Określa nazwę pliku kodu źródłowego, który zawiera obiekty wygenerowane z pliku CSDL.|
|`/outviews:`\<file>|Określa nazwę pliku kodu źródłowego zawierającego widoki, które zostały wygenerowane.|
|`/language:`[VB&#124;CSharp]|Określa język generowanych plików kodu źródłowego. Język domyślny języka C#.|
|`/namespace:`\<string>|Określa przestrzeń nazw modelu, która ma być używana. Przestrzeń nazw jest ustawiana w pliku CSDL podczas uruchamiania `/mode:FullGeneration` lub `/mode:FromSSDLGeneration` . Przestrzeń nazw nie jest używana podczas uruchamiania `/mode:EntityClassGeneration` .|
|`/entitycontainer:`\<string>|Określa nazwę, która ma zostać zastosowana do `<EntityContainer>` elementu w wygenerowanym modelu i plików mapowania.|
|`/pl[uralize]`|Stosuje reguły języka angielskiego dla liczb pojedynczej i pluralizmu do `Entity` , `EntitySet` i `NavigationProperty` nazwy w modelu koncepcyjnym. Ta opcja spowoduje wykonanie następujących akcji:<br /><br /> — Wprowadź wszystkie `EntityType` nazwy pojedyncze.<br />— Wprowadź wszystkie `EntitySet` nazwy w liczbie mnogiej.<br />-Dla każdej, `NavigationProperty` która zwraca co najwyżej jedną jednostkę, wprowadź nazwę pojedynczą.<br />-Dla każdego, `NavigationProperty` które zwraca więcej niż jedną jednostkę, wprowadź nazwę w liczbie mnogiej.|
|`/SuppressForeignKeyProperties or /nofk`|Zapobiega ujawnianiu kolumn klucza obcego jako właściwości skalarnych w typach jednostek w modelu koncepcyjnym.|
|`/help` lub `?`|Wyświetla składnię polecenia i opcje narzędzia.|
|`/nologo`|Pomija wyświetlanie komunikatu o prawach autorskich.|
|`/targetversion:` \<string>|Wersja .NET Framework, która będzie używana do kompilowania wygenerowanego kodu. Obsługiwane wersje to 4 i 4,5. Wartość domyślna to 4.|

## <a name="in-this-section"></a>W tej sekcji

[Instrukcje: Generowanie modelu i mapowania plików za pomocą EdmGen.exe](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

[Instrukcje: Używanie EdmGen.exe, aby wygenerować kod warstwy obiektu](how-to-use-edmgen-exe-to-generate-object-layer-code.md)

[Instrukcje: Walidacja modelu i mapowania plików za pomocą EdmGen.exe](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)

## <a name="see-also"></a>Zobacz także

- [Narzędzia Entity Data Model ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Entity Data Model](../entity-data-model.md)
- [Specyfikacje CSDL, SSDL i MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
