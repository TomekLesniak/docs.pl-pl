---
title: Regasm.exe (Narzędzie rejestracji zestawów)
description: Użyj Regasm.exe, narzędzia rejestracji zestawu. Odczytywanie metadanych zestawu i Dodawanie wymaganych wpisów do rejestru, co umożliwia klientom COM tworzenie klas platformy .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- Assembly Registration tool
- assemblies [.NET Framework], registering
- Regasm.exe
- registering assemblies
ms.assetid: e190e342-36ef-4651-a0b4-0e8c2c0281cb
ms.openlocfilehash: a3af6a0fbc7c9c695e18448da285977f04fd72ef
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517259"
---
# <a name="regasmexe-assembly-registration-tool"></a>Regasm.exe (Narzędzie rejestracji zestawów)

Narzędzie do rejestracji zestawów czyta metadane w zestawie i dodaje niezbędne wpisy do rejestru, co umożliwia klientom COM przejrzyste tworzenie klas .NET Framework. Po zarejestrowaniu klasy dowolny klient COM może jej używać tak, jakby była klasą modelu COM. Klasa jest rejestrowana tylko raz, kiedy zestaw jest instalowany. Nie można utworzyć wystąpień klas w zestawie z COM, dopóki nie zostaną one faktycznie zarejestrowane.

Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio. Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md).

W wierszu polecenia wpisz następujące polecenie:

## <a name="syntax"></a>Składnia

```console
regasm assemblyFile [options]
```

## <a name="parameters"></a>Parametry

|Parametr|Opis|
|---------------|-----------------|
|*assemblyFile*|Zestaw do rejestracji w modelu COM.|

|Opcja|Opis|
|------------|-----------------|
|**/codebase**|Tworzy wpis Codebase w rejestrze. Wpis codebase określa ścieżkę pliku dla zestawu, który nie jest zainstalowany w globalnej pamięci podręcznej zestawów. Nie określaj tej opcji, jeśli następnie zostanie zainstalowany zestaw, który jest rejestrowany w globalnej pamięci podręcznej zestawów. Argument *assemblyFile* określony za pomocą opcji **/codebase** musi być [zestawem o silnej nazwie](../../standard/assembly/strong-named.md).|
|**/registered**|Określa, że narzędzie będzie odnosić się tylko do bibliotek typów, które zostały już zarejestrowane.|
|**/asmpath: katalog**|Określa katalog zawierający odwołania do zestawów. Musi być używana z opcją **/regfile** .|
|**/nologo**|Pomija wyświetlanie transparentu startowego firmy Microsoft.|
|**/regfile** [**:** *regfile*]|Generuje określony plik reg dla zestawu zawierający potrzebne wpisy rejestru. Zaznaczenie tej opcji nie powoduje zmiany rejestru. Tej opcji nie można używać z opcjami **/u** i **/TLB** .|
|**/Silent** lub **/s**|Pomija wyświetlanie komunikatów o sukcesie.|
|**/TLB** [**:** *typeLibFile*]|Generuje bibliotekę typów z określonego zestawu zawierającego definicje dostępnych typów zdefiniowanych w zestawie.|
|**/Unregister** lub **/u**|Wyrejestrowuje klasy możliwe do utworzenia znajdujące się w *assemblyFile*. Pominięcie tej opcji powoduje, że Regasm.exe rejestruje utworzone klasy w zestawie.|
|**/verbose**|Określa tryb pełny; Wyświetla listę wszystkich zestawów, do których istnieją odwołania, dla których należy wygenerować bibliotekę typów, gdy zostanie określona z opcją **/TLB** .|
|**/?** lub **/help**|Wyświetla składnię polecenia i opcje narzędzia.|

> [!NOTE]
> W opcjach wiersza polecenia programu Regasm.exe nie jest rozróżniana wielkość liter. Wystarczy podać część nazwy opcji umożliwiającą jej jednoznaczną identyfikację. Na przykład **/n** jest równoważne **/nologo** i **/t:** *plik. tlb* jest równoważne **/tlb:** *plik. tlb*.

## <a name="remarks"></a>Uwagi

Można użyć opcji **/regfile** , aby wygenerować plik reg zawierający wpisy rejestru zamiast wprowadzać zmiany bezpośrednio do rejestru. Można zaktualizować rejestr na komputerze przez zaimportowanie pliku reg za pomocą narzędzia Edytora rejestru (Regedit.exe). Plik reg nie zawiera żadnych aktualizacji rejestru, które mogą być wykonywane przez zdefiniowane przez użytkownika funkcje rejestrowania. Opcja **/regfile** emituje tylko wpisy rejestru dla zarządzanych klas. Ta opcja nie emituje wpisów dla `TypeLibID` s lub `InterfaceID` s.

Po określeniu opcji **/tlb** Regasm.exe generuje i rejestruje bibliotekę typów opisującą typy znajdujące się w zestawie. Regasm.exe umieszcza wygenerowane biblioteki typów w bieżącym katalogu roboczym lub katalogu określonym dla pliku wyjściowego. Generowanie biblioteki typów dla zestawu, który odwołuje się do innych zestawów może spowodować, że zostanie wygenerowanych kilka bibliotek typów na raz. Możesz użyć biblioteki typów, aby dostarczyć informacje o typie do narzędzi programistycznych, takich jak Visual Studio. Nie używaj opcji **/TLB** , jeśli rejestrowany zestaw został wyprodukowany przez Importer biblioteki typów ([Tlbimp.exe](tlbimp-exe-type-library-importer.md)). Nie można wyeksportować biblioteki typów z zestawu, który został zaimportowany z biblioteki typów. Użycie opcji **/TLB** ma taki sam efekt jak użycie eksportera biblioteki typów ([Tlbexp.exe](tlbexp-exe-type-library-exporter.md)) i Regasm.exe, z wyjątkiem tego, że Tlbexp.exe nie rejestruje biblioteki typów, która produkuje.  Jeśli używasz opcji **/TLB** do zarejestrowania biblioteki typów, możesz użyć opcji **/TLB** z **/Unregister** opcji, aby wyrejestrować bibliotekę typów. Użycie obu tych opcji razem wyrejestruje bibliotekę typów i wpisy interfejsu, co może znacznie oczyścić rejestr.

Po zarejestrowaniu zestawu do użycia przez model COM, Regasm.exe dodaje wpisy do rejestru komputera lokalnego. Dokładniej, tworzy zależne od wersji klucze rejestru, które umożliwiają równoległe uruchomienie na komputerze wielu wersji tego samego zestawu. Przy pierwszym zarejestrowaniu zestawu jest tworzony jeden klucz najwyższego poziomu dla zestawu, a dla konkretnej wersji tworzony jest unikatowy podklucz. Za każdym razem, gdy rejestrowana jest nowa wersja zestawu, Regasm.exe tworzy podklucz dla nowej wersji.

Na przykład rozważmy scenariusz, w którym rejestrujemy składnik zarządzany myComp.dll w wersji 1.0.0.0 do użycia przez model COM. Później można zarejestrować myComp.dll w wersji 2.0.0.0. Należy określić, że wszystkie aplikacje klienckie modelu COM na komputerze używają myComp.dll w wersji 2.0.0.0 i użytkownik decyduje się wyrejestrować myComponent.dll w wersji 1.0.0.0. Schemat rejestru umożliwia wyrejestrowanie myComp.dll w wersji 1.0.0.0, ponieważ jest usuwany tylko podklucz wersji 1.0.0.0.

Po zarejestrowaniu zestawu przy użyciu Regasm.exe można go zainstalować w [globalnej pamięci podręcznej zestawów](../app-domains/gac.md) , aby można go było aktywować z dowolnego klienta com. Jeżeli zestaw będzie aktywowany tylko przez jedną aplikację, należy go umieścić w katalogu tej aplikacji.

## <a name="examples"></a>Przykłady

Następujące polecenie rejestruje wszystkie klasy publiczne zawarte w `myTest.dll` .

```console
regasm myTest.dll
```

Następujące polecenie generuje plik `myTest.reg` , który zawiera wszystkie niezbędne wpisy rejestru. Polecenie to nie powoduje aktualizacji rejestru.

```console
regasm myTest.dll /regfile:myTest.reg
```

Następujące polecenie rejestruje wszystkie klasy publiczne zawarte w i `myTest.dll` generuje i rejestruje bibliotekę typów `myTest.tlb` , która zawiera definicje wszystkich typów publicznych zdefiniowanych w `myTest.dll` .

```console
regasm myTest.dll /tlb:myTest.tlb
```

## <a name="see-also"></a>Zobacz także

- [Narzędzia](index.md)
- [Tlbexp.exe (Eksporter biblioteki typów)](tlbexp-exe-type-library-exporter.md)
- [Tlbimp.exe (Importer biblioteki typów)](tlbimp-exe-type-library-importer.md)
- [Rejestrowanie zestawów do użycia z modelem COM](../interop/registering-assemblies-with-com.md)
- [Wiersze poleceń](developer-command-prompt-for-vs.md)
