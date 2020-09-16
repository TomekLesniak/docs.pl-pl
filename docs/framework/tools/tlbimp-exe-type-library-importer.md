---
title: Tlbimp.exe (Importer biblioteki typów)
description: Użyj Tlbimp.exe, importera biblioteki typów. To narzędzie konwertuje definicje typów Znalezione w bibliotece typów modelu COM do równoważnych definicji w zestawie CLR.
ms.date: 03/30/2017
helpviewer_keywords:
- type libraries [.NET Framework], importing
- importing type library
- Tlbimp.exe
- type definition conversion
- Type Library Importer
- type libraries
- converting type definitions
ms.assetid: ec0a8d63-11b3-4acd-b398-da1e37e97382
ms.openlocfilehash: 4c2cddd78e14d1ae0b04bab07b57fe0ce0f627ca
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543371"
---
# <a name="tlbimpexe-type-library-importer"></a>Tlbimp.exe (Importer biblioteki typów)
Importer biblioteki typów konwertuje definicje typów znalezione w bibliotece typów modelu COM do równoważnych definicji w zestawie środowiska uruchomieniowego języka wspólnego. Wyjściem programu Tlbimp.exe jest plik binarny (zestaw) zawierający metadane środowiska wykonawczego dla typów zdefiniowanych w oryginalnej biblioteki typów. Ten plik można przeanalizować za pomocą narzędzi, takich jak [Ildasm.exe](ildasm-exe-il-disassembler.md).  
  
 To narzędzie jest instalowane automatycznie z programem Visual Studio. Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio (lub wiersza polecenia programu Visual Studio w systemie Windows 7). Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md).  
  
 W wierszu polecenia wpisz następujące polecenie:  
  
## <a name="syntax"></a>Składnia  
  
```console  
tlbimp tlbFile [options]  
```  
  
## <a name="parameters"></a>Parametry  
  
|Argument|Opis|  
|--------------|-----------------|  
|*tlbFile*|Nazwa dowolnego pliku zawierającego bibliotekę typów modelu COM.|  
  
|Opcja|Opis|  
|------------|-----------------|  
|**/asmversion:** *versionNumber*|Określa numer wersji zestawu do produkcji. Określ *versionNumber* w formacie *główna. pomocnicza. kompilacja. poprawka*.|  
|**/Company:**`companyinformation`|Dodaje informacje o firmie do wyjściowego zestawu.|  
|**/Copyright:**`copyrightinformation`|Dodaje informacje o prawach autorskich do wyjściowego zestawu. Te informacje można wyświetlić w oknie dialogowym **właściwości pliku** dla zestawu.|  
|**/delaysign**|Określa, że Tlbimp.exe ma podpisać wynikowy zestaw silną nazwą przy użyciu opóźnionego podpisywania. Należy określić tę opcję z opcją **/keycontainer:**, **/keyfile:** lub **/publickey:** . Aby uzyskać więcej informacji o opóźnionym procesie podpisywania, zobacz [opóźnienie podpisywania zestawu](../../standard/assembly/delay-sign.md).|  
|**/Help**|Wyświetla składnię polecenia i opcje narzędzia.|  
|**/keycontainer:** *ContainerName*|Podpisuje zestaw w postaci silnej nazwy przy użyciu pary kluczy publicznych/prywatnych znalezionych w kontenerze kluczy określonym przez *ContainerName*.|  
|**/keyfile:** *filename*|Podpisuje zestaw w postaci silnej nazwy przy użyciu oficjalnej pary kluczy publiczny/prywatny wydawcy, która została znaleziona w *pliku filename*.|  
|**/Machine:**`machinetype`|Tworzy to zestaw przeznaczony dla określonego typu komputera (procesor). Obsługiwane typy maszyn: x86, x64, Itanium i Agnostic.|  
|**/Namespace:** *przestrzeń nazw*|Określa przestrzeń nazw, w którym ma zostać wyprodukowany zestaw.|  
|**/noclassmembers**|Zapobiega dodawaniu przez Tlbimp.exe składowych do klasy. Pozwala to uniknąć możliwości <xref:System.TypeLoadException> .|  
|**/nologo**|Pomija wyświetlanie transparentu startowego firmy Microsoft.|  
|**/out:** *filename*|Określa nazwę wyjściowego pliku zestawu i przestrzeń nazw, w którym mają być zapisywane definicje metadanych. Opcja **/out** nie ma wpływu na przestrzeń nazw zestawu, jeśli biblioteka typów określa atrybut niestandardowy języka definicji interfejsu (IDL), który jawnie kontroluje przestrzeń nazw zestawu. Jeśli ta opcja nie zostanie określona, Tlbimp.exe zapisuje metadane do pliku o takiej samej nazwie jak rzeczywista biblioteka zdefiniowana w pliku wejściowym i przypisuje mu rozszerzenie dll. Jeśli plik wyjściowy ma taką samą nazwę jak plik wejściowy, narzędzie wygeneruje błąd, aby zapobiec zastąpieniu biblioteki typów.|  
|**/primary**|Tworzy podstawowy zestaw międzyoperacyjny dla określonej biblioteki typu. Do zestawu są dodawane informacje wskazujące, że wydawca biblioteki typów wyprodukował zestaw. Określając podstawowy zestaw międzyoperacyjny, różnicuje się zestawu wydawcy od innych zestawów utworzonych z biblioteki typów za pomocą Tlbimp.exe. Opcji **/Primary** należy używać tylko wtedy, gdy jesteś wydawcą biblioteki typów importowanej przy użyciu Tlbimp.exe. Należy pamiętać, że należy podpisać podstawowy zestaw międzyoperacyjny o [silnej nazwie](../../standard/assembly/strong-named.md). Aby uzyskać więcej informacji, zobacz [podstawowe zestawy międzyoperacyjności](/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).|  
|**/Product:**`productinformation`|Dodaje informacje o produkcie do wyjściowego zestawu. Te informacje można wyświetlić w oknie dialogowym **właściwości pliku** dla zestawu.|  
|**/ProductVersion:**`productversioninformation`|Dodaje informacje o wersji produktu do wyjściowego zestawu. Nie ma żadnych ograniczeń dotyczących formatu. Te informacje można wyświetlić w oknie dialogowym **właściwości pliku** dla zestawu.|  
|**/publickey:** *filename*|Określa plik zawierający klucz publiczny używany do podpisywania wynikowego zestawu. W przypadku określenia opcji **/keyfile:** lub **/keycontainer:** zamiast **/publickey:**, Tlbimp.exe generuje klucz publiczny z pary kluczy publiczny/prywatny dostarczonej z **/keyfile:** lub **/keycontainer:**. **/Publickey:** opcja obsługuje klucz testu i opóźnienia podpisywania. Plik jest w formacie generowanym przez Sn.exe. Aby uzyskać więcej informacji, zobacz opcję **-p** Sn.exe w [narzędziu silnej nazwy (Sn.exe)](sn-exe-strong-name-tool.md).|  
|**/Reference:** *filename*|Określa plik zestawu używać do rozpoznawania odwołań do typów zdefiniowanych poza bieżącą biblioteką typów. Jeśli nie określisz opcji **/Reference** , Tlbimp.exe automatycznie rekursywnie importuje każdą zewnętrzną bibliotekę typów, do której jest importowana biblioteka typów. W przypadku określenia opcji **/Reference** Narzędzie próbuje rozpoznać zewnętrzne typy w przywoływanych zestawach przed zaimportowaniem innych bibliotek typów.|  
|**/Silence:**`warningnumber`|Pomija wyświetlanie określonego ostrzeżenia. Tej opcji nie można używać z **/Silent**.|  
|**/Silent**|Pomija wyświetlanie komunikatów o sukcesie. Tej opcji nie można używać z **/Silence**.|  
|**/strictref**|Nie importuje biblioteki typów, jeśli narzędzie nie może rozpoznać wszystkich odwołań w bieżącym zestawie, zestawów określonych przy użyciu opcji **/Reference** lub zarejestrowanych podstawowych zestawów międzyoperacyjnych (zestawów PIA).|  
|**/strictref:nopia**|Analogicznie jak **/strictref**, ale ignoruje zestawów Pia.|  
|**/sysarray**|Określa narzędzie do importowania stylu COM SafeArray jako <xref:System.Array> Typ zarządzany.|  
|**/tlbreference:** *filename*|Określa plik biblioteki typów do użycia do rozpoznawania odwołań do biblioteki typu bez konsultacji z rejestrem.<br /><br /> Należy zauważyć, że ta opcja nie będzie ładować niektórych starszych formatów bibliotek typów.  Jednak nadal można ładować starsze formaty bibliotek typów niejawnie za pośrednictwem rejestru lub bieżącego katalogu.|  
|**/Trademark:**`trademarkinformation`|Dodaje informacje o znaku towarowym do wyjściowego zestawu. Te informacje można wyświetlić w oknie dialogowym **właściwości pliku** dla zestawu.|  
|**/Transform:** *transformname*|Przekształca metadane określone przez parametr *transformname* .<br /><br /> Określ **dispret** dla parametru *transformname* , aby przekształcić parametry [out, retval] metod w interfejsach tylko do wysyłania (dispinterfaces) do wartości zwracanych.<br /><br /> Aby uzyskać więcej informacji dotyczących tej opcji, zobacz przykłady w dalszej części tego tematu.|  
|**/unsafe**|Produkuje interfejsy bez sprawdzania zabezpieczeń platformy .NET Framework. Wywołanie metody, która jest widoczna w ten sposób, może stanowić zagrożenie bezpieczeństwa. Nie należy używać tej opcji, chyba że masz świadomość ryzyka związanego z ujawnieniem takiego kodu.|  
|**/verbose**|Określa tryb pełnej informacji; wyświetla dodatkowe informacje o importowanej bibliotece typów.|  
|**/VariantBoolFieldToBool**|Konwertuje `VARIANT_BOOL` pola w strukturach na <xref:System.Boolean> .|  
|**/?**|Wyświetla składnię polecenia i opcje narzędzia.|  
  
> [!NOTE]
> W opcjach wiersza polecenia programu Tlbimp.exe nie jest rozróżniana wielkość liter i opcje mogą być podawane w dowolnej kolejności. Wystarczy określić część nazwy opcji umożliwiającą jej jednoznaczną identyfikację. W związku z tym **/n** jest równoważne z **/nologo** i **/OU:** *outfile.dll* jest równoważne z **/out:** *outfile.dll*.  
  
## <a name="remarks"></a>Uwagi  
 Tlbimp.exe za jednym razem wykonuje konwersje na całej biblioteki typów. Nie można użyć narzędzia do generowania informacji o typie dla podzbioru typów zdefiniowanych w obrębie jednej biblioteki typów.  
  
 Często jest to przydatne lub konieczne, aby można było przypisać [silne nazwy](../../standard/assembly/strong-named.md) do zestawów. W związku z tym Tlbimp.exe zawiera opcje umożliwiającą podawanie informacji niezbędnych do generowania zestawów o silnych nazwach. Zarówno **/keyfile:** , jak i **/keycontainer:** opcje podpisywać zestawy o silnych nazwach. Dlatego logiczne jest podawanie tylko jedną z tych opcji na raz.  
  
 Można określić wiele zestawów odwołań za pomocą opcji **/Reference** wiele razy.

 Ze względu na sposób, w jaki Tlbimp.exe generuje zestawy, nie jest możliwe przekierowanie zestawu do innej `mscorlib` wersji. Na przykład jeśli chcesz wygenerować zestaw przeznaczony dla .NET Framework 2,0, należy użyć Tlbimp.exe dostarczonego z zestawem SDK .NET Framework 2.0/3.0/3.5. Aby można było zastosować .NET Framework 4. x, należy użyć Tlbimp.exe dostarczonej z zestawem SDK .NET Framework 4. x.

 Identyfikator zasobu można opcjonalnie dołączyć do pliku biblioteki typów podczas importowania biblioteki typów z modułu zawierającego wiele bibliotek typów. Tlbimp.exe jest w stanie zlokalizować ten plik tylko wtedy, gdy znajduje się w bieżącym katalogu lub jeśli określisz pełną ścieżkę. Zobacz przykład dalej w tym temacie.  
  
## <a name="examples"></a>Przykłady  
 Następujące polecenie generuje zestaw o tej samej nazwie co biblioteka typów znaleziona w `myTest.tlb` i z rozszerzeniem. dll.  
  
```console  
tlbimp myTest.tlb
```  
  
 Następujące polecenie generuje zestaw o nazwie `myTest.dll` .  
  
```console  
tlbimp  myTest.tlb  /out:myTest.dll  
```  
  
 Następujące polecenie generuje zestaw o tej samej nazwie co biblioteka typów określona przez `MyModule.dll\1` i z rozszerzeniem. dll. `MyModule.dll\1` musi znajdować się w bieżącym katalogu.  
  
```console  
tlbimp MyModule.dll\1  
```  
  
 Następujące polecenie generuje zestaw o nazwie `myTestLib.dll` dla biblioteki typów `TestLib.dll` . Opcja **/Transform: dispret** przekształca wszystkie parametry [out, retval] metod na dispinterfaces w bibliotece typów na wartości zwracane w bibliotece zarządzanej.  
  
```console  
tlbimp TestLib.dll /transform:dispret /out:myTestLib.dll  
```  
  
 `TestLib.dll`W powyższym przykładzie biblioteka typów zawiera metodę dispinterface o nazwie `SomeMethod` , która zwraca wartość void i ma parametr [out, retval]. Poniższy kod jest sygnaturą metody biblioteki typów wejściowych dla `SomeMethod` programu w programie `TestLib.dll` .  
  
```cpp  
void SomeMethod([out, retval] VARIANT_BOOL*);  
```  
  
 Określenie opcji **/Transform: dispret** powoduje Tlbimp.exe przekształcenia `[out, retval]` parametru `SomeMethod` do `bool` wartości zwracanej. Poniżej znajduje się sygnatura metody, która Tlbimp.exe wytwarza `SomeMethod` wartość w bibliotece zarządzanej, `myTestLib.dll` gdy została określona opcja **/Transform: dispret** .  
  
```csharp  
bool SomeMethod();  
```  
  
 Jeśli używasz Tlbimp.exe do tworzenia biblioteki zarządzanej programu `TestLib.dll` bez określania **/Transform: dispret**, narzędzie generuje następujący podpis metody `SomeMethod` w bibliotece zarządzanej `myTestLib.dll` .  
  
```csharp  
void SomeMethod(out bool x);  
```  
  
## <a name="see-also"></a>Zobacz także

- [Narzędzia](index.md)
- [Tlbexp.exe (Eksporter biblioteki typów)](tlbexp-exe-type-library-exporter.md)
- [Importowanie biblioteki typów jako zestawu](../interop/importing-a-type-library-as-an-assembly.md)
- [Podsumowanie dotyczące konwersji biblioteki typów na zestaw](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Ildasm.exe (IL dezasembler)](ildasm-exe-il-disassembler.md)
- [Sn.exe (Narzędzie silnej nazwy)](sn-exe-strong-name-tool.md)
- [Zestawy o silnych nazwach](../../standard/assembly/strong-named.md)
- [Atrybuty importowania bibliotek typów do zestawów międzyoperacyjnych](/previous-versions/dotnet/netframework-4.0/y6a7ak23(v=vs.100))
- [Wiersze poleceń](developer-command-prompt-for-vs.md)
